Processing
==========

Voice CDR processing is managed here. We can import a CDR to charge customers and print the register of calls within their invoice.

Within the processing module there are 4 menus, CDR Import, CDR Export, CDR History and CDR errors.


### CDR Import

To import a CDR, you simply just upload the file, select a delimiter, enable/disable first row contains column names, select the type and the handler(By default the Handler used is Base). Provider is not needed

![Upload](./upload.png)

Once the upload is complete, select the correct fields in every column, and then click on preview to check if all is working as expected.

![Import](./import.png)

If the system does not show any alert then click on import and check that all is accepted.

![Alert](./alert.png)

Then you will be able to view customer's calls, sms and data used on their statistics tab.

![Statistics](./statistics.png)


### CDR Export

It is also possible to export the same data that we insert/import to Splynx, to a new CDR, filtering by period and voice type.

![Export](./export.png)


### CDR History

In CDR history, we can check the register of imported CDR's, download them or delete them in case something was wrong or missing. If you delete a CDR the information imported will be also deleted.

![History](./history.png)

### CDR errors

After importing CDR's, this section will give you an overview of any errors that may have occurred while processing, with actions available to operate with the errors.

![Errors](cdr_errors.png)

For example:

An import was performed and completed with errors

![Error](cdr_error1.png)

You can review these error in `Voice / Processing / CDR errors`

![Error](cdr_error2.png)

In the Actions column, you can choose to view the errors, download the CDR, reprocess or delete the file. Below is an example of viewing an error:

![Error](cdr_error3.png)

You can interact with each entry within the error with the tools provided in the actions column. The tools in the actions column allow you to view detailed info about the error, update the CDR record, pair the CDR record to a service, reprocess or delete the record.

There could be a number of reasons for errors while importing CDR's and the tools provided in the CDR errors section are there to help fix these errors you may have encountered.

In this example we've encountered an error stating that the records have no service or customer associated.

An example of reprocessing an error:

1. Error reads that no service was found in each entry.

![Error](cdr_error3.png)

Select all entries to perform a bulk action:

![Error](cdr_reprocess1.png)

Click on the actions button on the top of the list and select pair:

![Error](cdr_reprocess2.png)

Enter the service ID to find, to use to pair to the CDR records and click on find:

![Error](cdr_reprocess3.png)
![Error](cdr_reprocess4.png)

Then click on the pair icon and confirm the action:

![Error](cdr_reprocess5.png)
![Error](cdr_reprocess6.png)

After confirming, each entry will be paired to the service and there will be no more errors.

![Error](cdr_reprocess7.png)


2. Error states no customer could be found with this number:

![Error](cdr_error3.png)

Navigate to the respective customer and ensure the number is present in his service and if it is not, please fill it in:

![Error](cdr_fix1.png)

![Error](cdr_fix2.png)

Navigate to `Voice / Processing / CDR errors` , view the errors:

![Error](cdr_fix3.png)

Select all entries to perform a bulk action:

![Error](cdr_fix4.png)

Click on the actions button on top of the table and select the reprocess option and confirm the action:

![Error](cdr_fix5.png)
![Error](cdr_fix6.png)

The system will then reprocess the CDR record and match the number to the customer. You will see that the total number of errors will decrease depending on how many entries were fixed in the reprocessing of the CDR.

Before the adding the number to the customer and reprocessing, there were 22 errors. After adding the number to the customer and reprocessing there are only 14 entires left to be fixed:

![Error](cdr_fix7.png)

The same process can be used again to fix the outstanding entries.
