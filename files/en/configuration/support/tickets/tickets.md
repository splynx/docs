Tickets
=============
**_Config -> Support -> Tickets_**

![tickets icon](icon.png)

## TICKETS
In this module you can configure sender details for [ticket notifications](../ticket_notifications/tickets_notifications.md).

**Note that email sending must be configured under [Config -> Main -> Email](../../main_configuration/email_config/email_config.md) first.**

![Tickets](tickets.png)

**Send emails** - if this option enabled, Splynx will send notifications when ticket is updated;
**Send attachments to emails** - if this option enabled, attachments from ticket messages also will be send in notifications;
**Sender name** - name of sender;
**Sender email** - email address of sender. Email sending for this address must be configured under [Config -> Main -> Email](../../main_configuration/email_config/email_config.md);
**Copy email** - send all email copies to this address(if set);
**Send notifications to the admin panel(if online)** - if this option enabled, admin will get a notification when he is online on admin page.

## SCHEDULED AUTO-ASSIGNING
Let's imagine a situation when you(administrator "splynx") are lead-support engineer. You have another support engineer(administrator "admin") and you started to use shifts. Administrator "splynx" will work from 09:00 to 14:00 and all tickets will be assigned to him, and administrator "admin" will work from 14:00 to 23:00 and "splynx" admin doesn't want to re-assign all tickets to "admin" while he is not working. For this purpose we have a feature scheduled auto-assigning of tickets in some time period, and it can be configured to auto assign all tickets to administator "admin" from 14:00 to 23:00.

![Auto assign](auto_assign.png)

First of all some project must be created under [Scheduling -> Projects](../../../scheduling/projects/projects.md)
and some admin must be selected as default admin(all tickets will be assigned to him).

Then to make all tickets assigned to administrator "admin" you have to create a task [Scheduling -> Tasks](../../../scheduling/tasks/tasks.md) under your project what you are using in this module.

![Scheduled auto assign](task_example.png)

Select correct project, make some descriptions, assign to admin what will receive all tickets and the most important - enable "Is scheduled". On this screenshot it's scheduled from 14:00, for 9 hours so from 14:00 to 23:00 all tickets will be assigned to "admin" and after 23:00 "splynx" will receive all tickets again.

## TICKET ASSIGNMENT
Here can be configured admins for auto-assigning tickets.

![Auto assign](ticket_assignment.png)

**Admins available for auto-assigning tickets** - select admin or admins for auto-assigning;
**Sending notifications** - there are 2 options available:
  * Random admin(will be assigned to a random admin) - notification will be send only for admin who get a ticket(admin from available list) and ticket will be assigned to this admin;
  * All available admins(will not be assigned to anyone) - all admins will get notification but ticket won't be assigned.

## TICKETS LINK STATUS WITH ACTION
Configuration of ticket statuses. Custom statuses can be added/removed under [Config -> Support -> General ticket configuration -> Ticket statuses](../general_ticket_configuration/ticket_config.md)

![Ticket statuses](ticket_statuses.png)

**On creating** - set status "New" when ticket created;
**On opening** - when ticket was closed, and re-opened set status "Work in progress";
**On closing** - when ticket closed, set status to "Resolved";
**On customer reply** - when customer replied to a ticket set status "Waiting on agent";
**On agent reply** - when admin replied to a ticket set status "Waiting on customer".

## DEFAULT TICKET TYPE

Configuration of default ticket type after creation. Custom ticket types can be added/removed under [Config -> Support -> General ticket configuration -> Ticket Types](../general_ticket_configuration/ticket_config.md)

![Ticket default type](default_type.png)
