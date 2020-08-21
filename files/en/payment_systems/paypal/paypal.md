Paypal payments
==========

You can receive payments via PayPal using Splynx. Splynx generates invoices for services that are sent to customer’s email and to the Splynx customer portal. From the customer portal, customer can pay for their invoices using Paypal.

![Invoices](portal_invoices.png)


When a customer clicks on the PayPal button and applies to pay now, he is redirected to the PayPal page to make the payment.


Customers can also add a credit card on the PayPal payment webpage, if they don’t have a PayPal account.

![Add card](3.png)


After payment has been made, the invoice is marked as paid, a transaction is created in Splynx and the customer’s balance is changed.


---
There are several steps needed to configure the Splynx PayPal add-on. The add-on can be installed in two methods, via the CLI or the Web UI of your Splynx server.

#### Installation

To install the "splynx-PayPal" add-on via CLI, the following commands can be used:

```
apt-get update
apt-get install splynx-paypal
```
To install it via the Web UI:

Navigate to `Config → Integrations → Add-ons`:

![4.png](4.png)

Locate or search for the "splynx-paypal" add-on and click on the install icon in the *Actions* column, you will be presented wwith a window to confirm or cancel the Installation, click on confirm to begin the Installation process:

![install.png](install.png)

#### Activate the developer’s tool in your PayPal account.

Obtain the access to your business PayPal account on the following website: https://developer.paypal.com

The ClientID and ClientSecret are the values Splynx needs to configure the add-on. Click on Add new Rest API application and call it Splynx.

![REST API](6.png)


Thereafter, you can find the ClientID and Secret on the application page. It is important to choose the “Live” version, because it shows the values for the test Sandbox account by default.

![Credentials](7.png)

When you have obtained the ClientID and Secret, you can insert it into your Splynx server and connect Splynx with PayPal.

#### Configure Splynx to work with your PayPal account.

Once the add-on has been installed and all details from PayPal has obtained, we can proceed to configuring the add-on.

Navigate to `Config/Modules/List` and click on the edit button of the Splynx PayPal addon:

![Edit.png](edit_module.png)

You can find Common settings and Partners settings in this section:

![Common settings](settings1.png)
![Common settings](settings2.png)

Each partner can use different settings

---
On this page you can also enable widgets for the customer portal.
Click on the "Entry points" button:

![Common settings](entry_points.png)

First widget(Point) configuration:
![Enable widget](edit_entry1.png)

Point 1 on customer portal page:
![Common settings](portal_entry1.png)

Second widget(Point) configuration:
![Enable widget](edit_entry2.png)

Point 2 on customer portal page:
![Common settings](portal_entry2.png)

##### NOTE: Point 2 will only be visible for customers using the *Prepaid (Daily) type of billing*

Paying for invoices with PayPal:

On customer portal page navigate to `Finance/Invoices` select a unpaid invoice and click on the "pay with PayPal" button

![Pay invoice](portal_invoices.png)
![Pay invoice](pay_with_paypal.png)

You can allow customers using the *Prepaid (Monthly)* billing type to use the last widget available. To achieve this, the code has to be modified. Replace `if customer.billing_type == 'prepaid'` to `if customer.billing_type == 'prepaid_monthly' or customer.billing_type == 'prepaid'`:
