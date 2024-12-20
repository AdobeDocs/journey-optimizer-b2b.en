---
title: Export Account List
description: Learn how to export the account list based on buying groups filter.
---
# Export account list

Use the _Export account list_ feature to export all accounts or a set for accounts based on filtering that you define. The export process produces a CSV file and sends the URL for the stored file within a pulse notification. You can use this feature to move accounts into third-party platforms when needed.

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
