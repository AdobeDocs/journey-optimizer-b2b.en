---
title: Configure Experience Manager asset repositories
description: Learn about asset management.
feature: Assets, Content
role: Administrator
---
# Configure Experience Manager asset repositories

Adobe Journey Optimizer B2B Edition integrates with Adobe Experience Manager Assets as a Cloud Service, allowing more than just using assets like emails within an account journey. It ensures transparency by exchanging information with Experience Manager Assets. You must configure the connection to Adobe Experience Assets to enable this capability.

Adobe Experience Manager Cloud Manager is organized into programs, and each program has multiple environments and repositories ([Learn more](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/programs/program-types)). When you configure Adobe Experience Manager Assets in Adobe Journey Optimizer B2B Edition, you set up connections to each repository that you want to use for accessing digital assets.

## Prerequisites

* Generate service credentials for the desired environment on the AEM Headless Developer Console ([Learn more](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials#generate-service-credentials)).
* Procure the certificates that are needed for the connection. As a best practice, ensure that the certificates have at least six months remaining before expiration. The certificates expire every 365 days.
* Adobe Journey Optimizer B2B Edition supports access to one digital asset management source at a time. Ensure the required assets are available in Adobe Experience Manager before you switch.

>[!IMPORTANT]
>
>The service credentials are bonafide and contain a private key. These must be stored, managed, and accessed according to your organization's IT and Security policy.

## Add a repository connection

1. Click Configuration in the left navigation.
1. Click **[!UICONTROL Assets]** on the intermediate panel.
   The default digital asset management option is configured as `Adobe Marketo Engage`.
1. Configure the connections to each environment repository one by one.
   Within the _[!UICONTROL Adobe Experience Manager Assets]_ box on the right, click the arrow next to **[!UICONTROL Configure a repository]** to access the repository. 
1. Select a repository to configure.
1. Click **[!UICONTROL Add a certificate]** and upload the file.
   You can upload a .json file either by dragging it onto the dialog or using the link. Ensure the file is of json type.
   After upload, the certificate is displayed at the bottom. 
   Click the Add button to complete the certificate.
   Note: If an invalid file is used, the modal would show an error at the bottom. 
1. Click the back (←) button to return to the main configuration page.
   Note: The configured repository is displayed in the table under the selection panel.  
   You may choose to add another repository following the above steps. 
1. Click Continue to complete the configuration.

When you finish configuring the repositories, you can select the Adobe Experience Manager Assets for digital asset management.

>[!NOTE]
>
>Adobe Journey Optimizer B2B Edition supports access to one digital asset management source at a time. 

When the Experience Manager Assets repository configuration is complete, Adobe Experience Manager Assets appears in use and you can use the Assets in your marketing content.

## Replace a certificate

Certificates expire every 365 days from the creation date. They must be replaced before their expiry to ensure you can continue to access assets.

>[!NOTE]
>
>Adobe Journey Optimizer B2B Edition communicates with Experience Manager assets for the usage information. The connection must stay active for reliable usage data sync and to prevent data discrepancies. Admin users will be notified about expiring certificates via the in-app notifications. They can also note the expiry dates on the Assets subsection - Digital asset management in the Admin area.

1. On the digital asset management page, locate the list of the configured repositories.
1. Click the desired repository to replace the certificate.
1. Click the ellipses (...) against the certificate file, to reveal the options for actions on the certificate. 
1. Click on replace to open the modal for file upload
1. Upload a file either by dragging it onto the modal or using the link on the modal. Ensure the file is of json type.
1. Click on replace to confirm the upload. 

## Delete a repository

Deleting a repository removes user access to the Experience Manager Assets environment within Journey Optimizer B2B Edition.

1. On the _Digital asset management_ page, locate the list of the configured repositories.
1. Click on the desired repository to edit the connection.
1. Click on the ellipses (...) against the certificate file, to reveal the options for actions on the certificate. 
1. Click on delete to delete the repository.

## Switch back to Adobe Marketo Engage Assets

Select Adobe Marketo Engage digital asset management in the Assets section.

After the confirmation, the Adobe Marketo Engage assets library is available for users.
