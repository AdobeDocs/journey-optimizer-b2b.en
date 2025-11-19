---
title: In-CRM Insights
description: Access Journey Optimizer B2B Edition buying groups directly in Salesforce. Sales team members can view engagement data and identify sales opportunities with In-CRM Insights.
feature: Sales Insights, Buying Groups
role: User
---

# In-CRM Insights

In-CRM Insights is a web-base application that integrates into Salesforce, giving you access to your Journey Optimizer B2B Edition buying groups directly within Salesforce. It allows you to identify opportunities for increased engagement and sales potential.

The In-CRM Insights application is available in the [Marketo Sales Insights package](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/marketo-sales-insight/msi-for-salesforce/installation/install-marketo-sales-insight-package-in-salesforce-appexchange).

## Permissions

To access the application, users must have membership in a role with the  **Sales Insights:View Sales Insights** permission .

If you want to restrict a group of users to InCRM-Insights, use the following guidelines to create a custom role specifically for InCRM-Insights:

* Create a custom role with only the **Sales Insights:View Sales Insights** permission set.
* Create a new user group, without adding any product profiles.
* Create another user group and add an AEP product profile, or add an existing AEP profile to the user group you just created.
* Assign the new user groups to the new role and add new users to the new user groups. 

## Using In-CRM Insights

The In-CRM Insights application is available in Salesforce through the App Launcher.

1. Click the App Launcher in Salesforce.
1. Select or search for `Journey Optimizer B2B Edition`.
1. In the displayed tab, log in with your Adobe credentials.
1. Choose a sandbox that hosts your Account Journeys.

Your buying groups are loaded and available. Data is read-only through In-CRM Insights.

>[!NOTE]
>
>Membership in the [B2B Sales User](../admin/user-management.md#b2b-built-in-roles) product role is required to access In-CRM Insights.

After selecting a buying group, you can browse the [group details](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/accounts/sales-experience/buying-group-details#), just as in Journey Optimizer B2B Edition.
