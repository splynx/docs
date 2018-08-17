Transactions
============

The whole billing process inside Splynx is based on transactions. Transactions are the key point in billing, and they are always added when there is a change in the customer’s flow or balance:

a. _Each invoice period Splynx charges customers automatically._ The admininstrator can set up the invoice date as the 1st day of the month, and then customer will be charged for the calendar month.
Splynx has the ability to charge each customer on a different date. For example, one customer is charged on the 15th day of the month, and another customer is charged on the 20th. This action creates an “+ Debit” transaction.

b. _When a customer pays for services, a transaction is created._ He can pay via bank transfer, cash or online payment gateway. Splynx will always pair the payment with the customer’s account and create one payment transaction. A “- Credit” transaction is then created.

c. _When administrator adds or removes money to/from the customer’s balance._

d. _When correction is needed, it’s also achieved with a transaction._

Thanks to the transaction system, there is always a clear history as well as a way to track changes in the customer’s profile.

---

Transactions table in _Finance Module_ displays all type of transactions related to the customer and contain Customer name, ID, date of transaction, type of transaction (debit or credit), its description, price etc.

* There is a table called "_Totals_" below which shows `type of transaction` (Debit / Credit), `number of transactions` in each type and `total amount of money`.

  ![Transactions](./transactions.png?w=300)
  
* In fact you can set a filter to view particular transactions, for example, by partner, by transaction's category or its type or period. 

  ![Filters](./filters.png?w=300)
  
* There is an option to print out, copy or save in CSV or PDF files transactions, chosen by you.
  
  ![Buttons](./print.png?w=300)
  
* You can also choose columns which will be displayed in the transactions table by sorting show/hide columns.

  ![Columns](./columns.png?w=300)
  
* **To correct customer's balance** is possible to create a new transaction and add invoice from transaction. You can find that option in _Customer → View Customer → Billing → Transactions_.
  
  ![Add transaction](./add_transaction.png?w=300)
  
  When you click on _Add transaction_ a pop-up window will appear with different options of new transaction you can choose: `Type (Debit/ Credit)`, `Description`, `Quantity`, `Unit`, `Price`, `VAT`, `Total amount`, `Category` (service, discount, payment, correction for customer's balance, Braintree fee etc.), `Date`, `Comment` on the transaction and `Period`.

  ![Add transaction form](./create_transaction_form.png?w=300)

* After the new transaction's created it is also possible **to generate an invoice manually** by clicking on _Add Invoice from transaction_ in the Transactions tab. The window will pop-up where you can fill in following fields: `Description`, `Price`, `Period`, `Note` for the customer or `Memo` for you (if necessary).
  
  ![Create invoice](./create_invoice.png?w=300)
  
* Once transaction is created it is possible to edit or delete it ![Buttons](./small_buttons.png) . Please note, if you've added an Invoice from transaction there is no longer a possibility to edit that transaction, but invoice only.   