PayU Africa
===========

**PayU africa** is a Splynx add-on. It is used to pay via **PayU** Payment Gateway - [https://www.payu.co.za/](https://www.payu.co.za/)

To install Payu Africa addon use following commands:

```bash
apt-get update
apt-get install splynx-payu-africa
```
or you can install it from Web UI:

*Config -> Params -> Add-ons:*

![(image)](11.png)

![(image)](12.png)

![(image)](13.png)

You need a PayU account to start the integration. Registration page - [https://www.payu.co.za/enquiry-form](https://www.payu.co.za/enquiry-form)

PayU will provide you access to the Merchant Portal. At the Merchant Portal you will find: **Soap user name**, **SOAP Password** and **SafeKey**

After add-on installation you have to configure it under _Config / Integrations / Modules List_

![(image)](Modules_list.png)

![(image)](Module_edit.png)

![(image)](Settings.png)

![(image)](Settings2.png)

* **Splynx URL** – URL of your server
* **Is Production** – Yes
* **Soap Username**, **Soap password**, **Safekey** – values from PayU’s Merchant Portal (look at the previous step)

Now customers can pay via PayU portal in _Finance / Invoices_

![(image)](Invoices_list_(customers_portal).png)
![(image)](Paying_window.png)
![(image)](Payment_Success.png)

![(image)](Payment_Success2.png)

When a customer pays the invoice, the information about the card is saved to the system. Customers can look at their stored cards at the _Finance / Credit card via PayU Africa gateway_. Customers can remove their cards here, but do not add. They can add a card only during payment process

![(image)](Add_card.png)

![(image)](Add_card2.png)

Besides that, you can charge all customers, using one button! Go to _Finance / Invoices_, set the period and click "_Charge_" as on a screen-shot:

![(image)](payuA_Selection_096.png)

![(image)](payuA_Selection_097.png)
