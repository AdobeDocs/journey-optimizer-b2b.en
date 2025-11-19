---
title: "XDM Field Management"
description: "Use XDM field management to control the data that is available to Journey Optimizer B2B Edition."
feature: Data Management, Integrations
role: User
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a limited beta release"
---

# XDM field management

Experience Data Model (XDM) fields are schema elements that provide data to the [!DNL Journey Optimizer B2B Edition] application. You use XDM fields as filters and constraints in journeys, buying groups, and features, such as email personalization and conditional content.

Schemas define fields based on standard XDM classes. Standard XDM classes include Individual Profile, Business Account, and Experience Event. Relational schemas also define fields that allow you to model structured data similarly to traditional relational databases.

Adobe Experience Platform (AEP) schemas typically contain many fields in complex hierarchies. Traversing XDM schema trees takes time. XDM field management streamlines field selection by displaying only fields relevant to each journey. Administrators control which fields appear for journey creators. Administrators also set fields to read-only or editable. These actions improve efficiency during journey design.

Administrators who understand XDM and collaborate with data engineers or B2B customer data platform (CDP) data modeling stakeholders follow the procedures in this guide.

>[!NOTE]
>[Relational schemas](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/relational#) are available for [!DNL Journey Optimizer B2B Edition] as a limited release. Data Mirror and relational schemas are available to Journey Optimizer Orchestrated campaigns license holders. Relational schemas are also available as a limited release for Customer Journey Analytics users, depending on your license and feature enablement. Contact your Adobe representative for access.

## Accessing XDM classes

To open the XDM field management area, navigate to **Configurations** > SETUP > **XDM Classes**.

* You can add new fields only after a schema is actively being used in a journey.
* Deleting, renaming, or changing field types can cause journey functionality issues. Take care when manipulating schemas.
* Do not rename or delete schemas or modify keys in relational schemas.

>[!IMPORTANT]
>You can update your field selection at any time by selecting new fields or deselecting fields that you no longer need. Once you publish a journey using this schema, you lock the schema structure. Deleting or renaming the schema, adding new fields, or changing field types is not supported and may cause journey failures.

## Standard classes

In the Standard classes tab, you can edit _Managed fields_ and _Updatable fields_.

* Managed fields appear in journeys, buying groups, and personalization features.
* Updatable fields serve as constraints for the _Update Account Profile_ and _Update Person Profile_ journey nodes.

![Standard classes tab showing managed and updatable fields for XDM class configuration](assets/xdm-standard.png){width="600" zoomable="yes"}

Follow these steps to select fields from the union schema for standard XDM classes:

1. Go to **Administration** > **Configurations** > **XDM Classes**.
1. Open the **Standard** tab. Choose one of the following classes:

   * XDM Individual Profile
   * XDM Business Account

The table displays information including:

* Number of Managed fields
* Number of Updatable fields
* Last update time

Click the class name to open the _Managed fields_ selection dialog.

![Managed fields selection dialog for standard XDM classes displaying configurable fields options](assets/xdm-standard-managed-fields.png){width="600" zoomable="yes"}

1. Click the **...** menu to switch between _[!UICONTROL Managed fields]_ and _[!UICONTROL Updatable fields]_. The dialog lists all configurable fields.
1. Select up to 100 fields for each XDM class.
1. Click **[!UICONTROL Save]** to confirm your selections.

Use the [!UICONTROL Only show selected fields] filter to display only active fields.

For _Updatable fields_, you access a separate dialog that lets you choose fields from other data sources:

1. In the Datasets dropdown, select the data source that you want to configure.
1. Edit the fields from the selected dataset.
1. Click **[!UICONTROL Save]** to apply changes.

![Dialog for selecting updatable fields from datasets in XDM schema configuration](assets/xdm-select-updateable.png){width="600" zoomable="yes"}

The field must first be _Managed_ before they can be _Updatable_. The _Updatable fields_ that you select must exist in your user-provided schema.

## Relational schemas

Relational schemas allow you to create custom data classes. With access to multiple datasets, you can create classes specifically tailored to your data needs.
Use relational schemas for business entities such as purchases, licenses, and event registrations in journey decisions and email personalization. You can select up to 50 schemas and up to 100 fields per schema.

![Relational schemas tab in Schema Editor showing business entity fields for Adobe Journey Optimizer](assets/xdm-relational.png)

>[!NOTE]
>This feature currently supports Account-related custom object use cases, with plans to support more out-of-the-box object use cases in the future.

Create relational schemas using the Schema Editor in **Data Management** > **Schemas**.

These configurations values must be included when creating a schema for use with [!DNL Journey Optimizer B2B Edition]:

* Behavior: Record
* Segmentation: Enabled
* Relationship type: Many-to-one
* Reference schema: B2B Account
* Required fields: Primary key, foreign key, and version descriptor
* Associated dataset: Defined and mapped to the schema

### Create a Relational Schema

Follow these steps to select fields for use in [!DNL Journey Optimizer B2B Edition]:

1. Go to **Administration** > **Configurations** > **XDM Classes**.
1. Open the **Relational** tab to view your schemas.
1. Click **[!UICONTROL Select relational XDM schema]**.

   * In the beta version, only _Account many-to-one Custom Objects_ are supported.

1. Select a relational schema and click **[!UICONTROL Next]**.

   * In the beta version, you cannot remove a schema from the list once you select it.

1. Enter a namespace or use the default namespace. Click **[!UICONTROL Next]**.

   * You can only set the namespace once, and cannot reverse this action.

1. Review the relational schema fields. Click the ![Info icon](../assets/do-not-localize/icon-info-light.svg) [!UICONTROL Info] icon to view the field metadata.
1. Select the fields to enable for journeys and personalization. The platform automatically selects the following required fields:

   * Foreign key
   * Primary key
   * Version descriptor

1. Use the [!UICONTROL Only show selected fields] slider to preview your selections.
1. Filter fields by name using the Search bar.
1. Click **[!UICONTROL Save]**.

## Events

Use Experience Events and their associated fields in journey decisions. You can select up to 50 events and up to 100 fields per event.

![Events tab showing Experience Events selection and schema fields for journeys and personalization](assets/xdm-events.png){width="700" zoomable="yes"}

Click an event name to view details and edit the configured fields.

Follow these steps to select Experience Events and schema fields:

1. Go to **Administration** > **Configurations** > **XDM Classes**.
1. Open the **Events** tab.
1. To select fields for an event, click **[!UICONTROL Select experience event]**.
1. On the Details page, click **[!UICONTROL Select event type]**.
1. From the Event list, choose your event.
1. Click **[!UICONTROL Select]** to close the dialog.

   * In the beta, you cannot remove selected events.

1. Click **[!UICONTROL Select fields]**.
1. Use the [!UICONTROL Only show selected fields] slider to view your current selections.
1. Select the fields to use in [!DNL Journey Optimizer B2B Edition]. Click **[!UICONTROL Select]** to close the dialog.
1. Click [!UICONTROL Save].
