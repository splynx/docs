Ticket automation
=============
We developed this feature to make a bit easier life of admins who are working with tickets.

![icon](icon.png)

In this menu can be created some rules to automate work with ticket.

**Example:** I want to close ticket, and reply with [canned response](../ticket_canned_responses/responses.md) to a customer if ticket has status "Waiting on customer" more than 7 days.

I can achieve this goal by adding next rule:

![add rule](add_rule.png)

So if this rule created, all tickets with status "Waiting on customer" with time of last update more than 7 days will be closed automatically and customer will get email with text that this ticket was closed due to lack of activity more than 7 days(canned response with this text must be created first).

##### Be attentive with "Recurrently" option as if logic of rule is incorrect it can re-work all tickets, even "Closed".
