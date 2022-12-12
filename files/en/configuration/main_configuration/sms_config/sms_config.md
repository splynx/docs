SMS sending configuration
=========

Splynx supports sending of SMS's using the different SMS gateways. To configure SMS sending you need to find a suitable SMS gateway and set up Splynx to work with it.

To configure SMS sending in Splynx, navigate to `Config → Main → SMS`.

![Config menu](icon.png)

**NOTE: The configuration will be unique for each SMS gateway.**

The **SMS logs** can be found in [`Administration → Logs → SMS`](administration/logs/sms/sms.md) or in [`Messages → Mass sending → History`](support_messages/sms_messages/sms_messages.md).

### Main

![Main sms](main_sms.png)
* **Gateway URL** - specify the URL of the SMS gateway (should be specified in gateway documentation);
* **Payload** - request payload for sending SMS. Depends on content type (*JSON* or *x-www-form-urlencoded*) and syntax provided by SMS gateway;
* **Method** - select the method to call the gateway (*POST* or *GET*);
* **Content type** - how to handle the payload (*JSON* or *x-www-form-urlencoded*). **JSON can be used only with POST method**;
* **Verify SSL certificate** - if the toggle is enabled, the system will verify the SSL certificate of the SMS gateway host with a secure (HTTPS) connection;
* **Enable SMS sending** - enables/disables SMS sending from Splynx;
* **Debug** - enable/disable the writing of debugging information to the log file `/var/www/splynx/logs/cron/sms.log`;
* **Successful response** - if the SMS gateway returns a certain successful response, the text to check response from gateway must be configured here so that Splynx can identify which SMS was sent;
* **Days until expiration** - how many days the server will try to send the SMS. After that the message status will be changed to "Error".


### Check SMS balance

![check balance](check_balance.png)
* **Enalbe** - enable/disable the SMS balance checking;
* **Check URL** - specify the URL which is used for checking SMS balance. It should be specified in gateway documentation (the first number in response will be parsed as the account balance value. You can change this behavior by defining the account balance field name in the field below;
* **Field name** - name of the field with the account balance;
* **Requested method** - select the method to call the gateway (*GET* or *POST*);
* **Once per** - check balance every selected period of time (*5 min*, *hour*, *day*);
* **Email** - result will be sent to this email;
* **Dashboard notification** - enables/disables notifications with SMS account balance on the dashboard;
* **Minimum balance** - balance value at which the notification is triggered.


### Custom header

The header is used for authentication. It can be either the *username* you supplied when you registered on your SMS gateway service or an *API Token*.

To know how to use these values correctly, always double-check the SMS gateway documentation.

![header1](custom_header1.png)


### Test

![test](test.png)

* **Phone** - the target phone number to send a test SMS to. Sometimes `+` sign must be added before the actual number (full format of the phone number for your country).


------------

<details style="font-size: 15px; margin-bottom: 5px;">
<summary>Example of Bulk SMS gateway configuration</summary>
<div markdown="1">




1. First of all, you need to have a valid account on https://www.bulksms.com/ and configure API Token to connect it with Splynx - [Register your BulkSMS account](https://www.bulksms.com/account/#!/registration);


2. On BulkSMS account page, navigate to `Settings → Advanced` and press **Create Token** button, type the name to your token. In a new window will be shown only once the credentials to your token, copy and save them.

![image](bulk_sms_1.png)

![image](bulk_sms_2.png)

![image](bulk_sms_3.png)



3. To **request sender id** which will be shown in SMS for your customers, navigate to `Settings → Message` and click on *Sender IDs* tab.

**NOTE:** You need to purchase credits at least once before you can use this facility.

![image](bulk_sms_4.png)



4. In Splynx, navigate to `Config → Main → SMS`, in **Main** section configure the following settings:


<details style="font-size: 12px; margin-bottom: 5px;">
<summary>The values example</summary>
<div markdown="1">


**Gateway URL:**

```
https://api.bulksms.com/v1/messages
```

**Payload:**

```
{"from": "YourSenderID", "to": "%TO%", "body": "%MESSAGE%"}
```


</div>
</details>




![image](bulk_sms_5.png)


In **Check SMS balance** section configure the next settings:

![image](bulk_sms_7.png)

Click on `Run test` to check the balance, the result will be shown in **Test result** area at the bottom of the page.

![image](bulk_sms_8.png)

In **Custom header** section use the generated `Basic Auth` value:

![image](bulk_sms_6.png)



5. In **Test** section, type your test phone number to check the SMS configuration

![test](test.png)

![image](bulk_sms_9.png)

More information you can find in these articles:


- [BulkSMS JSON REST API (v1.0.0)](https://www.bulksms.com/developer/json/v1/#)

- [BulkSMS generic error types](https://www.bulksms.com/developer/json/v1/errors/)



</div>
</details>



------------




<details style="font-size: 15px; margin-bottom: 5px;">
<summary>Example of Clickatell SMS gateway configuration</summary>
<div markdown="1">


![main](main.png)

* **Gateway URL** - ```https://platform.clickatell.com/messages```
* **Payload** - ```{''to'': [''%TO%''], ''content'': ''%MESSAGE%''}```


![main](check_balance.png)

* **Check URL** - ```https://platform.clickatell.com/public-client/balance?Authorization:your_API_key```

![image](bulk_sms_6.png)

* **Custom Header Name** - header parameter name, e.g `Authorization`;
* **Custom Header Value** - API Key.

For more information, see:

- https://www.clickatell.com/products/sms-platform

- https://docs.clickatell.com/channels/sms-channels/sms-api-documentation/

- https://docs.clickatell.com/channels/sms-channels/sms-api-reference/



</div>
</details>



------------




<details style="font-size: 15px; margin-bottom: 5px;">
<summary>Example of BurstSMS SMS gateway configuration</summary>
<div markdown="1">


![main](urlencoded_main.png)

![image](bulk_sms_6.png)

For more information, see:

- https://burstsms.com.au/sms-api





</div>
</details>



------------



We have a special topic on our forum where you can find a suitable SMS gateway and find out which gateways can't be used in Splynx:

- https://forum.splynx.com/t/sms-gateway-sharing-recommendations/1963 .


You might also be interested in video tutorial:

<iframe width="350" height="270" src="https://www.youtube.com/embed/grh1nMXrP4g" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
