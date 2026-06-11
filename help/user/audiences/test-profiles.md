---
title: Test Profiles
description: Learn how to create test profiles for use with content testing and preview in Journey Optimizer B2B Edition.
feature: Audiences
role: Admin
level: Intermediate
autotag-review: '2026-05-29T18:38:56.987Z'
TQID: 'https://experienceleague.adobe.com/7HMk9y8XhI6ONurF341d46oxkWj8dgnUdnWTylUu4pw'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: f2da1b69-6919-4386-a5d2-9c7b5c9033db
    internal-label: Data management
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
---
# Test profiles {#test-profiles}

Test profiles are required to [preview and test landing page content](../content/landing-pages-create-publish.md#test-landing-page) in Journey Optimizer B2B Edition. You can define a set of test profiles by creating a schema, creating the dataset, and uploading a CSV file.

<!--
>[!NOTE]
>
>[!DNL Journey Optimizer B2B Edition] allows testing different variants of your content by previewing it and sending proofs using sample input data uploaded from a CSV or JSON file, or added manually. 
-->

Creating a test profile is similar to creating regular profiles in [!DNL Adobe Experience Platform]. For more information, refer to the [Real-time Customer Profile documentation](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html){target="_blank"}.


## Create a schema {#create-schema}

To create profiles, you first need to create a schema in [!DNL Journey Optimizer B2B Edition].

1. Expand **[!UICONTROL Data Management]** in the left navigation, select **[!UICONTROL Schemas]**, and click **[!UICONTROL Create schema]** at the top right.

    ![Schemas menu with Create schema button](./assets/create-schema.png){width="800" zoomable="yes"}

1. Select **[!UICONTROL Standard]** as the schema creation option.

1. Select a schema type, for example **[!UICONTROL Manual]**, and click **[!UICONTROL Select]**.

    ![Schema type selection with Manual creation option selected](./assets/create-schema-options.png){width="500"}

1. Select a schema type, for example **[!UICONTROL Individual Profile]**, and click **[!UICONTROL Next]**.

   ![Schema type selection showing Individual Profile option](./assets/create-schema-individual-profile.png){width="700" zoomable="yes"}

1. Enter a name (required) and description (optional) for the schema and click **[!UICONTROL Finish]**.

    ![Add name and description for the schema](./assets/create-schema-name-description.png){width="700" zoomable="yes"}

    The schema structure is displayed, with the _[!UICONTROL Composition]_ panel on the left. 

1. In the **[!UICONTROL Field groups]** section, click **[!UICONTROL Add]** and select the appropriate field groups.

   Use the search tool to locate and select the **[!UICONTROL Profile test details]** field group.

    ![Search existing field groups and select Profile test details](./assets/create-schema-field-groups-profile-test-details.png){width="700" zoomable="yes"}

    When complete, click **[!UICONTROL Add field groups]** and the list of field groups is then displayed on the schema overview screen.

    Repeat this step to add additional field groups that you want to use for test profiles, such as **[!UICONTROL Person Contact Details]** and **[!UICONTROL Work Contact Details]**.

1. In the list of fields, click the field that you want to define as the primary identity.

1. In the _[!UICONTROL Field properties]_ right pane, check the **[!UICONTROL Identity]** and **[!UICONTROL Primary Identity]** options and select a namespace.

   If you want the primary identity to be an email address, choose the **[!UICONTROL Email]** namespace.

    ![Schema fields list for selecting primary identity](./assets/create-schema-primary-identity.png){width="700" zoomable="yes"}

    Click **[!UICONTROL Apply]**.

1. Select the schema and enable the **[!UICONTROL Profile]** option in the **[!UICONTROL Schema properties]** pane.

    ![Schema properties pane with Profile option enabled](assets/create-schema-profile-enable.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.

For more information about schema creation, refer to the [XDM documentation](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites){target="_blank"}.

>[!IMPORTANT]
>
>When creating or replacing a dataset for test profile ingestion, ensure that the schema has the correct identity descriptor applied to the primary identity field (`/personID`) for the intended namespace. If the identity descriptor is missing or incorrectly configured, profiles ingested into this dataset may not be flagged as test profiles (`testProfile = true`), even if the ingestion process completes successfully.
>
>If your test profiles are not flagged correctly after ingestion:
>
>1. Review the schema associated with your dataset.
>1. Confirm that the primary identity field has the correct identity descriptor for your namespace.
>1. If the descriptor is missing, update the schema to add the identity descriptor and re-ingest your data.

## Create a dataset {#create-dataset}

After you create the schema, create the dataset that is used to import the profiles. For more information about dataset creation, refer to the [Catalog Service documentation](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started){target="_blank"}.

1. Under _[!UICONTROL Data Management]_ in the left navigation, select **[!UICONTROL Datasets]**.

1. At the top right, click **[!UICONTROL Create dataset]**.

    ![Datasets menu with Create dataset button](./assets/create-dataset.png){width="800" zoomable="yes"}

1. Choose **[!UICONTROL Create dataset from schema]**.

    ![Create dataset from schema option](./assets/create-dataset-options.png){width="500"}

1. Select the previously created schema and click **[!UICONTROL Next]**.

1. Choose a name and click **[!UICONTROL Finish]**.

    ![Name and finish dataset dialog](./assets/create-dataset-name.png){width="700" zoomable="yes"}

1. In the right panel, enable the **[!UICONTROL Profile]** option.

## Create test profiles using a CSV file {#create-test-profiles-csv}

In [!DNL Adobe Experience Platform], you can create profiles by uploading a CSV file containing the different profile fields into your dataset. This is the easiest method.

1. Create a simple CSV file using a spreadsheet software.

1. Add one column for each required field.

   Make sure that you add the primary identity field (`personID`, for example) and the `testProfile` field set to `true`.

1. Add one line per profile and the values for each field.

   ![CSV file with sample test profile data](./assets/test-profile-csv-data-values.png){width="600" zoomable="yes"}

1. Save the spreadsheet as a csv file, making sure that commas are used as separators.

1. In [!DNL Adobe Experience Platform], navigate to **[!UICONTROL Workflows]**.

1. Choose **[!UICONTROL Map CSV to XDM schema]** and click **[!UICONTROL Launch]**.

   ![Map CSV to XDM schema workflow option](./assets/aep-workflows-data-ingestion.png){width="800" zoomable="yes"}

1. Select the dataset to use for the import and click **[!UICONTROL Next]**.

   ![Dataset selection screen for CSV import](./assets/aep-workflows-data-map-csv.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Choose files]** and select the CSV file, or drag and drop the file from your system. 

   After the file upload is complete, click **[!UICONTROL Next]**.

   ![File upload and sample data](./assets/aep-workflows-data-map-file-upload.png){width="700" zoomable="yes"}

1. Map the source csv fields to the schema fields, then click **[!UICONTROL Finish]**.

   ![CSV field mapping interface showing source and target fields](./assets/aep-workflows-data-mapping.png){width="700" zoomable="yes"}

   The data import begins. The status moves from _Processing_ to _Success_. 

1. At the top right, click **[!UICONTROL Preview dataset]** and check that the test profiles added to the dataset are correct.

   ![Dataset preview showing imported test profiles](./assets/aep-workflows-data-preview-test.png){width="700" zoomable="yes"}

    The test profiles can then be used to [test landing page content](../content/landing-pages-create-publish.md#test-landing-page).

>[!NOTE]
>
>For more information about CSV data import, refer to the [Data Ingestion documentation](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials){target="_blank"}.

<!--
## Create test profiles using API calls {#create-test-profiles-api}

You can also create test profiles via API calls. Learn more in [[!DNL Adobe Experience Platform] documentation](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html){target="_blank"}.

You must use a Profile schema that contains the **[!UICONTROL Profile test details]** field group. The `testProfile` flag is part of this field group.
When creating a profile, make sure you pass the value: `testProfile = true`.

You can also update an existing profile to change its `testProfile` flag to `true`.

Here is an example of an API call to create a test profile:

```bash
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```
-->
