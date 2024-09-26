---
title: Sales Alert Email
description: Learn how to include an automated sales alert email in your account journeys.
feature: Email Authoring, Content
exl-id: 01bffbce-6c73-483a-8731-de4e5569cf61
---
# Sales alert email

A _sales alert email_ signals the hand-off of buying groups to Sales. The email contains a summary of the buying group and information about the buying group members and their activities.

As a marketer, you can configure a sales alert email node in your account journeys to alert your sales team about the completion of the journey for particular buying groups. Within the node, you can specify the email addresses of the sales team or a distribution alias that reaches a set of accounts.

## Email content

+++Sample sales alert email
![Example of a sales alert email using the default template](./assets/sales-alert-email-example.png){width="500" zoomable="yes"}

+++

| Section  | Name | Description |
| - | ---- | ----------- |
| Buying group information | Buying Group Name | Display name for the buying group.|
|   | Account Name | Name of the account.|
|   | Engagement score | Engagement score of the buying group, based on active engagement activities in the last 30 days. |
|   | Completeness score | Completeness score of the buying group. |
|   | Solution interest | Solution interest linked to the buying group' |
|   | Status | Status of the buying group. |
| Buying group highlights | Top engaged members | Top engaged members of the buying group by buying group member engagement score and role. |
|   | Topic of interest | Most frequent keywords occurring in the content engagement, based on emails, downloads, chat, PDF review, activity summary, and webinar questions. |
|   | Missing roles | Mandatory roles in the template but are missing in the buying group.|
| Buying group summary | Activity summary (powered by Generative AI) | AI-generated summary of the buying group based on the activities of the members. The activities over the last 30 days are considered. |
|   | Key interesting moments | Recent interesting moments related to the members of the buying group. |
| Members | List of four Buying Members | Details of the top four buying group members by engagement score and role. |
| Each buying group member | Member name | Name of the buying group member. |
|   | Title | Title of the buying group member. |
|   | Role | The Buying group role of the member. |
|   | Engagement score | Buying group member engagement score. The score is based on active engagement activities in the last 30 days. |
|   | Last interesting moment | The recent most interesting moment related to the member. |
|   | Most recent activities | The latest two activities related to the buying group member. |
|   | Email ID | Email ID of the buying group member. |
|   | Phone number | Phone number of the buying group member. |

## Add a sales alert email action in an account journey

You can set up sales alert email deliveries in an account journey when you add a _[!UICONTROL Take an action]_ node and do the following:

1. For the _[!UICONTROL Action on]_ target, choose **[!UICONTROL Account]**.

1. For _[!UICONTROL Action on accounts]_, choose **[!UICONTROL Send Sales Alert]**.

1. For **[!UICONTROL Select solution interest]**, choose the solution interest to use for the generated email content.

1. For **[!UICONTROL Send Email To]**, enter each email address or alias that you want to include for the delivery.

   ![Create new email dialog](assets/sales-alert-email-journey-node.png){width="600" zoomable="yes"}

   After the account journey is published, the Sales Alert is delivered according to these parameters.
