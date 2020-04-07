CDR processing
==========

You can import a CDR(in .csv format) for charge the customer and print in his invoice the register of calls, messages or data.

Behind the processing menu there are 4 other pages, CDR Import, CDR Export, CDR History and CDR errors.
![Dashboard](dashboard_voice.png)

### Import CDR

To import a CDR file you have to upload this file(in .csv format), select delimiter, enable/disable first row contains column names, select voice type(call, messages, data or mixed) and select handler("Base" handler by default). Provider selection can be missed.

*NOTE! Almost every our client has different type of CDR files, so if Splynx base handler can't process your file because of another format you should ask Splynx Support to develop a custom handler for your type of CDR files. You should send 2-3 CDR files as an example and full description(what field should be imported, what field can be missed etc.). Handler development takes few business days and it's absolutely free*

![Upload](import_description.png)

Once is load, select the correct field in every column, and then click on preview to check if all is working fine.

![Import](./import.png)

If the system don't shows any alert then click on import and check that all is accepted.

![Alert](./alert.png)

Then customers on statistics will be able to see their calls, sms and data used.

![Statistics](./statistics.png)


### Export CDR

It's also possible to export the same data that we introduce to splynx to a new CDR, filtering by period and voice type.

![Export](./export.png)


### History CDR

In the history, we can check the register of CDR imported, dowload them or delete in case that something was wrong or missed. If delete the CDR the information impoted will be also deleted.

![History](./history.png)
