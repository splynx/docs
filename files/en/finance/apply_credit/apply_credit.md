How to apply Credit to future invoices
====================================

Sometimes your customer has a positive account balance, it is not enough for the next payment, but he wants to use it to reduce the invoice amount.

For example, the customer's account balance is $10:


![Preview](1.png)

from transactions you can see the same, his first payment was more than invoiced amount:

![Preview](2.png)

from the Services you can see the tariff price is $35:

![Preview](3.png)

and the same price you will see on the next charge (invoice):

![Preview](4.png)


To solve this issue and apply $10 to the future invoice, you have to go through the next steps:

1. Create a Debit transaction with the same Total as account balance (Description and Category they don't matter):

![Preview](5.png)

2. Create a Credit transaction with the same Total as account balance, but it's **critical to turn on "To invoice" toggle**:

![Preview](6.png)

That's all you need - only two transactions. Then we can check customer`s balance (it's the same - $10):

![Preview](7.png)

At last, you can create a future invoice via "To Charge" button or just wait for a Billing day and the system will automatically create it:

![Preview](8.png)

As you can see - a new invoice includes Credit correction transaction and reduced total amount.

Notice: Please don't worry if preview via To Charge button will not show the Credit transaction - it's normal. The invoice will be correct, with Credit transaction in any way.