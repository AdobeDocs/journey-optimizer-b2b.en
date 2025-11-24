---
title: In-CRM Insights
description: Access Journey Optimizer B2B Edition buying groups directly in CRMs. Sales team members can view engagement data and identify sales opportunities with In-CRM Insights.
feature: Sales Insights, Buying Groups
role: User
---

# In-CRM Insights

[!DNL In-CRM Insights] is a web-base application that integrates into Salesforce and Microsoft Dynamics 365, giving you access to [!DNL Journey Optimizer B2B Edition] buying groups directly within your CRM. It brings together sales data sources, making it easier to identify opportunities for increased engagement and sales potential.

The [!DNL In-CRM Insights] application is available in the [Marketo Sales Insights package](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/marketo-sales-insight/msi-for-salesforce/installation/install-marketo-sales-insight-package-in-salesforce-appexchange).

## Installation

The installation process includes:

* Setting up user permissions and groups
* Installing the software package
* Logging in through your CRM

### Set permissions

Users installing the software must have permissions to install Salesforce packages.

To access the application, users must have membership in a role with the  **Sales Insights:View Sales Insights** permission.

If you want to restrict users to only [!DNL In-CRM Insights]:

1. Create a [custom role](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/accounts/buying-groups/default-custom-roles#create-a-custom-role) and assign it the **Sales Insights: View Sales Insights** permission.
1. Create a new [user group](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/user-management#create-user-group).
1. Add an Experience Platform product profile to the group.

### Install the package

To install the In-CRM Insights package, follow the steps for Salesforce or Microsoft Dynamics.

#### Salesforce

1. Download the [In-CRM Insights installer package](https://experience.adobe.com/solutions/OneAdobe-sales-workflow-optimizer-sales-insight-ui/install/sales-insight?crm=salesforce).
1. After sign-in, you are redirected to the package installation page.
1. Select the **[!UICONTROL Install for All Users]** option and click **[!UICONTROL Install]**.

   ![Install the In-CRM Insights package](assets/incrm-install-sf.png){width=500}

1. Approve third-party access in the dialog, then click **[!UICONTROL Continue]**.
1. When the installation finishes, click **[!UICONTROL Done]**.

   It is now listed on the  **Installed Packages** page and **Journey Optimizer B2B Edition** is listed in the App Launcher.

   ![In-CRM Insights set up within Salesforce](assets/in-crm-install-sf-done.png){width=800 zoomable="yes"}

#### MS Dynamics

1. Download the [In-CRM Insights installer package](https://experience.adobe.com/solutions/OneAdobe-sales-workflow-optimizer-sales-insight-ui/install/sales-insight?crm=dynamics).
1. Go to the [Power Apps porta](https://make.powerapps.com/){target=_blank}.
1. After signing in, select the environment for the package, and then navigate to **[!UICONTROL Solutions]** from the left menu.
1. Click **[!UICONTROL Import solution]**.
1. Browse to and upload the installer package, then click **[!UICONTROL Next]**.
1. Verify the package details and click **[!UICONTROL Next]**.
1. Under _Environment variables_, verify that the value is set to `prod` (do not change the value) and click **[!UICONTROL Import]**.
1. When installation is complete,  **[!UICONTROL Journey Optimizer B2B Edition]** > **[!UICONTROL Buying groups]** is displayed on the left navigation bar.

   ![In-CRM Insights available in Microsoft Dynamics](assets/incrm-ms-install-done.png){width=800  zoomable="yes"}

## View your buying groups

Follow the prompts to log in to your Adobe account. Your buying groups are loaded and available to view.

After selecting a buying group, you can browse the [group details](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/accounts/sales-experience/buying-group-details#). This is the same as the data and insights displayed in Journey Optimizer B2B Edition, but data is read-only through [!DNL In-CRM Insights].
