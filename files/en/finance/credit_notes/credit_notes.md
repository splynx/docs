Credit Notes
==========

The **Credit notes**, as a completely new entity, was introduced in Splynx v3.2. A credit note is a document issued to indicate a return of funds in the event of a service cancellation, network equipment return, miscalculation of price/tax/discount in the invoice or other specified circumstances. Sometimes we can send a customer an invoice and then realize that we have overcharged them for certain goods or services. Instead of canceling the original or recreating a new invoice, which can confuse the customer in accounting processes, we can issue a credit note to correct the totals.

### Getting started

Credit notes are negative invoices designed to give a refund on part or all of the invoice amount.

Let's consider in details the *Credit notes* statuses and the actions that can be applied to:

| Status  | Description  |
| ------------ | ------------ |
| <icon class="image-icon">![](non_refunded.png)</icon> | the initial status of a new credit note. It means that the money has been refunded to customer's balance but customer has not yet physically taken money out from SIP. The `-Credit` transaction will be created. The specific amount of money will be added on customer balance|
| <icon class="image-icon">![](refunded.png)</icon>  | administrator sets this status when a customer withdrew money from the balance to the credit card or took the money physically. The `+Debit` transaction will be created. The specific amount of money will be withdrawn from the customer's balance. The new *Refund* payment with the negative sum amount will be created |
| <icon class="image-icon">![](deleted.png)</icon>  | it means that the credit note was **Marked as deleted**. In this case the credit note item remains visible in Splynx but the `-Credit` transaction will be removed. Some specific amount of money will be withdrawn from the customer's balance. Not to be confused with **Delete completely** action  |


| Action  | Description  |
| ------------ | ------------ |
| <icon class="image-icon">![](view.png)</icon> View  | to view the details of the credit note  |
| <icon class="image-icon">![](refund.png)</icon> Refund  | the administrator should choose this action when a customer withdrew money from the balance to the credit card or took the money physically |
| <icon class="image-icon">![](view_pdf.png)</icon> View PDF  | to view the credit note according to its template in Splynx |
| <icon class="image-icon">![](download_pdf.png)</icon> Download PDF  | to download the generated credit note pdf file |
| <icon class="image-icon">![](send.png)</icon> Send  | send the credit note to customer's email or portal. The specific template can be loaded or saved as new one in a new window  |
| <icon class="image-icon">![](edit.png)</icon> Edit  | used to edit the details of the credit note: note, status, link/unlink to the invoice etc.|
| <icon class="image-icon">![](delete.png)</icon> Delete  | can be applied to the credit note with `Non refunded` or `Delete` status. In case a credit note is in `Non refunded` status, two options are available to choose from:  **Marked as deleted** and **Delete completely**. If a credit note is in `Deleted` status, only **Delete completely** action can be applied to remove a credit note from the Splynx |
| <icon class="image-icon">![](edit_payment.png)</icon> Edit payment  | can be applied to the credit note with `Refunded` status. In new window we can change/add payment type, date, sum, comment, note/memo etc. |
| <icon class="image-icon">![](delete_payment.png)</icon> Delete payment  | The *Refund* payment will be remove and credit note status will be changed to `Non refunded`. The `+Debit` transaction will be re-created and the money will be returned to the customer balance |


**Example:**

Let's imagine that


All issued *Credit notes* can be found in `Finance → Credit Notes`. In case the module is not visible on the left sidebar of Splynx, you can enable it in `Config → Integration → Main modules`.

![](cred_note_location.png)

![](enable_disable_cred_notes.png)

With the use of a filter, it is possible to display credit notes by its **Number**, **Period** of time, **Partner** or **Status** (Any, Paid, Refunded, Non refunded, Deleted). Below the table of *Credit notes* you'll find a *Totals* table that displays a total of all credit notes by their status and the amount of credit notes in each status.

![](credit_notes_list.png)

To export the list of *Credit notes*, click on `Export` button, in a new window specify the **Period** of time, **Export type** (*CSV, PDF files in archive, One PDF file, Template, External handler*) etc.

![](export.png)

Alternatively, once you have selected the required *Credit note (-s)* in the table, click on `Actions` button and select the required option in drop down menu.

![](mass_actions.png)

### Creating credit notes




Поле status в Credit Notes имеет три состояния

not_refunded - по дефолту ставим 'not_refunded' это значит что деньги вернулись на ланс клиента, но он их еще не забрал у провайдера

refunded - когда клиент забрал деньги у провайдера, т.е. Вывел их с баланса

deleted - удалено


Credit notes in PDF format are fully customizable with [templates](configuration/system/templates/templates.md). You can create a new template using the different [variables](configuration/system/templates/templates_variables/templates_variables.md) or edit the build-in templates in `Config → Templates` (Type: **Credit Note PDF**). Then, open `Config → Company Information`, find the field `Credit Note PDF Template` and in drop down list choose the template that will be used by default in Splynx.



To choose the default template that will be used by Splynx


Use the Dashboard to adjust or refund finalized invoices with credit notes


Explore more ways to simplify your invoicing processes and make sending credit notes easier with

“Invalid price, must be greater than 0, if you need less than 0, create a credit note”, т.е. Если пользователь будет создавать инвойс с минусом, ему будет показана ошибка, что надо пойти и создать кредит ноту. (Если что поправьте текст)

Добавил в Messages аттачментом кред ноты




Related documents
