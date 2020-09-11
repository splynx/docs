Tickets
=======

The Splynx ticketing system has been designed to empower technicians and satisfy customers by means of integration and automation. We welcome you to your in-house support platform.

To help understand both perspectives, let's separate our ticketing system into two sections or views, one being an administrative perspective and the other, a customer experience.

**ADMINISTRATORS**

**Dashboard**

![Dashboard](tickets_dashboard.png)

The ticketing dashboard shows the following sections:
* Status of all current/open tickets on the system.
* General and per-agent statistics of all your support agents
* Live log of recent activities of tickets.
* Quick reference to the tickets table of the administrator currently logged into the system

Administrators are able to create the tickets in 3 ways:
1. From `Tickets > Dashboard` and clicking **Create** in the top right corner of the page.

![Create_ticket](admin_create_1.png)

2. Directly from a customer's profile by clicking on the **Support** button and selecting **Create** from the drop-down menu.

![Create_ticket](admin_create_2.png)

3. Within the list of new & open tickets `Ticket > List new & open`, there is a button located at the top right of the page.

![Create ticket](tickets_new&opened.png)

After clicking on the "create ticket" button anywhere in the system, you will be redirected to the *'Create ticket'* window where the following fields have to be completed together with a body for the ticket:

![New ticket](createnew_ticket.png)

* **Customer** - which customer to open the ticket for
* **Assign to** - the administrator the ticket will be assigned to
* **Subject** -  a relevant subject of the ticket, usually pertaining to the reason for opening the ticket
* **Priority** - the urgency of the ticket which can be set to low, medium, high or urgent
* **Status** - the state of the ticket currently which can be set to New, Work in Progress, Waiting for Customer, Waiting on agent, Resolved
* **Group** - the ticket can be filtered to a specific group of admins depending on the nature of the ticket
* **Type** - the reason for creating the ticket which can be set to Question, Problem, Incident, Feature request, Lead
* **Message** - the body of the ticket can be typed here
* **Attachments** - used to attach files to the ticket

It is possible to add a canned response to the message body to optimize the productivity of admins.

In Splynx we have added the ability to configure canned responses to minimize typing and save on time to ultimately create efficiency. To populate the body of the ticket with a canned response, simply click on the arrow highlighted below and choose a response from your list of canned responses:

![Canned response](canned_response.png)

New canned responses can be added by clicking **Add response** button

![Canned response](canned_add_1.png)

or in `Config > Ticket canned responses`.

![Canned response](canned_add_2.png)

The  *Hidden* <icon class="image-icon">![Hidden](./hidden.png)</icon> toggle allows you to hide tickets from a customer.

You are also able to create [new fields](customer_management/custom_additional_fields/custom_additional_fields.md) in the tickets module. More information about **adding custom fields** is available here - [Additional fields](configuration/system/additional_fields/additional_fields.md). Remember, that in order to see the new field in the main table, you should enable it by clicking on the breadcrumbs <icon class="image-icon">![Add](add.png)</icon> icon below the table.

Once the ticket has been created, it will be visible in the `New and opened tickets` table. Here you can **filter tickets** by *Condition, Period, Customer/Lead ID, Group, Partner, Type or Type*. We've added the capability to search for specific text with the _Text search function_ or the customers full name in the _Find Filter_ field. You can also choose the list of new and opened tickets to view filtered by the administrator assigned or the status of the tickets.

![New & Open](tickets_filter.png)

Depending on the layout you have chosen to view new and opened tickets with the layout <icon class="image-icon">![layout](tickets_layout.png)</icon> icons, you are to reassign, change the status of, change the priority or the type of the ticket, directly from the tickets table.

![Edit ticket](edit_ticket.png)

The ticket working area is divided into 3 parts: *ticket properties, action buttons, and a messages area*.

![Working area](ticket_workarea.png)

* In the properties we can reassign the ticket to the specific administrators, change status, prioritize the work, assign to a specific group and set the ticket type.  We also oversee the Customer's information like Name, Email, Phone number, and recent tickets.

## Ticket properties section parameters:

* **Customer/Lead** -  changes the customer this ticket has been open for
* **Assigned to** - reassign the ticket to a specific administrator
* **Subject** -  change the subject of the ticket
* **Priority** - change the urgency of the ticket
* **Status** - change the current state of the ticket
* **Group** - change the group of administrators this ticket is available to
* **Type** - change the reason for the tickets
* _Show more options_ - this option will either hide or display additional fields of tickets

* The action buttons allow us to add a note, reply or forward the answer, check all ticket activities and schedule the task for an engineer directly within the ticket.

## Tickets actions section parameters:

* **Reply** - used to respond to a message or add a message to the conversation, this button opens up the body area of the message for you to type or insert content from canned responses.
* **Add note** - this button opens a typing area to add a note to the ticket that is not visible to the customers
* **Forward** - this button opens the "Cc" and "Bcc" fields for forwarding the response as well as ticket content to another email address(s)
* **Actions** - this is a drop-down list of functions namely:
_Show Activities_ - to view all activities executed to/within the ticket
_Show all files_ - provides a list of all attachments within the ticket
_Create task_ -  integration to the scheduling module, this button allows you to create a task pertaining to requests made within the ticket
_Merge ticket_ - allows the merging of the current ticket with another
_Close ticket_ - marks ticket status as resolved and the ticket is moved into the list of closed tickets

Below is a quick look at the task creation page after clicking the create task option

![Schedule tech](schedule_task.png)


Once a ticket has been resolved, you can change the status on *closed* and close the ticket or press the **Update and Close** option of the update button immediately after adding a response to the ticket. All closed tickets are shown in `Tickets → List of closed`.

![List closed](closed_list.png)

------

**CUSTOMERS**

Your customers can also create tickets in three ways:

1. By sending a query to your incoming email (*support@yourdomain.com*), and the ticket will be created automatically on the system. Incoming mail configuration can be found [here](configuration/main_configuration/incoming_mail.md).

2. By creating a ticket from Customers Portal in `Tickets > Create`

![Tickets portal](portal_ticket.png)

* **Subject** -  a relevant subject of the ticket, usually pertaining to the reason for opening the ticket
* **Priority** - the urgency of the ticket which can be set to low, medium, high or urgent
* **Message** - the body of the ticket can be typed here
* **Attachments** - used to attach files to the ticket

Once the ticket is created it is possible to view or close it by using the following icons <icon class="image-icon">![Add](icons.png)</icon> within the tbale/list of new & opened tickets:

![Tickets portal](portal_list_of_tickets.png)

3. By creating a ticket from Splynx mobile self-service app.

![Tickets mobile app](app_ticket.jpg)

There are a number of elements that can be automated within the ticketing module to improve efficiency and speed up engagement. These automation rules can be set up under `Config / Support / Ticket automation`
More information about **tickets configuration** can be found here - [Support](configuration/support/support.md).

When tickets are opened by either the customer or administrator, notifications are sent to each other via email. Depending on the template you are using for tickets, tickets may include the body of the ticket and this can ultimately create convenience, as customers/administrators can respond directly from the email to respond to the ticket. If the template does not include the body, customers/administrators are able to log into their respective portals by means of a link included in the ticket notifications.

## List of new & opened

This is where you will find a list/table of all new and opened tickets. For administrators part of the support team and designated to answering customer queries it is their working space within the ticketing module.

![Tickets](new&opened.png)

Above the table of new & opened tickets, we've added a quick filter to change the tickets being displayed. You can choose to display tickets assigned to a specific administrator, unassigned tickets or all new and open tickets in the system. You may also filter tickets by status once the source of tickets to display has been selected. For ease of access "Refresh" and "Create ticket" buttons have been added alongside the button to hide or display the main filter menu.

![Tickets](topfilter_tickets.png)


The main filter menu can be found on the right side of the page when the filter button  <icon class="image-icon">![filter](filter_icon.png)</icon> is clicked. This filter can be used to specify which tickets to view based on the selections in the fields provided.

![Tickets](mainfilter.png)

**Find filter parameter descriptions**

**Full name** - search for tickets by the customers full name<br>
**Condition** - search in the list of open, closed or all tickets<br>
**Period** - search for tickets within a specific time period<br>
**Customer / Lead ID** - search for tickets via the Splynx customer ID or lead ID<br>
**Group** - search for tickets in the list of tickets for the specific group of administrators<br>
**Partner** -  search for tickets of a particular partner<br>
**Type** - search for tickets of a specific type or reason for opening<br>
**Priority** - -search for tickets marked with a specific urgency<br>
**Text search** - search for tickets containing specified Text<br>

After selecting the desired data to display in the provided fields simply click _Apply_ to search for these tickets or _Clear filters_ to clear the filter fields and display all/assigned new & opened tickets.

The layout of the new & opened tickets table can also be changed with two options <icon class="image-icon">![layout](tickets_layout.png)</icon>. The first formats the list into a _Table view_ and the second into a _Card view_.

## Table View

![Tickets](tablewview.png)

## Card view

![Tickets](cardview.png)


Deciding which view to use is a matter of personal preference. Each view has its own capabilities too. Namely:

**Table view**

Displays more details and has an "Actions" column limited to viewing the ticket, marking it as read or unread or closing the ticket. Please keep in mind that because this is a table, it can be customized to view more/less data like all tables in Splynx and the data can also be export with the use of the <icon class="image-icon">![layout](table_icons.png)</icon> icons.

**Card View**

Displays fewer details but has quick access to function like reassigning tickets to admins or groups and changing the priority, status or type of the ticket.


## List of closed

Here is where you will find the list/table of all closed tickets in the system.

![Tickets](closedtickets.png)

Above the list/table is a filter to use when viewing closed tickets.

![Tickets](closed_filter.png)

You are able to filter tickets by a specific period and customer ID, assigned to a specific administrator, unassigned or all closed tickets.

The table/list of closed tickets have the same functionalities of the list/table of the new and opened tickets list/table.
You are able to select the layout just as with the new & opened list/table and perform certain functions.

In the closed tickets section, however, options to re-open tickets or move them to trash become available:

![Tickets](closedtable_functions.png)


## Trash

Here you can find all tickets moved to trash from the list/table of closed tickets.

![Tickets](trash.png)

This list can also be filtered to view the content of a specific time period and customer ID, of a specific administrator, unassigned or all tickets in the system.

![Tickets](trash_filter.png)

The trash tickets list/table layout can also be customized to display tickets in a table or card format and has functions in the actions column of the table view to either view, restore or permanently delete tickets.

![Tickets](trash_actions.png)
