---
title: Sales alert email
description: Learn how to include an automated sales alert email in your account journeys.
feature: Email Authoring, Content
---
# Sales alert email

A _sales alert email_ signals the hand-off of buying groups to Sales. The email contains a summary of the buying group and information about the buying group members and their activities.

As a marketer, you can configure a sales alert email node in your account journeys to alert your sales team about the completion of the journey for particular buying groups. Within the node, you can specify the email IDs of the sales team or a distribution alias that reaches a set of accounts.

>[!NOTE]
>
>The sales alert email is sent if the buying group has at least four members with the assigned buying group role and the group contains a person with the _Decision Maker_ or an _Influencer_ role.

+++Sample sales alert email
![Example of a sales alert email using the default template](./assets/sales-alert-email-example.png){width="500" zoomable="yes"}

+++

## Email content


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
| Buying group summary | Activity summary (powered by Gen AI) | AI-generated summary of the buying group based on the activities of the members. The activities over the last 30 days are considered. |
|   | Key interesting moments | Recent interesting moments related to the members of the buying group. |
| Members | List of four Buying Members | Details of the top four buying group members by engagement score and role. |
| Each buying group member | Member Name | Name of the Buying Group member. |
|   | Title | Title of the Buying Group member. |
|   | Role | Buying Group member role of the member. |
|   | Engagement Score | Buying Group member engagement score. The score is based on active engagement activities in the last 30 days. |
|   | Last Interesting Moment | The recent most interesting moment related to the member. |
|   | Latest 2 recent activities | The latest two activities related to the buying group member. |
|   | Email ID | Email ID of the buying group member. |
|   | Phone number | Phone number of the buying group member. |
