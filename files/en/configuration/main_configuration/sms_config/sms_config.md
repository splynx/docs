SMS sending configuration
=========

Splynx supports sending of SMS using different SMS gateways. To configure SMS sending you need to find a suitable SMS gateway and set up Splynx to work with it.

To configure SMS sending in Splynx navigate to `Config → Main → SMS`.

![Config menu](icon.png)

**NOTE! Configuration will be unique for each SMS gateway.**

**SMS logs can be found under [`Administration - Logs - SMS`](../../../administration/logs/sms/sms.md) or under `Support - Messages - History`**

Example of [Clikatell SMS gateway](https://www.clickatell.com/) configuration:
![main](main.png)
![main](custom_header.png)

Example of [BurstSMS SMS gateway](https://burstsms.com.au/sms-api) configuration:
![main](urlencoded_main.png)
![main](urlencoded_header.png)

## Main
* **Gateway URL** - URL of SMS gateway(should be specified in gateway documentation);
* **Payload** - request payload for sending SMS. Depends on content type(JSON or x-www-form-urlencoded) and syntax provided by SMS gateway;
* **Method** - method to call gateway (POST or GET);
* **Content type** - how to handle payload (JSON or x-www-form-urlencoded). JSON can be used only with POST method;
* **Enable SMS sending** - enable/disable SMS sending from Splynx;
* **Debug** - enable/disable debug to log file */var/www/splynx/logs/cron/sms.log*;
* **Successful response** - if SMS gateway returns some successful response it should be configured here so Splynx could know what SMS was sent;
* **Days to expire** - how many days server will try to send SMS. Then will be marked as "Error".

## Check SMS balance
Example of check SMS balance config using [Clikatell SMS gateway](https://www.clickatell.com/)
![main](check_balance.png)

* **Enalbe** - enable/disable checking SMS balance;
* **Check URL** - URL what is using for checking SMS balance(should be in gateway documentation);
* **Field name** - name of field with account balance;
* **Requested method** - method to call gateway(GET or POST);
* **Once per** - check balance every selected period of time;
* **Email** - result will be send to this email;
* **Dashboard notification** - enable/disable notification with SMS account balance on dashboard;
* **Minimum balance** - balance value which will trigger notification.

## Custom header
Sometimes needed for configuration of SMS sending. To use or not to use - must be described in SMS gateway documentation.

Few examples of custom headers below:

![header1](custom_header.png)
OR
![header2](urlencoded_header.png)

## Test

![test](test.png)

* **Phone** - target phone number to make test. Sometimes must be specified with "+" ahead(full format of phone number for country).

We have a special topic on forum where you can find a suitable SMS gateway and find our what gateways can't be used in Splynx: https://forum.splynx.com/t/sms-gateway-sharing-recommendations/1963/8
