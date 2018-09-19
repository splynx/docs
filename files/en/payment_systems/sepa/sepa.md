SEPA debit orders
=================

SEPA is a European standard for bank payments. You can install SEPA add-on and charge your customer via Direct debit orders.

**1\. SEPA Installation**

The Installation is pretty simple:

```bash
apt-get update
apt-get install splynx-sepa
```

or In Splynx you can select _Config → Integrations → Addons_

![111.png](111.png)

find _splynx-sepa_ and click install

![112.png](112.png)

**2\. Configuration**

Open Config→Integrations→Modules list→Splynx SEPA Add-on and fill in selected fields

![113.png](113.png)

where: ID prefix - it's bank contact ID prefix : ES12500 example (before company VAT ID)

**Customer’s IBAN** can be set in the customer profile (see below)

![114.png](114.png)

**3\. Generate the XML file for the bank.**

Open _Finance/Invoces/_ and click on the _Charge_ button

![115.png](115.png)

![116.png](116.png)

![117.png](117.png)

By opening a second tab _Export history_ you can see all errors in generation or download ready XML files.

In this example we have an error:

![SEPA_3.png](SEPA_3.png)

By clicking on icon _Download_ we can get an error description file and open it in Notepad:

![SEPA_4.png](SEPA_4.png)

In our example it says one of our customers has empty IBAN in his information tab. After fixing it and re-submitting the export we will find the correct status in Export history:

![SEPA_5.png](SEPA_5.png)

SEPA XML file is ready for downloading and sending to Bank for further processing and charging subscribers:

![SEPA_6.png](SEPA_6.png)

The line `<ReqdColltnDt> 2017-06-01</ReqdColltnDt>` says when Bank should charge the customer. By default we put there the date of XML generation. It can be changed in XML file before sending.

**4\. Mark invoices as paid**

![118.png](118.png)

![119.png](119.png)

My file contains “_Creating payment for invoice 201801000001: ok!_”

Check invoices

![121.png](121.png)

**5\. SEPA - process the return file from bank with non-payers**

Sometimes customer doesn't have funds on his bank account. In that case Bank sends you XML file back with returns. It will contain data about customers Bank was not able to charge. You can import this file to Splynx as well, and then paid invoices of non-payers will become unpaid again. So you can charge them next month and include the fee for failed charge.

The handler to choose is SEPA XML returns:

![SEPA_last.png](SEPA_last.png)