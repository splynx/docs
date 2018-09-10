Paypal payments
==========

You can receive payments via PayPal using Splynx. Splynx generates invoices for services that are sent to customer’s email and to Splynx portal. From Splynx portal customer can pay the invoice using Paypal.

![Invoices](invoices.png)

When customer clicks the PayPal button and applies to pay now, he is transferred to the PayPal page to make the payment.

![Paypal](paypal_com.png)

Customers can also add a credit card on PayPal payment webpage, if they don’t have a PayPal account.

![Add card](add_card.png)


After payment has made, the invoice is marked as paid, transaction in Splynx is created and customer’s balance is changed.


---
There are several steps needed to configure Splynx PayPal add-on:

#### Install the add-on with commands:
```
apt-get update
apt-get install splynx-paypal
```
#### Activate developer’s tool in your PayPal account.
Get the access to your business PayPal account on website https://developer.paypal.com

ClientID and ClientSecret are the values Splynx needs. Click on Add new Rest API application, call it Splynx.

![REST API](rest_api.png)


Then, you can find ClientID and Secret on the page of application. Important is to choose “Live” version, because it shows values for test Sandbox account by default.

![Credentials](credentials.png)

When you got the ClientID and Secret, you can put it to Splynx server and connect Splynx with PayPal.

#### Configure Splynx to work with your PayPal account.

You should go to `Config/Modules/List and click` edit Splynx PayPal addon:
![Edit addon](edit_addon.png)

where you can find Common settings and Partners settings:

![Common settings](in_production.png)

for each partner you can use own settings!

---
#### Also on this page you can enable widgets for the customer portal.

One
![Enable widget](widget1_enable.png)
![Enable widget](widget1.png)

---
Another
![Enable widget](widget2_enable.png)
![Enable widget](widget2.png)
