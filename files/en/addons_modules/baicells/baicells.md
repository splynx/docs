Baicells LTE
============

Baicells LTE is a Splynx add-on which is supporting [Baicells](http://baicells.com/) equipments. Using this software you can:

* add Baicells-system;
* create and manage SIM-cards, which use Baicells-system;
* assign SIM-cards via customer's internet services.  

**Attention!** This add-on is prepaid, so if you haven't bought it and install, you will only see a message as on the screenshot:

![Selection_029.jpg](Selection_029.jpg)

To install "Baicells LTE" add-on please enter the command:

```bash
apt-get update
apt-get install splynx-baicells-lte
```
or you can install it from Web UI:

Config -> Integrations -> Add-ons:

![1.png](1.png)

![2.png](2.png)

![3.png](3.png)

After installation in menu _Networking_ you will see new icons: _LTE systems_ and _LTE Configs_. First of all, you should create a new LTE system:

![Selection_035.jpg](Selection_035.jpg)

![Selection_036.jpg](Selection_036.jpg)

![Selection_037.jpg](Selection_037.jpg)

After you've created LTE system, you can create SIM-cards for that system. In order to do this you should go to _Networking → LTE Config_ and create cards (manually or using import):

![Selection_038.jpg](Selection_038.jpg)

![Selection_039.jpg](Selection_039.jpg)

![Selection_040.jpg](Selection_040.jpg)

![Selection_041.jpg](Selection_041.jpg)

And now you can create Internet service for customers. Open _Customer → Services_ and create new Internet service:

![Selection_042.jpg](Selection_042.jpg)

![Selection_043.jpg](Selection_043.jpg)

![Selection_044.jpg](Selection_044.jpg)

When customer uses LTE IMSI, you can check IMSI list in special bookmark:

![Selection_045.jpg](Selection_045.jpg)

**Troubleshooting!** If something is wrong with add-on, please, check WebHooks inside Splynx settings menu: _Config → Hooks,_ it should be enabled:

![Selection_046.jpg](Selection_046.jpg)
