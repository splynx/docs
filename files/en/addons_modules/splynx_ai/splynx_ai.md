Splynx AI
================================
The Splynx AI add-on, based on artificial intelligence, is intended to evaluate the quality of feedback on support tickets. Previously, the option to [grade tickets](administration/reports/ticket_reports/ticket_reports.md) was manual. This feature has been automated by teaching neural networks to evaluate the support work considering various parameters in closed tickets.

Together with the [Ticket feedback add-on](addons_modules/ticket-feedback/ticket-feedback.md), this will give you a powerful tool to analyze and improve the quality of your customer support service on a single report.

## Installation

Navigate to *Config → Integrations → Add-ons* and search for the *splynx-ai* package. Then click the *Install* button:

![install](install.png)

Confirm the installation by clicking the `Ok, confirm` button.

![confirm](confirm.png)

## Ticket grades

After installation, the Splynx AI add-on will start evaluating tickets each time a ticket is closed with a *Resolved* status.

The graded tickets can be found in *Administration → Reports → Ticket reports* under *Content*, *Timing* and *Feedback* columns:

1 - satisfied;

0 - not satisfied.

![grades](grades.png)

Under the *Grade* column, there is the total grade for each ticket. The average grade can be found below the Ticket reports table.

## How Splynx AI evaluates tickets

In order for a ticket to be evaluated -  it should be in the *Resolved* status and be closed by an administrator.

The following parameters are considered when evaluating the ticket by the Splynx AI neural networks:

1. **Content**
* admin's messages in text format.

2. **Timing**
* ticket type;
* ticket priority;
* the number of customer's messages in the ticket;
* the number of admin's messages in the ticket;
* the number of attached files in the ticket;
* how much time has passed since the admin's first response;
* the admin's longest response time to the customer;
* the admin's average response time to the customer;
* the duration (lifecycle) of the ticket from being opened until resolved.

3. **Feedback**
* the last message from the admin in the ticket;
* the last message from the customer in the ticket.

