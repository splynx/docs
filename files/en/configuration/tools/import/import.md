Import
======

When you are migrating to Splynx it is needed to import existing customers from your previous system into a new one. Manual import will take a lot of time and we have a tool to save this time.
Using the import tool you can import your data (customers, tariff plans, routers, leads, administrators, services, inventory items and products, etc) into Splynx in a few clicks. All what you need is a CSV file with your data.


### Customers import

To open this tool navigate to `Config → Tools → Import`:

![config_tools_import](config_tools_import.png)

We have a CSV file with the following structure:

![file_struct](customers_file_struct.png)

Let's import it:

![new_import](new_import.png)

select the **Customers** module and upload your file:

![customers_import](customers_import.png)

once file is loaded you need to define columns for import:

![select_columns](select_columns.png)

here you need to select appropriate column according to the columns of the file:

![define_columns](define_columns.png)

<icon class="image-icon">![INFO](information.png)</icon> **Tips for importing CUSTOMERS:**

* Fields with `*` sign are required. For the **Customers** module, the only required field is **Full name**;
* Email must be valid: e.g. `email@some.email` (invalid), `william.rieth@gmail.com` (valid);
* For the **Category** column there are only 2 available options: `person` or `company`. Strictly in lower case;
* For the **Location** and **Partner** columns **use only locations and partners IDs from Splynx, not names**;
* It's **not required** to import all columns from the file. You can select the `Do not import` option for a column and it will be ignored:

![do_not_import](do_not-import.png)

Once columns are defined, click on the **Submit** button at the bottom of this page. This will generate a preview for import. Click on the **Show preview and confirm** button to check the preview and confirm:

![preview](generated_preview.png)

If there are no rows with errors you can click on the **Confirm import** button and the import process will start in the background but when you have some errors and do not want to start the import again you can enable the **Ignore rows with errors** option at the bottom of this page and such errors will be ignored during the import and you'll be able to download the file with the elements where the errors occurred in order to reprocess them later.

![confirm](confirm.png)

Here is the result of a successful import:

![imported](imported.png)

Under **Actions** you can check the import summary and download this record from the list.

### Internet services import

Once customers are imported and internet plans are created we can import internet services for these customers. The flow is the same - select appropriate module, upload a CSV file, define columns, import.

![services_file_struct](services_file_struct.png)

In this file, the values in the **id** column will be ignored and in the **name** column we have customers' login values. To match records from the file with existing customers in Splynx you can use the email address, customer login or customer ID (the columns names are: **Customer email**, **Customer login** and **Customer** respectively).

<icon class="image-icon">![Important](warning.png)</icon> The required fields for services import are: **login**, **plan (tariff ID or name)** and **start date**.

![import_services](import_services.png)

![services_uploaded](services_uploaded.png)

We will match customers by login so instead of the **Customer*** field we will use the **Customer login** field:

![match_by_login](match_by_customer.png)

<icon class="image-icon">![INFO](information.png)</icon> **Tips for importing SERVICES:**

* For the **Plan** column use the tariff plan ID or plan name;
* **Start/end date** should be in the following format - `YYYY-MM-DD`;
* **Service login** is unique value;
* **IPv4 addresses** pool must be created before the import with IPs in `Networking → IPv4 networks`.

![services_preview](services_preview.png)

We have 1 error in services, because the customer is inactive:

![services_error](services_error.png)

You won't be able to confirm the import without the **Ignore rows with error** option enabled. To continue importing, but without the error in the record, enable the specified option and confirm.

![services_imported](imported_services.png)
