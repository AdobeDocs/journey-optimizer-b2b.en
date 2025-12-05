---
title: XDM Field Management
description: Use XDM field management to control the data that is available to Journey Optimizer B2B Edition.
feature: Data Management, Integrations
role: User
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a limited beta release"
---

# XDM field management

Experience Data Model (XDM) fields are schema elements that provide data to the [!DNL Journey Optimizer B2B Edition] application. Use XDM fields as filters and constraints in journey nodes, buying groups, and for content features, such as email personalization and conditional content.

Schemas define fields based on standard XDM classes. Standard XDM classes include Individual Profile, Business Account, and Experience Event. Relational schemas also define fields that allow you to model structured data similarly to traditional relational databases.

Adobe Experience Platform (AEP) schemas typically contain many fields in complex hierarchies. Traversing XDM schema trees takes time. XDM field management streamlines field selection by displaying only fields relevant to each journey. Administrators control which fields appear for journey creators. Administrators also set fields to read-only or editable. These actions improve efficiency during journey design.

Administrators who understand XDM and collaborate with data engineers or B2B customer data platform (CDP) data modeling stakeholders should use the procedures on this page.

>[!NOTE]
>[Relational schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/relational#) are available for [!DNL Journey Optimizer B2B Edition] as a limited availability release. Data Mirror and relational schemas are available to Journey Optimizer Orchestrated campaigns license holders. Relational schemas are also available as a limited release for Customer Journey Analytics users, depending on your license and feature enablement. Contact your Adobe representative for access.

## Access XDM classes

1. In the left navigation, choose **[!UICONTROL Administration]** > **[!UICONTROL Configuration]**.

1. Click **[!UICONTROL XDM Classes]** on the intermediate panel.

   * Use the **[!UICONTROL Standard]** and **[!UICONTROL Relational]** tabs to add new fields and make them available in Journey Optimizer B2B Edition.

   * Use the **Events** tab to [select specific AEP Experience Events and their associated fields](./configure-aep-events.md) to use for journey event nodes.

## Field selections

>[!IMPORTANT]
>
>You can update your field selection at any time by selecting new fields or deselecting fields that you no longer need. When you publish a journey using this schema, you lock the schema structure. Deleting or renaming the schema, adding new fields, or changing field types is not supported and may cause journey failures.

Use the following guideline for making field selections:

* You can add new fields only after a schema is actively being used in a journey.
* Deleting, renaming, or changing field types can cause journey functionality issues. Take care when manipulating schemas.
* Do not rename or delete schemas or modify keys in relational schemas.

### Standard classes

In the _[!UICONTROL Standard]_ tab, you can edit _Managed fields_ and _Updatable fields_ for the standard classes:

* Managed fields appear in journeys, buying groups, and personalization features.
* Updatable fields serve as constraints for the _Update Account Profile_ and _Update Person Profile_ journey nodes.

![Standard classes tab showing XDM class configuration](assets/xdm-standard.png){width="600" zoomable="yes"}

The list includes two classes:

* **[!UICONTROL XDM Individual Profile]**
* **[!UICONTROL XDM Business Account]**

The displayed class information includes:

* Number of Managed fields
* Number of Updatable fields
* Last update time

To select fields from the union schema for standard XDM classes, click the class name to open the _Managed fields_ selection dialog, or click the _More menu_ ( **...** ) icon to choose between _[!UICONTROL Managed fields]_ and _[!UICONTROL Updatable fields]_.

![Click the More menu icon to choose between managed fields and updatable fields](./assets/xdm-classes-standard-more-menu.png){width="550" zoomable="yes"}

>[!NOTE]
>
>A field must first be _Managed_ before it can be _Updatable_. The _Updatable fields_ that you select must exist in your user-provided schema. Your schema may not include required fields, except for system-defined fields.

#### Managed fields

When you choose **[!UICONTROL Managed fields]**, the _Select fields_ dialog lists all configurable fields.

1. Select up to 100 fields for each XDM class.

   Use the _[!UICONTROL Search]_ field to filter the displayed list by name. Use the **[!UICONTROL Only show selected fields]** slider to review the current selections.

   ![Managed fields selection dialog for standard XDM classes displaying configurable fields options](assets/xdm-standard-managed-fields.png){width="450" zoomable="yes"}

1. Click **[!UICONTROL Save]** to confirm your selections.

#### Updatable fields

Before you configure updatable fields, they must reside in a custom dataset. For a walkthrough of the custom dataset workflow, see [Create datasets and ingest data](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-management/create-datasets-and-ingest-data#){target="_blank"}, and use the **[!UICONTROL Create dataset from schema]** option. This dataset is used to isolate updatable fields. All updatable fields must be in this dataset.

>[!IMPORTANT]
>
>Guardrails for updateable fields:
>
>* Schemas - The schema must not include any required fields other than system-defined ones, such as `identityMap` or `personID`, on the XDM Individual Profile class.
>* Datasets - Do not select a dataset that is already in use for another purpose. As a best practice, create dedicated datasets specifically for storing updatable fields. Use a separate dataset for each XDM class.

Create a dataset for Individual Profile, and another for Business Account. Select each new dataset during the configuration process:

1. For **[!UICONTROL Datasets]**, select the new data source that you created.

1. Choose the fields from the selected dataset.

   ![Dialog for selecting updatable fields from datasets in XDM schema configuration](./assets/xdm-select-updateable.png){width="450" zoomable="yes"}

1. Click **[!UICONTROL Save]** to apply your changes.

### Relational schemas

Relational schemas allow you to create custom data classes. With access to multiple datasets, you can create classes specifically tailored to your data needs. Use relational schemas for business entities such as purchases, licenses, and event registrations in journey decisions and email personalization. You can select up to 50 schemas and up to 100 fields per schema.

For information about how the selected fields are used for advanced email personalization, see [Content personalization](../content/personalization.md#custom-datasets).

>[!NOTE]
>
>This feature currently supports account-related custom object use cases, with plans to support more out-of-the-box object use cases in the future.

You can create relational schemas using the schema editor (go to **[!UICONTROL Data Management]** > **[!UICONTROL Schemas]** in the left navigation).

When creating a schema for use with [!DNL Journey Optimizer B2B Edition], the following configurations values are required:

* Behavior: Record
* Segmentation: Enabled
* Relationship type: Many-to-one
* Reference schema: B2B Account
* Required fields: Primary key, foreign key, and version descriptor
* Associated dataset: Defined and mapped to the schema

To select relational schema fields for use in [!DNL Journey Optimizer B2B Edition]:

1. Select the **[!UICONTROL Relational]** tab to view your schemas.

   ![Relational schemas tab in Schema Editor showing business entity fields for Adobe Journey Optimizer B2B Edition](assets/xdm-relational.png){width="600" zoomable="yes"}

1. Click **[!UICONTROL Select relational XDM schema]**.

   >[!NOTE]
   >
   >In this beta feature release, only _Account many-to-one Custom Objects_ are supported.

1. Select a relational schema and click **[!UICONTROL Next]**.

   >[!NOTE]
   >
   >In this beta feature release, you cannot remove a schema from the list after you select it.

   ![Select a relational schema in the dialog](./assets/xdm-classes-relational-select-schema-dialog.png){width="500" zoomable="yes"}      

1. Enter a namespace or use the default namespace. Click **[!UICONTROL Next]**.

   You can only set the namespace once, and cannot reverse this action.

   ![The default namespace in the Create namespace dialog](./assets/xdm-classes-relational-create-namespace.png){width="400" zoomable="yes"}   

1. Review the relational schema fields. 

   Click the _Info_ ![Info icon](../assets/do-not-localize/icon-info-light.svg) icon to view the field metadata.

1. Select the fields to enable for journeys and personalization.

   The platform automatically selects the following required fields:

   * Foreign key
   * Primary key
   * Version descriptor

   Use the _[!UICONTROL Search]_ field to filter the displayed list by name. Use the **[!UICONTROL Only show selected fields]** slider to review the current selections.

   ![Select fields for the relational schema in the dialog](./assets/xdm-classes-relational-select-schema-fields.png){width="500" zoomable="yes"}   

1. Click **[!UICONTROL Save]**.
