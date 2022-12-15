Pairing
=============

Before processing Payment statements, it is necessary to define first pairing parameters. The payment statement processing feature allows you reconcile payments receivable with invoices issued by pairing, so it can proceed multiple payments at once.

To configure Paring, click on `Config → Finance → Pairing`.

![Pairing](icon.png)


Here you will define parameters to pair Bank statement with Invoice or Proforma Invoice: Global #1 or # 2 parameters with Invoices or Proforma Invoices parameters.

As Global parameters #1 and #2 for pairing you can choose:

* None
* Customer ID
* Customer login
* Customer Birthday\ Firm ID

<icon class="image-icon">![image](note.png)</icon> You can create additional parameters in [Additional fields](configuration/system/additional_fields/additional_fields.md), and they will be shown in pairing fields as well.

In our example we selected Customer ID as a Global #1 parameter:

![Item global1 & global2](global.png)

As Invoice parameter for pairing you can choose:

* None
* Invoice number
* Invoice ID

![Invoice](invoice.png)

You can choose the following Proforma Invoice parameters:

* None
* Proforma Invoice number
* Proforma Invoice ID

![Proforma invoice](proforma.png)

After defining Pairing parameters, you can process payment (bank) statements. More information about payment statement processing can be found in the following tutorial page: [Payment statement processing](finance/payment_statement_processing/payment_statement_processing.md).
