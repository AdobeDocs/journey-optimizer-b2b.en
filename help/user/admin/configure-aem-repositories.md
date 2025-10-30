---
title: Configure Experience Manager Asset Repositories
description: Connect Experience Manager Assets repositories to Journey Optimizer B2B Edition for seamless digital asset access in content authoring.
feature: Assets, Integrations
role: Admin
exl-id: 4cdfc8bc-823f-4320-a2c3-08226f26eec2
---
# Configure Experience Manager asset repositories

[!DNL Adobe Journey Optimizer B2B Edition] integrates with [!DNL Adobe Experience Manager Assets as a Cloud Service], allowing the use of assets in your email content. It ensures transparency by exchanging information with [!DNL Experience Manager Assets]. Configure the connection to [!DNL Adobe Experience Assets] to enable this capability.

Adobe Experience Manager Cloud Manager is organized into programs, and each program has multiple environments and repositories ([Learn more](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/programs/program-types){target="_blank"}). When you configure Adobe Experience Manager Assets in Adobe Journey Optimizer B2B Edition, you set up connections to each repository that you want to use for accessing digital assets.

{{aem-assets-licensing-note}}

## Prerequisites

* Generate service credentials for the desired environment on the AEM Headless Developer Console ([Learn more](https://experienceleague.adobe.com/en/docs/experience-manager-learn/getting-started-with-aem-headless/authentication/service-credentials#generate-service-credentials){target="_blank"}).
* Procure the certificates that are needed for the connection. As a best practice, ensure that the certificates have at least six months remaining before expiration. The certificates expire every 365 days.
* Adobe Journey Optimizer B2B Edition supports access to one digital asset management source at a time. Ensure that the required assets are available in Adobe Experience Manager before you switch.

>[!IMPORTANT]
>
>The service credentials are bona fide and contain a private key. These credentials must be stored, managed, and accessed according to your organization's IT and Security policy.

## Add a repository connection

1. In the left navigation, choose **[!UICONTROL Administration]** > **[!UICONTROL Configuration]**.

1. Click **[!UICONTROL Assets]** on the intermediate panel.

   ![Access the Assets configuration space](./assets/configuration-assets-aem.png){width="700" zoomable="yes"}

<!--   The default digital asset management option is configured as `Adobe Marketo Engage`.
-->
   From here, you can configure the connections to each AEM environment repository one by one.

1. Within the _[!UICONTROL Adobe Experience Manager Assets]_ box, click the arrow next to **[!UICONTROL Configure a repository]** and choose the repository.

   ![Choose an AEM Assets repository](./assets/configure-assets-aem-choose-respository.png){width="500"}

1. Click **[!UICONTROL Add a certificate]** and use the dialog tools to upload the file.

   You can upload a .json file by dragging it onto the dialog. You can also click the link to locate and select a file from your system.

   ![Upload the certificate JSON file](./assets/configuration-assets-aem-upload-cert.png){width="500"}
   
   After upload, the certificate is displayed at the bottom.

   >[!NOTE]
   >
   >If an invalid file is used, the dialog displays an error at the bottom.

   Click **[!UICONTROL Add]** to complete the certificate.

1. Click the back (←) arrow to return to the main configuration page.   

   The configured repository is displayed in the table under the selection panel. You can add another repository by repeating steps 3-4.

   ![Review the configured AEM asset repositories](./assets/configuration-assets-aem-repositories.png){width="600" zoomable="yes"}

When you finish configuring the repositories, team members can select the [!DNL Adobe Experience Manager Assets] when authoring content.

>[!NOTE]
>
>Adobe Journey Optimizer B2B Edition supports access to one digital asset management source at a time when authoring content. 

## Replace a certificate

Certificates expire every 365 days from the creation date. To ensure that your team can continue to access assets, replace the certificate before it expires.

>[!NOTE]
>
>[!DNL Adobe Journey Optimizer B2B Edition] communicates with [!DNL Experience Manager Assets] for usage information. The connection must stay active for reliable usage data synchronization and to prevent data discrepancies. Administrators receive notifications about expiring certificates via the in-app notifications. Expiration dates are also displayed in the _Assets_ subsection of the _[!UICONTROL Administration]_ area.

1. On the digital asset management page, locate the list of the configured repositories.

1. Click the desired repository to replace the certificate.

1. Click the ellipses (**...**) icon for the certificate file to reveal the options for actions on it.

   ![Access the options menu for the AEM asset repository certificate](./assets/configuration-assets-aem-repo-menu.png){width="600" zoomable="yes"}

1. Choose **[!UICONTROL Replace]** to open the dialog for file upload.

1. Upload a file either by dragging it onto the dialog or using the link. Ensure that the file is of JSON type.

   ![Upload the replacement AEM assets repository certificate JSON file](./assets/configuration-assets-aem-upload-replacement-cert.png){width="500"}

1. Click **[!UICONTROL Replace]** to confirm the upload.

## View a certificate

You can view the certificate JSON file associated with the repository connection. 

1. On the digital asset management page, locate the list of the configured repositories.

1. Click the connected repository.

1. Click the ellipses (**...**) icon for the certificate file to reveal the options for actions on it.

1. Choose **[!UICONTROL View]**.

   ![View the certificate JSON file for a connected AEM asset repository](./assets/configuration-assets-aem-view-cert.png){width="600"}

1. Click **[!UICONTROL Close]** to return to the Configure repository page. 

## Delete a repository connection

Deleting a repository removes user access to the Experience Manager Assets environment within Journey Optimizer B2B Edition.

1. On the _[!UICONTROL Digital asset management]_ page, locate the list of the configured asset repositories.

1. Click the desired repository name to edit the connection.

1. Click the ellipses (**...**) icon for the certificate file to reveal the options for actions on it.

1. Choose **[!UICONTROL Delete]**.

1. In the confirmation dialog, click **[!UICONTROL Delete]**.
<!--

## Switch back to Adobe Marketo Engage Assets

Select Adobe Marketo Engage digital asset management in the Assets section.

After the confirmation, the Adobe Marketo Engage assets library is available for users.
-->
