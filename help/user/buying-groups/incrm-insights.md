---
title: In-CRM Insights
description: Access Journey Optimizer B2B Edition buying groups directly in CRMs. Sales team members can view engagement data and identify sales opportunities with In-CRM Insights.
feature: Sales Insights, Buying Groups
role: User
exl-id: c55a1fce-2ddc-481b-9f60-5e67a4bf9633
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: afadf741-c5fe-42cd-8013-23bb6ff2d1bc
    internal-label: Buying Groups
  - id: fc1ff3b2-6614-41ad-a113-de48597598fd
    internal-label: Sales Experience
  - id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
    internal-label: Integrations
subfeature_v2:
  - id: fe583b80-65a2-48c2-b4e1-9ea8fbac0a8a
    internal-label: CRM integrations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
autotag-review: '2026-03-30T21:40:22.011Z'
---
# In-CRM Insights

[!DNL In-CRM Insights] is a web-base application that integrates into Salesforce and Microsoft Dynamics 365, giving you access to [!DNL Journey Optimizer B2B Edition] buying groups directly within your CRM. It brings together sales data sources, making it easier to identify opportunities for increased engagement and sales potential.

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
