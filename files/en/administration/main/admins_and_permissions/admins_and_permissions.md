Administrators
======================

![menu](icon.png)

The administrators' table in *Administration* displays a full list of all administrators using Splynx, their admin logins, full names, roles, phone numbers and other information relevant to the administrator.

You can easily filter administrators to display the list by partners using the partners filter at the top right corner of the table.

![Administrators list](admin_list.png)

You can export via print, copy or saving the list of admins in PDF and/or CSV file formats by clicking on the export <icon class="image-icon">![ViewIcon1](view_icon1.png)</icon> icon below the table.

It is also possible to select the columns to be displayed in the table by clicking on the breadcrumbs <icon class="image-icon">![ViewIcon2](view_icon2.png)</icon> icon below the table.

### Adding an administrator
To add a new administrator, click on the `Add` button at the top right corner of the page, and a window will appear with the following fields to enter the relevant details for the administrator:

![Create administrator](create_administrator2.png)

* **Admin login** - type the login of the administrator;

* **Password** - type or generate the password of the administrator;

* **Profile photo/avatar** - click on the default profile image in order to change photo/avatar. In the new window you can choose one of the built-in avatars or the own photo. The custom image requirements are: file with *jpg/jpeg/png/bmp* extension, size is not more than 5MB. Zoom and visible image region selection functions are supported;

* **Two-factor authentication** - shows the status of two factor authentication for the administrator. The configuration can be made in [My Profile](my_profile/profile/profile.md) after the account has been created;

* **Full name** - specify the full name of the administrator;

* **Email** - specify the email address of the administrator;

* **Phone** - specify the phone number of the administrator;

* **Timeout** - specify the timeout interval for login sessions in seconds, leave the value on 0 to disable this function;

* **Role** - assign a role to the administrator: Administrator, Customer creator, Engineer, Financial manager, Manager, Super administrator, Technician or a [custom role](administration/main/roles/roles.md) you have created;

* **Router access (radius)** - specify the permissions to routers for the administrator: *None*, *Read*, *Write*, *Full*;

* **Send emails from my name** - enables/disables sending of emails from the administrators email; overrides system email configuration;

* **Partner** - select a partner to associate the administrator with;

* **Calendar color** - select a color to associate it with [Calendar](scheduling/calendars/calendars.md) events of the current admin account;

* **CashDesk** - *(available only when CashDesk add-on is installed)* the toggle switcher allows to process incoming payments via [Cashdesk](addons_modules/cashdesk/cashdesk.md) module for the current account.

### Editing an administrator
To edit administrators' details, click on the *Edit* icon <icon class="image-icon">![ViewIcon3](view_icon3.png)</icon> in the *Actions* column of the table.

![Edit administrator](edit_v3.2.png)

![Edit administrator](edit1_v3.2.png)

![Edit administrator](edit2_v3.2.png)

### Changing permissions for the new administrator
To change the permissions of an administrator, click on the *Permissions* icon in the *Actions* column. The window will appear, where you will be able to check and change all administrator's permissions.

![ViewIcon4](view_icon4.png)

![Change permissions](perm.png)

Main fields available for changes :

* **Dashboard**

* **Customers**

* **Leads**

* **Tickets**

* **Finance**

* **Messages**

* **Networking**

* **Scheduling**

* **Inventory**

* **Voice**

* **Tariff plans**

* **Administration**

* **Config**

* **Add-ons**

By clicking on each field you will be able to change particular permissions for different subcategories of that field.

![Subcategories permissions](perm2.png)

### Helpdesk

By clicking on the *Helpdesk* icon <icon class="image-icon">![ViewIcon5](helpdeski.png)</icon> in the *Actions* column of the table, we can change the scope of the administrators' access to tickets. The feature allows you to restrict administrators to only view/interact with tickets you wish to grant them access to.

This feature only restricts the administrator's access to tickets by your selection of the scope. It does not change any permissions you have granted to the administrator, it only narrows or broadens the scope of ticket the admin will have access to with the same permissions you have granted to the admin via the role assigned or the custom permissions you have selected for the admin.

![Helpdesk](helpdesk.png)

There are 3 scopes you can assign an administrator to:

* **Global** - selecting this option will give the administrator access to all tickets on the system. If the administrator is assigned to a specific partner, they will be able to see all tickets that belong to the partner. If the administrator is not assigned to a partner, they will be able to view all tickets.

* **Group** - selecting this option will limit the administrator to a specific group which you will have to specify upon clicking this option. If the administrator is not assigned to a partner they will be able to view all tickets assigned to the specific group (regardless of a partner). If the administrator is assigned to a partner, they will be able to view all tickets related to the group and partner (with or without partner allocation).

![Helpdesk](helpdesk1.png)


* **Restricted** - the administrator will only be able to view tickets that have either been created by or assigned to them.


### Deleting an administrator
To remove an administrator account from the system, click on the *Delete* <icon class="image-icon">![ViewIcon5](view_icon5.png)</icon> icon in the *Actions* column.

![Delete administrator](del1.png)

_____________________________________________________

It is possible **to view all the operations executed by each Administrator** by navigating to `Administration → Logs → Operations`. If you click on the *View details* icon in the *Actions* column of the table you will be able to see details of each operation:

![Operation details](operation_details.png)

There is a way to limit the access to information for admins in Splynx by selecting only one partner, so the administrator will only be able to operate with all information associated with one particular partner. Click on the  *Edit icon* <icon class="image-icon">![edit](view_icon3.png)</icon> in the *Actions* column and a window will appear, where it will be possible to choose one partner or the option *Any* to give the admin access to all the partners and their information on the system.

![Limit access per partner](limit_partner.png)

You can also change permissions for adding, editing or deleting partner(-s) for the particular administrator by clicking on the permissions <icon class="image-icon">![ViewIcon8](view_icon8.png)</icon> icon in the *Actions* column. In the window that will appear, click on the *Administration section*, and enable or disable the *Partner* section and choose additional permissions of the Partner you'd like to assign the administrator to.

![Edit permissions](del3.png)
