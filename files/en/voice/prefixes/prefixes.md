Prefixes
========

We added prefixes to Splynx to identify calls when the CDR is imported.

To add prefix(-es) manually, navigate to *Voice → Prefixes* and click on `Add` button located at the top right of the table:

![Add prefixes](add_prefixes.png)

![Create prefixes](create_prefixes.png)

The following parameters need to be specified:

* **Prefix** - Add the prefix using the pattern from *Examples*;

  You can use the phone pattern to match phone number groups.
  The pattern is created using special symbols.

  Examples can be found on the following page:
  [Examples.](voice/prefixes/example.md)

* **Destination** - Field to identify which type of destination this prefix will use, for example: international, fixed, mobile, etc;


* **Rate Type** - Select between Call, SMS or Data;


* **Category ID** - Select the category. The categories must be added earlier in *Voice → Categories*.


We can also import all the prefixes from a ***csv*** file:

Simply click on *Import* button located at the top right corner of the table:

![Add prefixes](import1.png)

Then upload the file and specify the necessary parameters:

![Import tool](import2.png)

* **File** -  click to upload the file from your computer;

* **Delimiter** - select a delimiter, default (recommended) = Auto detect;

* **Handler** - select between Base or other External handlers 

* **Column names in first row** - enable this option if the first row contains your column names;

* **Rate Type** - select between Call, SMS or Data;

* **Clear existing items** - enable this toggle to overwrite all the existing prefixes.

Also, it is possible to `Load default prefixes` for a predefined country:

![load](load.png)
