SagePay
====================

**SagePay Direct debit is a Splynx add-on. It used to customers be able to pay their invoices by https://sagepay.co.za/**

Install the add-on with commands:

```bash
apt update
apt install splynx-sagepay
```

**or you can install it from Web UI:**

**Config → Integrations → Add-ons:**

![1.png](0.png)

![1.png](1.png)

**After that you need to registrate on **[*https://sagepay.co.za/*](https://sagepay.co.za/)**  **and configure your account.**

![1.png](5.png)

![1.png](6.png)

![1.png](7.png)

After installation and registration you have to configure add-on params:

Config → Integrations → Modules list:

![1.png](4.png)

![1.png](8.png)

![1.png](9.png)
![1.png](10.png)

**Entry point status for portal** means enable SagePay widget for customer portal.
**Service key** and **Software vendor key** provided by SagePay.
After installation SagePay, customers will see a new pay button on their invoices.

![1.png](11.png)

After pressing those buttons customers will see payment window where they have to confirm payment:

![1.png](12.png)

![1.png](13.png)

![1.png](14.png)

If everything went well, you will see status of invoice as "Paid" (portal and admin).

Also if in SagePay module settings entry points(widgets) enabled you will see this widget on customer portal:
![1.png](15.png)
