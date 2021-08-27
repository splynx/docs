Transactions
============

The entire billing process within Splynx is based on transactions. Transactions are the key points in billing and they are always added when there is a change in the customer’s flow or balance. The following actions create transactions:

1. **Each invoice period Splynx charges customers automatically**. The administrator can set up the invoice date as the 1st day of the month, and then the customer will be charged for the calendar month.
Splynx has the ability to charge each customer on a different date. For example, one customer is charged on the 15th day of the month and another customer is charged on the 20th. This action creates an `+ Debit` transaction.

2. **The administrator creates the invoice manually**. This action can be performed in `Billing → Invoices` tab of customer's profile using `Add one-time invoice` button. This action creates an `+ Debit` transaction.

3. **When a customer pays for service, a transaction is created**. Customers can pay via bank transfer, cash or an online payment gateway. Splynx will always pair the payment with the customer’s account and create one payment transaction. A `- Credit` transaction is created in such case.

4. **When an administrator adds or removes money to/from the customer’s balance**.

5. **When a correction is needed, it’s also achieved with a transaction**.

Thanks to the transaction system, there is always a clear history as a way to track changes in the customer’s profile (`Customers → List → View (some customer id) → BILLING tab → TRANSACTIONS tab`).

---

The transactions table in `Finance → Transactions` displays all types of transactions related to the customers and contains the *Customer name/ID*, *transaction ID*, *date of transaction*, *type of transaction (debit or credit)*, its *description*, *price*, etc.

A table called **Totals** below the transactions list, displays the **type of transaction** (`Debit / Credit`), **the number of transactions** in total for each of type and **total amount of money** respectively.

  ![Transactions](./transactions.png)

A filter is located above the transactions table, it can be used to sort particular transactions, e.g. by **partner**, by transaction's **category**, by **type** or **period**.

  ![Filters](./filters.png)

Like all tables in Splynx, the icon <icon class="image-icon">![Export](export_icon.png)</icon> below the table can be used to export the table by means of printing, copying or saving the table in preferred file. The table can also be customized to view desired/preferred fields/columns with the use of <icon class="image-icon">![Columns](columns_icon.png)</icon> icon.

  ![Buttons](export.png)

  ![Columns](./columns.png)

Sometimes it's necessary to **correct customer account balance** due to offering of free services, credit, etc. We can do this by means of creating a new transaction and adding an invoice from the transaction. To perform these actions, navigate to `Customer → View Customer → Billing → Transactions`.

  ![Add transaction](./add_transaction.png)

When you click on `Add transaction` button, a window will appear with different fields and options for you to complete and select for the new transaction: the **Type** (`Debit/ Credit`), **Description**, **Quantity**, **Unit**, **Price**, **VAT%**, **Total**, **Category** (*service, discount, payment, refund, correction for customer's balance*, etc.), **Date**, **Comment**, **Period** values and **Add to invoice** option can be specified here.

  ![Add transaction form](./create_transaction_form.png)

Once a new transaction is created, it is also possible **to generate an invoice manually** by clicking on `Add Invoice from transaction` button in the `Billing → Transactions` tab. When clicking this button a window will appear where you can fill-in/select the following fields: **Description**, **Price**, **Period**, **Note** to the customer or **Memo** for you (if necessary).

  ![Create invoice](./create_invoice.png)

When the transaction is created, it is possible to **edit** or **delete** it with the icons in the *Operations* column <icon class="image-icon">![Buttons](./small_buttons.png)</icon> .

**Note:** If the transaction is created with `Add to invoice` option and it's related to invoice, the transaction by itself will be in read-only mode (you cannot edit or delete such transaction), however, the invoice can be edited accordingly.

![Read only](./read_only.png)

For more information about invoices, please navigate to the [Invoices manual](finance/invoices/invoices.md).
