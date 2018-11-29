SagePay Direct debit
====================

**SagePay Direct debit is a Splynx add-on. It used to customers be able to pay their invoices by https://sagepay.co.za/**

Install the add-on with commands:

```bash
apt update
apt install splynx-sagepay-direct-debit
```

**or you can install it from Web UI:**

**Config → Integrations → Add-ons:**

![1.png](1.png)

![2.png](2.png)


**After that you need to registrate on **[*https://sagepay.co.za/*](https://sagepay.co.za/)** .**

After installation and registration you have to configure params:

Config → Integrations → Modules list:
![3.png](3.png)

![11.png](11.png)


****Servicice key - this key need only when customers use their own credit cards to pay.****


You can also set fee for customers and Set admins roles to access from admin panel:

![3.png](3.png)

![5.png](5.png)

After installation SegaPay Direct Debit, customers will see new pay window on their Dashboard and new pay button on their invoices.

![6.png](6.png)

![7.png](7.png)

After pressing those buttons customers will see payment window where they have to set their Credit card or Bank account depending on how they want to pay their invoices:

![20.png](20.png)

or they can set their credit card or bank account in *finance -> credit card* to use it all the time when they will make payments:

![21.png](21.png)


You can also charge all customers using one button! Go to: Finance → Invoices, set period and click "Charge" as on the screenshot:

![8.png](8.png)

![9.png](9.png)



After that splynx will create and send debit batch file with payment details to the [*https://sagepay.co.za/*](https://sagepay.co.za/) after what SegaPay procces this file. (The Statement API runs everyday at 00h15 and cheks all transactions for the previous day)

Then you need to send the request once per day to SagePay by ****cron**** and sage pay will return you payment status or you can view Payments status by *“Sage Pay check payments”* in the *finance* menu:

![12.jpg](12.jpg)
