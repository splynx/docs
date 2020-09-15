Auto processing
==========

The Voice auto CDR processing is managed here. We can import CDR's to charge customers and print their register of calls on their invoices.

The process is similar to the [Voice -> Processing -> CDR import](voice/processing/processing.md), but here we can import multiple CDR's together, automatically.

Firstly, to import CDR's you need to navigate to **Config -> Voice -> Import data source** and add a CRD data source location.

![import data source](icon_data_source.png)

Simply click on the *Add* button located at the top right of the table:

![Add](1.png)

The following types of data location types can be used:

* **SFTP**
* **FTP**
* **Local**

Adding an SFTP data source:

![SFTP](9.png)

Adding an FTP data source:

![Add source](add_source.png)

Adding a local data source:

![Add local source](local_storage.png)

We will use a local storage/data source as an example.

The following parameters need to be configured to add data sources:

  * **Title** - provide a relevant name for the data source location;

  * **Data source type** - select a type from the drop-down menu:

    * SFTP - if you select "SFTP" then you will need to enter a RSA private key. CDR files are located on a FTP server;

    * FTP - if you select "FTP" then you will need to set the same parameters as for "SFTP" but without a RSA key. CDR files are also located on a FTP server;

    * Local - if you select "Local" then you only need to set the Title and Folder path. CDR files are located on the Splynx server;

  * **Folder path** - set your path to the folder with the CDR files;

  * **Host** - set your host IP address;

  * **Port** - if the data source type selected is FTP or SFTP - specify the port to connect to FTP here;

  * **Login** - if the data source type selected is FTP or SFTP - specify the login to connect to FTP here;

  * **Password** - if the data source type selected is FTP or SFTP - specify the password to connect to FTP here.

Once the data source is added, you can test the connection (if FTP or SFTP is configured), edit the data source or delete it using the buttons provided in the *Actions* column as depicted below:

![list](list_of_sources.png)

**When using a FTP server as a CDR data source - make sure that connection is successful.**

**In case of using a local storage/data source (on Splynx server), make sure that the folder with the files has the correct permissions and "splynx" is the owner**

We have added local storage of CDRs named "Local storage test CDRs" and we will use it in a auto CDR processing configuration.

We will use the following format of CDR files(it is a very simple format so we can not use custom handlers to parse files):

![File format](test_cdr_format.png)

**Very important note to take is that each file must have a unique name, because Splynx checks the name of the file and if the file with the same name is imported to Splynx, after that file was updated - Splynx will not re-load the updated file, as the file with this name was already imported.**

Once we have added a data source, we can then navigate to **Config -> Voice -> Auto CDR processing** and add an auto processing unit:

![icon processing](icon_processing.png)

Let's create an auto processing entry by clicking on the *Add* button located at the top right of the table:

![Add](3.png)

![create auto processing](add_auto_processing.png)

The following parameters need to be specified here:

  * **Title** - provide a relevant name for the entry;

  * **Import data source** - select a data source from the drop-down menu(in our case we used the local storage);

  * **File name pattern** - Regex for filtering file names (uses pcre syntax):
    This will process all the files that have pattern entrances in the file name. [Examples](voice/auto_cdr_processing/examples/examples.md). We have all the CDR file names starting with "test-cdr"(eg. test-cdr-2020-08-01.csv);

  * **Import from file modification date** - specify the file modification date for the import. In our example, to import only files for August 2020, we've specified 2020-08-01 00:00:00, but if the file with calls for July was created on 2020-08-01 00:00:01, it will be also imported;

  * **First row contains column names** - enable this option, if the first row in your CDR's contains the columns names;

  * **Delimiter** - select a delimeter from the drop-down menu;

  * **Type** - select a type from the drop-down menu, relevant to the data you would import. In our case it's only calls;

  * **Voice provider** - select the necessary voice provider;

  * **Import handler** - select your handler from the drop-down menu;

  * **Launch time interval** - How often the auto processing will executed;

  * **Max processing time** - max time that Splynx will spend to process one file. If processing of the file takes more than the specified value - it will be ignored;

  * **Enable** - when enabled, an auto processing unit will be executed every 'Launch time' interval, and if disabled - you will have to run it manually;

As we have a strict and simple format of files, we have specified columns regarding to our file format. If you are using a handler - columns configuration can be ignored.

After Auto CDR processing entries have been added, you can run it manually(to test how it works, after successful test results, the auto import can be enabled to do all this stuff automatically(described at the end of this document)),  from **Config -> Voice -> Auto CDR processing**, simply click on the "Run import" button. Before running an import, we recommend checking the preview of files that will be imported:

![files preview](files_preview.png)

We have 4 files to be imported and all is correct, so we can start the import:

![run import](run_import.png)

After the import has completed, we can check the results by clicking on the "History" button:

![history](import_result.png)

In our case, the first file was fully processed and all the rest completed with warnings. Simply place the mouse cursor on the "Warning" message under each file to see the number of processed/unprocessed rows:

![warnings](warnings.png)

We can click on the "Show warning rows" button, to view more information about the warnings:

![show warnings](show_warning_rows.png)

As we can see, some calls can't be placed to the correct service with the source number = 28449988. To fix this, we have added a voice service for the customer with the number = 28449988 and direction = outgoing. Let's reprocess the warnings:

![click reprocess](click_reprocess.png)

![reprocessed rows](reprocessed.png)

After reprocessing, we have successfully imported all files. Now we can enable the auto processing to grab new files from the data source, once a day. So Splynx will automatically grab and import files with calls:

![enable](enable.png)
