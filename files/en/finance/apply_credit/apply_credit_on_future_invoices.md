How to apply Credit on future invoices
====================================

Sometimes your customer has positive account balance, not enough for next payment but he want to use it for reduce from invoice amount. 

For example: customer`s account balance is $10:

![Preview](1.png)

from transactions you can see the same, his first payment was more than invoiced amount:

![Preview](2.png)

from the services you can see the service price as $35:

![Preview](3.png)

and same price you will see on the next charge (invoice):

![Preview](4.png)


For solving this issue and apply $10 to the future invoice you have to go through next steps:

1. Create a Debit transaction with same total as account balance (Description and Category they doesn't matter):

![Preview](5.png)

2. Create a Credit transaction with same total as account balance, but it's **critical - turn on "To invoice" toggle**:

![Preview](6.png)

That's all you need - only two transactions. Then we can check customer`s balance (it's the same - $10):

![Preview](7.png)

At last you can create future invoice via "To Charge" button or just wait Billing day and the system automatically create it:

![Preview](8.png)

As you can see - new invoice included Credit correction transaction and total reduced.

Notice: Please don't worry if preview via To Charge button will not show Credit transaction - it's normal. Invoice will correct, with Credit transaction in any way.