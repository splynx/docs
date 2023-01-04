Ticket automation
=============
We've developed this feature for the convenience of administrators who deal with tickets. With automation, the admin can easily perform their work and achieve better results.

![icon](icon.png)

In this section, rules can be created to automate operations with tickets.

**Example:** We want to close tickets automatically, and reply with a [canned response](configuration/support/ticket_canned_responses/ticket_canned_responses.md) to a customer if the ticket has a status of "Waiting on customer" for more than 7 days.

We can achieve this goal by adding the following rule:

![add rule](add_rule.png)

If this rule is created, all tickets with a "Waiting on customer" status with a period of the last update being more than 7 days ago, the ticket will be closed automatically and the customer will receive an email with the text that this ticket was closed due to a lack of activity for more than 7 days (a canned response with this text should be previously created).

<icon class="image-icon">![image](warning.png)</icon> **Be attentive with the "Recurrently" option because if the logic of the rule is incorrect, it can reply to all tickets, even to "Closed".**
