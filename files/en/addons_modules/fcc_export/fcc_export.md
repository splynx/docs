FCC 477 export
==============

"FCC 477 export" is a Splynx module which is used to generate reports for Federal Communications Commission (USA) - [https://www.fcc.gov/](https://www.fcc.gov/).

To install "FCC 477 export" add-on please enter the command:

```bash
apt-get update
apt-get install splynx-fcc-export
```
or you can install it from Web UI:

Config → Integrations → Add-ons:

![fcc Web install](fcc_web_install.png)

After installation you need to generate Google API Key - [https://console.cloud.google.com](https://console.cloud.google.com)

![fcc Google get key 1](fcc_google_key_1.png)

![fcc Google get key 2](fcc_google_key_2.png)

![fcc Google get key 3](fcc_google_key_3.png)

![fcc Google get key 4](fcc_google_key_4.png)

![fcc Google get key 5](fcc_google_key_5.png)

![fcc Google get key 6](fcc_google_key_6.png)

![fcc Google get key 7](fcc_google_key_7.png)

![fcc Google get key 8](fcc_google_key_8.png)

Then you have to copy Google API Key in to the *Config → Module Lists → Splynx FCC → Edit:*

![Edit module list](edit_module_list.png)

![Add API key](add_api_key.png)

Configuration is complete and in menu “Administration” you will see a new icon:

![fcc icon](fcc_icon.png)

Now you need to sync addresses of your customers to “FCC Export” (it’s not necessarily, but it will be better for you, then “FCC Export” will be working faster. You can do it only once - when you use FCC for the first time):

![fcc Sync 1](fcc_sync_1.png)

![fcc Sync 2](fcc_sync_2.png)

There you have to choose "Partners" and click to "Load" button:

![fcc filters](fcc_filters.png)

If everything is correct, you will see the result and export buttons as on the screenshot below:

![fcc export data](export_report.png)
