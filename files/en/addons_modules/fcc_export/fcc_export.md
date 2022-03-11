FCC 477 export
==============

**FCC 477 export** is a Splynx module used to generate reports for the *Federal Communications Commission (USA)* - [https://www.fcc.gov/](https://www.fcc.gov/).

The add-on can be installed in two methods, via CLI or via the Web UI.

To install the **FCC 477 export** add-on via CLI, the following commands can be used:

```bash
apt-get update
apt-get install splynx-fcc-export
```
To install it via the Web UI:

Navigate to `Config → Integrations → Add-ons`:

![Add-ons](0.png)

Locate or search for the `splynx-fcc-export` package and click on the install icon in the *Actions* column:

![fcc Web install](fcc_web_install.png)

The following window will appear for you to either cancel or confirm the installation, click on **OK, confirm** to begin the installation process:

![Addon](confirm.png)

After the installation process has completed, you need to generate a **Google API key** to use in the configuration of the add-on. Open a page of **Google Cloud Console**  - [https://console.cloud.google.com](https://console.cloud.google.com) and follow the steps below:

![fcc Google get key 1](fcc_google_key_1.png)

![fcc Google get key 2](fcc_google_key_2.png)

![fcc Google get key 3](fcc_google_key_3.png)

![fcc Google get key 4](fcc_google_key_4.png)

![fcc Google get key 5](fcc_google_key_5.png)

![fcc Google get key 6](fcc_google_key_6.png)

![fcc Google get key 7](fcc_google_key_7.png)

Once you've generated an **API key**, you have to copy it into the **Google API key** field of the add-on configuration. To achieve this, navigate `Config → Module Lists` locate the `splynx_addon_fcc_export` module and click on the Edit in the *Actions* column:

![Edit module list](edit_module_list.png)

![Add API key](add_api_key.png)

 <icon class="image-icon">![image](warning.png)</icon> **IMPORTANT**

 After that, it's necessary to investigate the following parameters:

- check if the required value is selected in the **Type of connection** field in **Services** of the necessary customers:

![image](type_of_connection.png)

- check whether a customer has filled out the next fields under **Information** tab: **Street**, **Zip Code** and **City**. Please note, in the **City** field, it's obligatory to add the state value as well, e.g. `Colorado Springs, CO`, where `CO` stands for state:

![image](set_state.png)

Once these steps are completed, a new section will appear in `Config → Administration` - **FCC Export**

![fcc icon](fcc_icon.png)

Now we can sync addresses of your customers to **FCC Export**:

<icon class="image-icon">![image](information.png)</icon> It’s not necessary to do it on a regular basis, but it will be better for you to improve the performance of the **FCC Export** module. Syncing addresses is only necessary when using *FCC export* for the first time on Splynx.

![fcc Sync 1](fcc_sync_1.png)

![fcc Sync 2](fcc_sync_2.png)

To run the export, simply select the desired **Partners** and **Tariffs**, then click on the **Load** button:

![fcc filters](fcc_filters.png)

If all configurations are correct, after you click the **Load** button, you will be presented with the results based on the criteria you set, with the option to export the results using the **Export** buttons below the tables:

![fcc export data](export_report.png)

In case of error, double check the error identifier to understand the reason issue and fix it (click on the example to see more information).

<details style="font-size: 15px; margin-bottom: 5px;">
<summary><b>Example</b></summary>
<div markdown="1">

![image](error1.png)

![image](error2.png)

</div>
</details>
