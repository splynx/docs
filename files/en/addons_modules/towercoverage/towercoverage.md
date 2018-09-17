TowerCoverage Integration
=========================

Splynx has ability to use [Towercoverage](https://www.towercoverage.com/) to help you understand where your existing and potential clients are located. Towercoverage integration is a part of the [Self Registration add-on](addons_modules/self_registration/self_registration.md). That's why you have to install Self Registration add-on first.

After installation open add-on settings - _Config / Integrations / Modules list_

![Modules_list.png](Modules_list.png)
![Module_edit.png](Module_edit.png)

Enable Towercoverage:

![tower_enable.png](tower_enable.png)

**Add customer to Towercoverage** - when the customer registers via Self Registration, his coordinates will appear in the Towercoverage portal.

It is necessary to have Towercoverage account. You can register it here - [https://www.towercoverage.com/En-US/Home/Register](https://www.towercoverage.com/En-US/Home/Register)

![tower_register.png](tower_register.png)

Copy Towercoverage **Account Id** and **Account key** to Splynx.

![tower_API.png](tower_API.png)

![tower_API2.png](tower_API2.png)

Then, create Multi-coverage map (aka Multimap), open it and copy it's ID to Splynx. You can find ID of the Mutimap in your browser. It will be the last part of the URL.

![tower_multimap.png](tower_multimap.png)

Finally, enter the country code (where you create Multimap), and save the settings. You can see the list of country codes here - [http://wiki.towercoverage.com/wiki/79/api-country-codes](http://wiki.towercoverage.com/wiki/79/api-country-codes)

![tower_country.png](tower_country.png)

* * *

### Registration

When customer registers his account and Towercoverage integration is enabled, then **Street** and **City** fields are required to fill.

![tower_registration.png](tower_registration.png)

**Street** and **City** values entered by the customer will be transferred to Towercoverage. Towercoverage will try to translate **Street** and **City** to geographical coordinates and if it is possible - customer will be added to the Towercoverage portal.