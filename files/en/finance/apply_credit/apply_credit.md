How to apply Credit to future invoices
====================================

In certain cases, you may have a customer with a positive balance however it is not enough to pay for the cost of their services on the next invoice. So the customer wants this positive balance to be deducted from the next invoice. Let's use an example to illustrate the process of applying credit to a customer's account.


For example, the customer's account balance is $10:


![Preview](1.png)

From the list of transactions you can see That the customer's first payment was more than invoiced amount:

![Preview](2.png)

From the Services tab, you can see the tariff price is $35:

![Preview](3.png)

If you were to charge the customer for the next invoice, you will see the price of the service again on the invoice preview:

![Preview](4.png)


To resolve this issue and apply $10 credit to the future invoice,  the next steps should be taken:

1. Create a Debit transaction with the same Total as account balance (Description and Category doesn't really matter, this is for your personal reference):

![Preview](5.png)

2. Create a Credit transaction with the same Total as account balance, but it's **critical to turn on the "To invoice" toggle**:

![Preview](6.png)

That's all you need to do  - only two transactions. Then we can check the customer's balance (it's the same - $10):

![Preview](7.png)


The final step will be to charge the customer for the future invoice with the "Charge & Invoice" button in the Billing overview tab or simply wait for the next billing day for the system to create the invoice automatically:

![Preview](8.png)

As you can see - the new invoice includes the Credit correction transaction and the reduced total amount.

_Notice: Please don't worry if the preview via the Charge & invoice button does not show the Credit transaction - it is normal. The invoice will be correct, with Credit transaction if these steps were taken._
