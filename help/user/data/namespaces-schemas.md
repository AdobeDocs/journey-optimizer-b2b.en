---
title: B2B Namespaces and schemas
description: Configure Experience Platform B2B namespaces and schemas for Journey Optimizer B2B Edition using the Postman auto-generation utility.
feature: Setup, Data Management
role: Admin
exl-id: 40d01027-7cf2-4189-8a49-7a0783c00721
---
# B2B Namespaces and schemas

The Journey Optimizer B2B Edition setup on the simplified architecture includes configuration of the Experience Platform namespaces and schemas that are used with B2B sources. The Postman automation utility is required for generating B2B namespaces and schemas.

>[!AVAILABILITY]
>
>- You must have access to [Adobe Real-Time Customer Data Platform B2B Edition](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/intro/rtcdpb2b-intro/b2b-overview){target="_blank"} for your B2B schemas to qualify in [Real-Time Customer Profile](https://experienceleague.adobe.com/en/docs/experience-platform/profile/home){target="_blank"}.
>
>- Your Experience Platform B2B entities must use the standard relationships outlined in the [B2B namespaces and schemas guide](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b){target="_blank"}.

Review the following information about the underlying set up for the namespaces and schemas to be used with B2B sources. It also provides details for setting up your Postman automation utility, which is required for generating B2B namespaces and schemas.

## Set up the auto-generation utility

Refer to the following resources for prerequisites and detailed information about how to set up your [!DNL Postman] environment to support the B2B namespace and schema auto-generation utility.

- Download the namespace and schema auto-generation utility collection and environment from the [GitHub repository](https://github.com/adobe/experience-platform-postman-samples/tree/master/Postman%20Collections/CDP%20Namespaces%20and%20Schemas%20Utility){target="_blank"}.
- For information about using Experience Platform APIs including details about gathering values for required headers and reading sample API calls, see [_Getting started with Adobe Experience Platform APIs_](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-guide){target="_blank"}.
- For information about generating your credentials for Experience Platform APIs, see  [_Authenticate and access Experience Platform APIs_](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-authentication){target="_blank"}.
- For information about setting up [!DNL Postman] for Experience Platform APIs, see [_[!DNL Postman] in Adobe Experience Platform_](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/postman){target="_blank"}.

### Environment values

With an Experience Platform developer console and [!DNL Postman] set up, you can apply the appropriate environment values to your [!DNL Postman] environment. The following table provides example values and additional information about populating your [!DNL Postman] environment:

| Variable | Description | Example |
| --- | --- | --- |
| `CLIENT_SECRET` | A unique identifier used to generate your `{ACCESS_TOKEN}`. | `{CLIENT_SECRET}` |
| `API_KEY` | A unique identifier used to authenticate calls to Experience Platform APIs. | `c8d9a2f5c1e03789bd22e8efdd1bdc1b` |
| `ACCESS_TOKEN` | The authorization token required to complete calls to Experience Platform APIs. | `Bearer {ACCESS_TOKEN}` |
| `META_SCOPE` | With regards to [!DNL Journey Optimizer B2B] and [!DNL Marketo Engage], this value is fixed and is always set to: `ent_dataservices_sdk`. | `ent_dataservices_sdk` |
| `CONTAINER_ID` | The `global` container holds all standard Adobe and Experience Platform partner provided classes, schema field groups, data types, and schemas. With regards to [!DNL Marketo], this value is fixed and is always set to `global`. | `global` |
| `TECHNICAL_ACCOUNT_ID` | A credential used to integrate to Adobe I/O. | `D42AEVJZTTJC6LZADUBVPA15@techacct.adobe.com` |
| `IMS` | The Identity Management System (IMS) provides the framework for authentication to Adobe services. With regards to [!DNL Journey Optimizer B2B] and [!DNL Marketo Engage], this value is fixed and is always set to: `ims-na1.adobelogin.com`. | `ims-na1.adobelogin.com` |
| `IMS_ORG` | A corporate entity that can own or license products and services and allow access to its members. | `ABCEH0D9KX6A7WA7ATQE0TE@adobeOrg` |
| `SANDBOX_NAME` | The name of the virtual sandbox partition that you are using. | `prod` |
| `TENANT_ID` | An ID used to ensure that the resources you create are namespaced properly and are contained within your organization. | `b2bcdpproductiontest` |
| `PLATFORM_URL` | The URL endpoint that you are making API calls to. This value is fixed and is always set to: `http://platform.adobe.io/`. | `http://platform.adobe.io/` |

{style="table-layout:auto"}

### Run the scripts

After the environment values are in place, use the [!DNL Postman] interface to run the script for creating the namespaces and schemas. Select the root folder of the auto-generator utility and then select **[!DNL Run]** from the top header.

![Root folder of the Namespaces and Schemas generator in the Postman UI](./assets/namespaces-schemas-postman-root-folder.png){width="500" zoomable="yes"}

The [!DNL Runner] interface appears. From here, ensure that all the checkboxes are selected and then select **[!DNL Run Namespaces and Schemas Autogeneration Utility]**.

![Postman UI with several requests in the Namespaces and Schemas collection selected.](./assets/namespaces-schemas-postman-run-generator.png){width="800" zoomable="yes"}

A successful request creates the required B2B namespaces and schemas.

## B2B namespaces

Identity namespaces are a component of Experience Platform [[!DNL Identity Service]](https://experienceleague.adobe.com/en/docs/experience-platform/identity/home){target="_blank"} that serve to distinguish the context of an identity. A fully qualified identity includes an identity value and a namespace. See [namespaces overview](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces){target="_blank"} for more information.

B2B namespaces are used in the primary identity of the entity.

| Display Name | Identity Symbol | Identity Type |
| --- | --- | --- |
| B2B Person | `b2b_person` | `CROSS_DEVICE` |
| B2B Account | `b2b_account` | `B2B_ACCOUNT` |
| B2B Opportunity | `b2b_opportunity` | `B2B_OPPORTUNITY` |
| B2B Opportunity Person Relation | `b2b_opportunity_person_relation` | `B2B_OPPORTUNITY_PERSON` |
| B2B Campaign | `b2b_campaign` | `B2B_CAMPAIGN` |
| B2B Campaign Member | `b2b_campaign_member` | `B2B_CAMPAIGN_MEMBER` |
| B2B Marketing List | `b2b_marketing_list` | `B2B_MARKETING_LIST` |
| B2B Marketing List Member | `b2b_marketing_list_member` | `B2B_MARKETING_LIST_MEMBER` |
| B2B Account Person Relation | `b2b_account_person_relation` | `B2B_ACCOUNT_PERSON` |

{style="table-layout:auto"}

## B2B schemas

Experience Platform uses schemas to describe the structure of data in a consistent and reusable way. By defining data consistently across systems, it becomes easier to retain meaning and therefore gain value from data.

Before Experience Platform can ingest data, there must be a schema that describes the data's structure and provides constraints to the type of data that can be contained within each field. Schemas consist of a base class and zero or more schema field groups.

For more information on the schema composition model, including design principles and best practices, see [_Basics of schema composition_](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition){target="_blank"}.

+++ B2B Account

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-account" target="_blank">XDM Business Account</a></td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>XDM Business Account Details</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>accountKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Account</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td><code>extSourceSystemAudit.externalKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>B2B Account</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td><ul><li><code>accountParentKey.sourceKey</code> in XDM Business Account Details field group</li><li>Destination property: <code>/accountKey/sourceKey</code></li><li>Type: one-to-one</li><li>Reference schema: B2B Account</li><li>Namespace: B2B Account</li></ul> </td>
    </tr>
</table>

+++

+++ B2B Person

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/individual-profile">XDM Individual Profile</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td><ul><li>XDM Business Person Details</li><li>XDM Business Person Components</li><li>IdentityMap</li><li>Consent and Preference Details</li></ul> </td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>b2b.personKey.sourceKey</code> in the XDM Business Person Details Field Group</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Person</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td><ol><li><code>extSourceSystemAudit.externalKey.sourceKey</code> of XDM Business Person Details field group</li><li><code>workEmail.address</code> of XDM Business Person Details field group</li></ol></td>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td><ol><li>B2B Person</li><li>Email</li></ol></td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td><ul><li><code>personComponents.sourceAccountKey.sourceKey</code> of XDM Business Person Components field group</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Account</li><li>Namespace: B2B Account</li><li>Destination property: accountKey.sourceKey</li><li>Relationship name from current schema: Account</li><li>Relationship name from reference schema: People</li></ul> </td>
    </tr>
</table>

+++

<!--

+++B2B Opportunity

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-opportunity">XDM Business Opportunity</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>XDM Business Opportunity Details</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>opportunityKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Opportunity</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td><code>extSourceSystemAudit.externalKey.sourceKey</code> in the base class</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>B2B Opportunity</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td><ul><li><code>accountKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Account</li><li>Namespace: B2B Account</li><li>Destination property: <code>accountKey.sourceKey</code></li><li>Relationship name from current schema: Account</li><li>Relationship name from reference schema: Opportunities</li></ul></td>
    </tr>
</table>

+++

+++B2B Opportunity Person Relation

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation">XDM Business Opportunity Person Relation</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>None</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>opportunityPersonKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Opportunity Person Relation</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td> **First relationship**<ul><li><code>personKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Person</li><li>Namespace: B2B Person</li><li>Destination property: <code>b2b.personKey.sourceKey</code></li><li>Relationship name from current schema: Person</li><li>Relationship name from reference schema: Opportunities</li></ul>**Second relationship**<ul><li><code>opportunityKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Opportunity </li><li>Namespace: B2B Opportunity </li><li>Destination property: <code>opportunityKey.sourceKey</code></li><li>Relationship name from current schema: Opportunity</li><li>Relationship name from reference schema: People</li></ul> </td>
    </tr>
</table>


+++

+++B2B Campaign

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-campaign">XDM Business Campaign</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>XDM Business Campaign Details</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>campaignKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Campaign</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td>None</td>
    </tr>
</table>

+++

+++B2B Campaign Member

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-campaign-members">XDM Business Campaign Members</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>XDM Business Campaign Member Details</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>campaignMemberKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Campaign Member</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td>**First relationship**<ul><li><code>personKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Person</li><li>Namespace: B2B Person</li><li>Destination property: <code>b2b.personKey.sourceKey</code></li><li>Relationship name from current schema: Person</li><li>Relationship name from reference schema: Campaigns</li></ul>**Second relationship**<ul><li><code>campaignKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Campaign</li><li>Namespace: B2B Campaign</li><li>Destination property: <code>campaignKey.sourceKey</code></li><li>Relationship name from current schema: Campaign</li><li>Relationship name from reference schema: People</li></ul></td>
    </tr>
</table>

+++B2B Marketing List

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-marketing-list">XDM Business Marketing List</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>None</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>marketingListKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Marketing List</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td>None</td>
    </tr>
</table>

>[!NOTE]
>
>Static List in [!UICONTROL Marketo Engage] is not synced from Salesforce and therefore does not have a secondary identity.

+++

+++B2B Marketing List Member

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members">XDM Business Marketing List Members</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>None</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>marketingListMemberKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Marketing List Member</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td>**First relationship**<ul><li><code>personKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Person</li><li>Namespace: B2B Person</li><li>Destination property: <code>b2b.personKey.sourceKey</code></li><li>Relationship name from current schema: Person</li><li>Relationship name from reference schema: Marketing Lists</li></ul>**Second relationship**<ul><li><code>marketingListKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Marketing List</li><li>Namespace: B2B Marketing List</li><li>Destination property: <code>marketingListKey.sourceKey</code></li><li>Relationship name from current schema: Marketing List</li><li>Relationship name from reference schema: People</li></ul></td>
    </tr>
</table>

>[!NOTE]
>
>Static List member in [!UICONTROL Marketo Engage] is not synced from Salesforce and therefore does not have a secondary identity.

+++

+++B2B Account Person Relation

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-account-person-relation">XDM Business Account Person Relation</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>Identity Map</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>accountPersonKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Account Person Relation</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td>**First relationship**<ul><li><code>personKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Person</li><li>Namespace: B2B Person</li><li>Destination property: <code>b2b.personKey.sourceKey</code></li><li>Relationship name from current schema: People</li><li>Relationship name from reference schema: Account</li></ul>**Second relationship**<ul><li><code>accountKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Account</li><li>Namespace: B2B Account</li><li>Destination property: <code>accountKey.sourceKey</code></li><li>Relationship name from current schema: Account</li><li>Relationship name from reference schema: People</li></ul></td>
    </tr>
</table>

+++
-->
