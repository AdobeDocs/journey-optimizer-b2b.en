---
title: Export Accounts
description: Export filtered account lists to CSV for third-party platforms with buying groups and engagement score filters in Journey Optimizer B2B Edition.
feature: Audiences
role: User
exl-id: 3ec8e8fd-1bc2-4efa-840f-f06520099060
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: e935834c-48b7-43d8-b754-a815196a1b05
    internal-label: Account lists
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
autotag-review: 2026-03-30T19:51:33.392Z
TQID: https://experienceleague.adobe.com/fvkVLjO9oIF7hOuoqdSS-jU4wAvsrPnKp1fIabH-Ewk
---
# Export accounts

Use the _Export accounts_ feature to export all accounts or a set of accounts based on filtering that you define. The export process produces a CSV file and sends the URL for the stored file within a pulse notification. You can use this feature to move accounts into third-party platforms when needed.

1. In Journey Optimizer B2B Edition, go to **[!UICONTROL Accounts]** > **[!UICONTROL Buying groups]** in the left navigation.

1. Select the **[!UICONTROL Browse]** tab.

1. Click **[!UICONTROL Export accounts]** at the top right.

   ![Edit account details](./assets/export-accounts.png){width="800" zoomable="yes"}

1. In the dialog, define the parameters of the account audiences to be exported.

   ![Specify the account audience filtering](./assets/export-accounts-dialog.png){width="400"}

   For the **[!UICONTROL Engagement score]**, the operator `Between` is inclusive, as are percentage ranges. For example, 5.1 and 5 are both _between_ 5 and 6.

   Empty filtering parameters are treated like `Is Any`.

1. Click **[!UICONTROL Export accounts]** to generate the CSV file using the specified filters.

1. When you receive the notification that the export is complete, click the notification link to access the CSV file.

   ![Click the notification to download the exported accounts list CSV file](./assets/export-accounts-notification.png){width="425"}

   >[!NOTE]
   >
   >If you have a notification subscription for email notification that is set up in your Adobe user account preferences, it may be an email notification.

   The application page redirects to the _Buying Group_ browse tab and the system save file dialog prompts you to save the file to your system. If you need to share the data, you can use your team's file sharing system.
