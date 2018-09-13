#### Webhooks

Webhooks allow you to build external Apps which subscribe to certain events on Splynx system. When one of those events is triggered, we'll send a HTTP POST payload to the webhook's configured URL.

#### Events

When configuring a webhook, you can choose which events you would like to receive payloads for.

#### Handle webhook events

For validate event you need to check header `X-Splynx-Signature` which contains the event signature. Signature is generated from response body string using the `sha1` hash function and the secret as the `HMAC key`.

#### Example PHP webhook handler

```php
<?php

define('REQUEST_TYPE_PING', 'ping');
define('REQUEST_TYPE_EVENT', 'event');
define('CONTENT_TYPE_JSON', 'application/json');
define('CONTENT_TYPE_FORM_URLENCODED', 'application/x-www-form-urlencoded');

$headers = getHeaders();
$input = file_get_contents('php://input');
$contentType = isset($headers['Content-Type']) ? $headers['Content-Type'] : '';

// Parse payload data
if ($contentType == CONTENT_TYPE_JSON) {
    $postData = json_decode($input, true);
} else {
    parse_str($input, $postData);
}

$requestType = isset($postData['type']) ? $postData['type'] : null;

// Process ping request
if ($requestType === REQUEST_TYPE_PING) {
    http_response_code(200);
    exit('ok');
}

// Validate request type
if ($requestType !== REQUEST_TYPE_EVENT) {
    http_response_code(400);
    exit('Invalid request type!');
}

// Calculate signature from payload and secret
$secret = 'your secret';
$calculatedSignature = hash_hmac('sha1', $input, $secret);

// Signature from HTTP request header
$inputSignature = isset($headers['X-Splynx-Signature']) ? $headers['X-Splynx-Signature'] : '';

// Compare signatures
if (hash_equals($inputSignature, $calculatedSignature)) {
    http_response_code(200);
    echo 'ok';

    // Success, you can process event as you want
    // ...
} else {
    // Invalid signature, return from code
    http_response_code(401);
    exit('Unauthorized!');
}

// Specific PHP function for safe getting HTTP headers
function getHeaders()
{
    $headers = [];

    if (function_exists('getallheaders')) {
        $headers = getallheaders();
    } elseif (function_exists('http_get_request_headers')) {
        $headers = http_get_request_headers();
    } else {
        foreach ($_SERVER as $name => $value) {
            if (strncmp($name, 'HTTP_', 5) === 0) {
                $name = str_replace(' ', '-', ucwords(strtolower(str_replace('_', ' ', substr($name, 5)))));
                $headers[$name] = $value;
            }
        }
    }

    return $headers;
}
```
