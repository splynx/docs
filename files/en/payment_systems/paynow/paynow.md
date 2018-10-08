Paynow Zimbabwe
===============

Paynow Zimbabwe is a Splynx add-on to make payments via Paynow payment gateway - [https://paynow.co.zw/](https://paynow.co.zw/).

To install Paynow Zimbabwe add-on, use following commands:

```bash
apt-get update
apt-get install splynx-paynow
```

## Paynow account

To use this Splynx add-on, it is necessary to have **Paynow 3rd party shopping cart**.

To create this:

1. Register your Paynow account
2. Log in
3. In the upper menu, choose **Receive Payments** / **Other ways to get paid**  
    ![(image)](Menu_060.png)

4. Under **3rd Party Shopping Carts & Business Systems Integration** press the button **Create/Manage Shopping Carts**  
    ![(image)](Selection_061.png)

5. **Under Advanced Integration** press the button **Create Advanced Integration**  
    ![(image)](Selection_062.png)

6. Fill out the form and press **Save**
   ![(image)](Selection_063.png)

7. After you have pressed **Save**, the section **Integration Key** appears.  
    Copy **Intergration ID** and paste it into Splynx.  
    Press the button **Email Key To**. Email letter will be sent to **Notification Email** address. Copy **Integration Key** and paste it into Splynx.
    ![(image)](Selection_064.png)

## Configuration

Add-on configuration - _Config / Integrations / Modules list / splynx_paynow_addon_

![(image)](Modules_list.png)

![(image)](paynow_edit-module.png)

## Entry points

By using **Entry points**, you can enable add-on features. You allow:

1. Customers to pay invoices
   ![(image)](paynow_entry-point-1.png)

2. Customers to pay proforma invoices
   ![(image)](paynow_entry-point-2.png)

3. Customers to pay invoices and proforma invoices from portal dashboard  
   ![(image)](paynow_entry-point-3.png)

4. Customer with **type of billing** - **prepaid** to put money into account from portal dashboard  
   ![(image)](paynow_entry-point-4.png)

## Add On settings

![(image)](paynow_add-on-settings1.png)

* **API domain** - URL of Splynx server
* **API key**, **API secret** - default values. Don't change them
* **Integration ID**, **Integration Key** - values from Paynow portal

![(image)](paynow_add-on-settings2.png)

* **Splynx url** - URL of Splynx server

* **Payment method ID** - id number of payment method from **Config** / **Finance** / **Payment methods**

* **Bank statements group** - Group bank statements (**Config** / **Finance** / **Bank Statements** / **History**) monthly or daily

* **Service Fee** - Paynow commision (in %). Depends on Paynow plan

* **Add fee to request** - Add **service fee** to proforma invoice (as an additional item)

* **Fee message** - Description of fee invoice item

* **Fee VAT** - VAT of Paynow comission (in %). Will be included into service fee

* **Transaction fee category** - id number of transaction category from **Config** / **Finance** / **Transaction categories**

* **Additional info pattern for Paynow** - the value will be shown at the Paynow payment page. Look at the screenshot:  
  ![(image)](paynow-payment.png)