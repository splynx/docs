Tariff Settings
===============

We have introduced new settings on the tariff config, which allows to add included pricing and group pricing to the tariff, and also a preview tool for test. You also have to choose on which rate table will be based that tariff and in case we are managing buy prices(prices from our providers) we can add an increase percentage to define the final sell price.

On Tariffs Plans → Voice, click on the symbol ![ViewIcon1](./icon1.png) pricing to configure settings.

![Configure tariff](./configure_tariff.png)

It has 2 windows Groups and Preview.

![Groups and Preview](./groups_preview.png)

On the window Groups, we have 3 boxes. In the first one we have to set the Rate table and the Buy price increase in %.

![Rate](./rate.png)

On second one, we can add the included pricing.

![Included pricing](./included_pricing.png)

![Create pricing](./create_pricing.png)

* **Type** - Type of the pricing, could be Call, SMS or Data.


* **Categoires** -  We have to choose to which categories are this price included. We should create first categories and prefixes.


* **Days** - Select days of the week included.


* **Unlimited** - Enable if is not limited by minutes.


* **Included amount** - Select amount of time for calls(in seconds, minutes or hours), nº of messages or amount of data(in B, KB, MB or GB).


* **Time** - Period when this pricing included is applied.


And on the last one we can configure pricing groups. For example if we want to manage any category in different way or if we want to add something specific.

![Add pricing group](./add_pricing_group.png)

![Create group](./create_group.png)

* **Title**  - Title of the Group pricing.


* **Type** - Type of the pricing, could be Call, SMS or Data.


* **Categoires**  -  We have to choose to which categories are this price asigned. We should create first categories and prefixes.


* **Days** - Select days of the week included.


* **Time** - Period when this pricing included is applied.


* **Operation** - + % to buy, + % to sell, Establish, Tarification Step, First tarification.


* **Value** -  + % to buy, + % to sell → increase percentaje of price. Establish, Tarification Step, First tarification → Price.
              

####Preview Tool

We can set an example of comsuption to test if our setting and config are working well.

![Preview Tool](./preview_tool.png)

The preview is showing that is included only 6000sec(100min), and as we have set 7000sec, the other 1000 seconds will be charged in base to the table, so total price is 1'17, that correspond to out config in the Rate table selected.