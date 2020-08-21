Bitpay
===============

**Bitpay is a Splynx add-on which allows refilling of customer balances and paying of invoices via the Bitpay payment gateway - https://bitpay.com.**

The add-on can be installed in two methods, via the CLI or the Web UI of your Splynx server.

To install the splynx-bitpay add-on via CLI, the following commands can be used:

```
apt-get update
apt-get install splynx-bitpay
```
To install it via the Web UI:

Navigate to `Config → Integrations → Add-ons`:

Locate or search for the "splynx-bitpay" add-on and click on the install icon in the *Actions* column:

![(image)](1.png)

Click on the "OK, confirm" button to begin the installation process:

![(image)](2.png)


After the installation process has completed, we can configure the add-on under  *Config -> Integrations -> Modules list:*

Locate or search for the "splynx-bitpay" add-on and click on the edit icon in the *Actions* column:

![(image)](3.png)

![(image)](4.png)

Enter your Splynx URL into the field provided:

![(image)](5.png)

Thereafter, you need to retrieve a **"Pairing Code"** from BitPay. To retrieve the **"Pairing Code"**, please open your *Bitpay dashboard → Payment Tools*, select *Manage API Tokens* and *create a New Token*, as depicted below:

![(image)](6.png)

You can then enter your pairing code in *Config → Integrations → Bitpay → Pairing code:*

![(image)](7.png)

![(image)](8.png)

Thereafter, customers will be able to pay for their invoices and refill their balances using the Bitpay system. Customers will see a new button "Pay" on their customer portal Dashboard:

![(image)](8.1.png)

The new icon will also appear in the Invoices section as depicted below:

![(image)](8.2.png)

The following window will appear when a customer clicks on the new pay button:

![(image)](8.3.png)

Customers will be redirected to Bitpay-page upon clicking the icon in the window:

![(image)](8.4.png)

The customer will have to select a currency:

![(image)](8.5.png)

Then confirm the payment:

![(image)](8.6.png)

If the payment was successful, the status of invoice will be marked as "Paid":

![(image)](10.1.png)

To refill balance, customers can use the link - “http://yoursplynxurl/bitpay” where they have to enter an Amount of the payment and click on "Pay":

![(image)](12.png)
