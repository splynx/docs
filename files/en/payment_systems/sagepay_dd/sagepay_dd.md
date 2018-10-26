SagePay Direct debit
====================

**SagePay Direct debit is a Splynx add-on. It used to customers be able to pay their invoices by **https://sagepay.co.za/**

Install the add-on with commands:

```bash
apt update
apt install splynx-sagepay-direct-debit
```

**or you can install it from Web UI:**

**Config → Integrations → Add-ons:**

![1.png](1.png)
****

****

**After that you need to registrate on **[*https://sagepay.co.za/*](https://sagepay.co.za/)** .**

**After installation and registration you have to configure params:**

Config → Integrations → Modules list:

****

****

****Serv******ice key- this key need onl******y when customers use their own credit cards to pay.****

****

**You can also set fee for customers and **Set admins roles to access from admin panel:**

****

****

**After **installation** SegaPay Direct Debit, customers will see new pay window on their Dashboard and new pay button on their invoices.**

****

****

**You can also charge all customers using one button! Go to ***Finance → Invoices***, set period and click "Charge" as on the screenshot: **

****

****

****

**A**fter that **splynx will **create and **send **debit **batch file with payment details to the **[*https://sagepay.co.za/*](https://sagepay.co.za/)** after what **SegaPay procces this file. (The Statement API runs everyday at 00h15 and cheks all transactions for the previous day) **

**Then you need to send the request once per day** to SagePay by ****cron**** and sage pay will return you payment status **or you can** view Payments status **forcibly** by “Sage Pay check payments” in the finance menu:**

****
