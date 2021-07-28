3CX add-on
========

*3CX* is the add-on module designed for the integration your Splynx with [3CX service](https://www.3cx.com/call-center/crm-integration/) via the server-side CRM integration engine and its own API. The add-on creates the API key/secret with the necessary permissions and helps to generate the XML configuration file with specific structure inside for integration purpose.

To install the add-on use one of the two methods: via CLI on the Splynx server or via the Splynx Web UI.

To install the add-on via CLI, the following commands can be used:

```bash
apt-get update  
apt-get install splynx-3cx
```

To install the add-on from the Web UI:

Navigate to `Config → Integrations → Add-ons`:

![](img_000001.png)

Find there the "splynx-3cx" add-on and click on the install icon in the *Actions* column of the table

![](img_000002.png)

Then, click on the "OK, confirm" button to begin the installation process

![](img_000003.png)

Once the installation process has completed, all configurations for the add-on can be found in `Config → Modules → List`, simply click on the necessary icon of the module and you will be able to change settings of the add-on

![](img_000004.png)

## Using the 3CX module

After add-on installation in your Splynx system will be created [API key/secret](administration/main/api_keys/api_keys.md) (unsecure access unabled) with such permissions:

|Customers|
|:-----------:|
|**Customer:** Add, View; **Customer notes:** Add|

|CRM|
|:-----------:|
|**Leads:** Add, View; **Leads notes:** Add|

![](img_000005.png)

![](img_000006.png)

And, in `Config → Integrations`, you can find the *3CX* section with the link to download the generated `splynx.xml` file

![](img_000007.png)

![](img_000008.png)

![](img_000009.png)

Use any text editor to open the downloaded `splynx.xml` file, specify the necessary values, such as your Splynx domain (`[Domain]`), API key/secret (`[ApiKey]` / `[ApiSecret]`). and save the changes. Use this XML file for CRM integration procedure.



Let's perform the first time configuration of the 3CX system:

1. [Sign up](https://www.3cx.com/ordering/pricing/) on the 3CX web page with preferred price choice

2. Choose the location for the 3CX system, write down your license key and follow the required installation steps. Open the IP of the machine 3CX is installed on followed by port 5015 in a browser, e.g. https://10.172.1.88:5015. The 3CX Web Configuration Tool guides you through important network and security settings.

Check the following links for more details:

[Installing 3CX using ISO (Debian)](https://www.3cx.com/docs/manual/configuring-your-pbx/)
[Installing 3CX on Windows](https://www.3cx.com/docs/manual/phone-system-installation-windows/)
[Using Hyper-V to host your 3CX](https://www.3cx.com/docs/installing-microsoft-hyper-v/)
[Hosting 3CX on Google Cloud](https://www.3cx.com/docs/hosted-pbx-google-cloud/)
[Hosting 3CX on Amazon AWS](https://www.3cx.com/docs/cloud-pbx-amazon-aws/)
[Hosting 3CX on Amazon Lightsail](https://www.3cx.com/docs/hosted-pbx-amazon-lightsail/)
[Hosting 3CX on Microsoft Azure](https://www.3cx.com/docs/hosting-pbx-phone-system-microsoft-azure/)
[How to access for Self Hosted Instances via SSH](https://www.3cx.com/docs/self-hosted-instances-ssh/)

![](img_000011.png)

![](img_000012.png)

3. Once 3CX is installed, open the 3CX Management console via `https://<domain/IP>:5001`  

![](img_000013.png)

![](img_000014.png)

4. Click on `Settings → CRM Integration`, upload your XML file to 3CX system, set up the required integration settings


![](img_000015.png)

![](img_000010.png)

More information about the integration can be found on the following link: https://www.3cx.com/docs/crm-integration/

5. Install [iOS](https://apps.apple.com/us/app/3cx-communications-system/id992045982), [Android](https://play.google.com/store/apps/details?id=com.tcx.sipphone14) or [Windows](https://www.3cx.com/user-manual/installation-windows/) app, navigate to your [3CX Web Client](https://www.3cx.com/user-manual/web-client/) via `https://<domain/IP>/webclient`, log in using the extension number and password from your email letter and click on *Activate your 3CX Browser Extension*, in the top left-hand corner of the Web Client click *Allow Notifications* to enable desktop notifications, you will see the blue phone icon in the extensions bar in your browser. Click on the icon to open the Browser Extension pop out window.
Now you can quickly and easily make and receive calls from your desktop without needing to open the full Web Client. Moreover, you can call to customers directly from Splynx.

![](img_000016.png)

![](img_000017.png)
