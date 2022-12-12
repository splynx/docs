Site customization
==========

You can configure the default view of the Admin and Customer portal of your Splynx here. In particular, can be changed/applied the **Header**, **Footer**, **Custom CSS** and **Custom JavaScript**.

![site_customization](site_customization.png)

The default code for **Header**:

```
{% if context.companyInfo.file_logo %}<a class='navbar-brand' href='/admin/'><img src='{{ context.companyInfo.getLogoUrl }}' alt='Logo' class='img-responsive' style='max-width: 100%;max-height: 100%;'> </a>{% else%}<a class='navbar-brand' href='/admin/'>Splynx</a>{% endif %}

```

The default code for **Footer**:

```
Powered by <a href='https://splynx.com/' target='_blank'>Splynx</a>

```

After you make any changes in the code block, it is recommended to click first on `Preview in new tab`, check if the changes work correctly and then press **Save** button. The Splynx Dashboard page will be opened as a new tab where you can check the result.
If the page is corrupted, you still have an active tab with the **Revert all changes** button to undo the latest changes.

**Do not close this page until you can verify that everything is working correctly**.
