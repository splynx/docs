Cashdesk
========

Cashdesk is a Splynx module for processing payments. Administrator can create users of cashdesk and provide them access to the module. User is not able to change and view any customer’s data, except his name/company name, invoice numbers and actual balance. The cashdesk can be used by accountants, who doesn’t have to get access to Splynx, but only process the incoming payments. It can be also used by resellers. Reseller will see only his customers and is able to enter payments to Splynx when he receives money from customer.  

The first step for Cashdesk activation is installation. It’s performed by two following commands in Linux CLI where Splynx is installed:

```bash
apt-get update  
apt-get install splynx-cashdesk
```
or you can install it from Web UI:

*Config -> Integrations -> Add-ons:*

![01.png](01.png)

![02.png](02.png)

![03.png](03.png)

All configs you can find in Config / Modules / List:

![Selection_892.png](Selection_892.png)

then click edit Cashdesk and you can change Payment method ID:

![Selection_893.png](Selection_893.png)

To create a cashdesk user it’s needed to create an administrator and enabled CashDesk access. Other permissions to Splynx access can have define or he can get 0 permission level (defined access Cashdesk only):

![1.jpg](1.png)

Add access privileges for cashdesk-module to the superadministrator - enable CashDesk in superadministrator account.
![Super_admin](super_admin.png)

When the Cashdesk is installed, it’s available on "http://yoursplynxurl/cashdesk".

First step, superadministrator must added deposit for cash-administrators for operations. To do this, you should login as superadministrator (he have full access) and Create deposit:
![2.jpg](2.png)
![3.jpg](3.png)
![4.jpg](4.png)
![5.jpg)](5.png)

Later, you can increase or decrease the amount of the deposit

![6.jpg](6.png)

After clicking the [Deposit History] button you can view the history of the deposit changes

![7.jpg](7.png)

CSV — is export Deposit History to csv-file:
![8.jpg](8.png)

For cashdesk-administrator the first screen is a login page:
![9.jpg](9.png)

Cashdesk user has logged, he can search customers based on customer’s name, login or number of invoice.

![10.jpg](10.png)

After entering the invoice number or customer name in search field, Cashdesk displays customer information about his balance and unpaid invoices.

When we entering a payment we can choose the invoice which will be marked as paid.

![11.jpg](11.png)

After:

![12.jpg](12.png)

When the payment has been added, it appears in Splynx as a new transaction and a payment and also as a invoice .

![13.jpg](13.png)

All payments of the user “Casher” can be found in History section of Cashdesk.

![14.jpg](14.png)

For superadministrator History is extended.

![15.jpg](15.png)

Remember! Only Superadministrator - can delete payments.
