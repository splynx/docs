Auto processing
==========

The Voice auto CDR processing is managed here. We can import a CDR's to charge the customer and print the register of calls in his invoice.

The process is similar to Voice/Processing/CDR import, but here we can import many CDR's together.

To import CDR's you need to go to the source and configure "Import data source"

![Import](1.png)

![Import](9.png)

![Import](2.png)

![Import](8.png)

Here you need to set:

  * Title - any name.

  * Data source type - select type from drop-down menu.

    * SFTP - if you select "SFTP" then you will need to enter RSA private key

    * FTP - if you select "FTP" then you will need to set the same parameters as for "SFTP" but without RSA key

    * Local - if you select "Local" then you will need to set only Title and Folder path

  * Folder path - set your path to folder

  * Host - set your host IP address

Now you need to go to the Config / Voice / Auto CDR processing and create Import data source

![Import](3.png)

![Import](4.png)

Here you can set:

  * Title - any name.

  * Import data source - select data source from the drop-down menu

  * File name pattern - Regex for filtering file names (uses pcre syntax):
    Will process all the files that have pattern entrances in a file name.

[Examples](voice/auto_cdr_processing/examples/examples.md)


  * First row contains column names - turn it on if the first row in your CDR's contains columns names

  * Delimiter - select a delimeter from drop-down menu

  * Type - select from drop-down menu type of data what you would import

  * Data unit - (If type = Mixed or Data) select from drop menu

  * Voice provider - select a provider from the drop-down menu (if you have it)

  * Import handler - select your handler from the drop-down menu

  * Launch time interval - How often an auto processing will be running

  * Enable - In case it is on, an auto processing will be running every 'Launch time' interval.

After that Auto CDR processing is added, you can run it manually, go to the Config / Voice / Auto CDR processing and press "Run import" button.
In case something is wrong, you can see it in Auto CDR processing history, for this press "History" button, and you will see errors, here you can also Reprocess the errors:

![Import](5.png)

![Import](6.png)

![Import](7.png)
