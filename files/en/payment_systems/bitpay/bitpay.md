**Bitpay is a Splynx add-on. It allows to refill balance and pay invoices via Bitpay payment gateway - https://bitpay.com.**

To install splynx-bitpay add-on, use following commands:

apt-get update

apt-get install splynx-bitpay

or you can install it from Web UI:

Config → Integrations → Add-ons:

![(image)](1.png)

![(image)](2.png)
after installation you have to Enter your splynx url on the *config -> integrations -> modules list:*

![(image)](3.png)

![(image)](4.png)

![(image)](5.png)

After that you need to receive **"Pairing Code"**. To receive **"Pairing Code"**, please open your *Bitpay dashboard → Payment Tools*, choose *Manage API Tokens* and *create New Token*, like on the screenshot:

![(image)](6.png)
Now you need to enter your pairing code in *Config → Integrations → Bitpay → Pairing code:*

![(image)](7.png)

![(image)](8.png)

After that customers can pay their invoices and refill balances using Bitpay system. They will see a new button "Pay" on Dashboard:

![(image)](8.1.png)

and new icon in Invoices as on a screenshot:

![(image)](8.2.png)

When customer will press pay button he will see new window:

![(image)](8.3.png)

After that he will be redirected to Bitpay-page:

![(image)](8.4.png)

Then customer must choose currency:

![(image)](8.5.png)

Then customer has to confirm a payment:

![(image)](8.6.png)

If payment was successful, the status of invoice will  be "Paid":

![(image)](10.1.png)

To refill balance customers can use the link - “http://yoursplynxurl/bitpay” where they have to enter Amount of payment and click "Pay":

![(image)](12.png)
