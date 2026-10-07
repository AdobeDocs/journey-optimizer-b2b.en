---
title: Exported Experience Platform Datasets
description: Reference for the Adobe Experience Platform dataset names and key field paths exported by Adobe Journey Optimizer B2B Edition.
feature: Setup, Data Management
role: Admin
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
    internal-label: Experience Platform
feature_v2:
  - id: f2da1b69-6919-4386-a5d2-9c7b5c9033db
    internal-label: Data management
  - id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
    internal-label: Integrations
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
autotag-review: '2026-09-29T00:00:00.000Z'
---

# Exported [!DNL Adobe Experience Platform] datasets {#aep-export-datasets}

[!DNL Adobe Journey Optimizer B2B Edition] exports Data Hub data into [!DNL Adobe Experience Platform] datasets using this naming pattern:

**`AJOB2B-<datasetVersion>-<entity>`**

The following datasets are the current export contract. Use them as the canonical reference for dataset names, entity purpose, and key field paths. Each dataset is marked as either _Standard XDM_ (uses a full Adobe-standard XDM class and field groups) or _Relational_ (simplified XDM schema modeled as a flat record).

For the namespace and schema setup that supports these exports, see [B2B namespaces and schemas](./namespaces-schemas.md).

## Dataset summary {#summary}

| Dataset | Type | Purpose |
|---|---|---|
| `AJOB2B-1_5_1-person` | Standard XDM | Person profile with identity and consent. |
| `AJOB2B-1_5_4-account_relational` | Relational | Account profile and account attributes. |
| `AJOB2B-1_5_4-person_relational` | Relational | Person profile and contact attributes. |
| `AJOB2B-1_5_4-account_member` | Relational | Account-to-person relationship rows. |
| `AJOB2B-1_5_4-account_person` | Relational | Account-person relationship rows. |
| `AJOB2B-1_5_4-buying_group` | Relational | Buying group records and scores. |
| `AJOB2B-1_5_4-buying_group_member` | Relational | Buying group membership rows. |
| `AJOB2B-1_5_4-account_journey` | Relational | Account journey metadata. |
| `AJOB2B-1_5_4-person_journey` | Relational | Person journey metadata. |
| `AJOB2B-1_5_4-account_journey_member` | Relational | Account journey membership rows. |
| `AJOB2B-1_5_4-person_journey_member` | Relational | Person journey membership rows. |
| `AJOB2B-1_5_4-account_journey_node` | Relational | Account journey node metadata. |
| `AJOB2B-1_5_4-person_journey_node` | Relational | Person journey node metadata. |
| `AJOB2B-1_5_4-journey_node` | Relational | Generic journey node rows for both account and person journeys. |
| `AJOB2B-1_5_4-account_event` | Relational | Account journey activity events. |
| `AJOB2B-1_5_4-buying_group_event` | Relational | Buying group lifecycle events. |
| `AJOB2B-1_5-person_event` | Standard XDM | Person activity events, such as email, web, and journey activity. |
| `AJOB2B-1_5_4-person_event_relational` | Relational | Relational version of person events. |

Across these datasets, a few field conventions repeat:

- `_id` is the record or activity identifier in the relational datasets.
- `lastUpdatedDate` is the standard update timestamp for relational records.
- `timestamp` and `eventType` are the standard event metadata in the event datasets.
- `personID`, `accountID`, `journeyID`, and `buyingGroupID` are the common entity identifiers.
- `identityMap` and `personKey.*` carry identity metadata in the XDM person profile.
- Journey activity rows use `journeyID`, `journeyNodeID`, `previousJourneyNodeID`, and `newJourneyNodeID` to model movement between journey states.

+++Entity relation diagram

![Entity relationship diagram for datasets exported to [!DNL Adobe Experience Platform]](./assets/ajo-b2b-data-model.svg)

+++

## Key dataset contracts {#contracts}

Use the following sections to review the available dataset contracts.

### Person profile: `AJOB2B-1_5_1-person` {#person-profile}

**Type:** Standard XDM

| Field path | Description |
|---|---|
| `personID` | Primary person identifier. |
| `personKey.sourceID` | Source system person ID. |
| `personKey.sourceInstanceID` | Sandbox or instance ID. |
| `personKey.sourceType` | Source type, such as `AJOB2B`. |
| `personKey.sourceKey` | Composite source key. |
| `identityMap` | Identity map for person identities. |
| `consents.marketing.email.val` | Email marketing consent. `y` = subscribed, `n` = unsubscribed. |
| `consents.marketing.email.time` | Last consent update timestamp. |
| `consents.marketing.email.reason` | Reason for unsubscribing, when provided. |

### Account profile: `AJOB2B-1_5_4-account_relational` {#account-profile}

**Type:** Relational

| Field path | Description |
|---|---|
| `_id` | Account record ID. |
| `accountName` | Account name. |
| `industry` | Industry classification. |
| `country` | Country. |
| `domainName` | Primary web domain. |
| `annualRevenue` | Annual revenue. |
| `numberOfEmployees` | Number of employees. |
| `createdDate` | Source-system creation timestamp. |
| `customAttributes` | JSON-serialized custom attribute key/value pairs. |
| `isDeleted` | Soft-delete flag. |
| `lastUpdatedDate` | Last modification time. |

### Relational person profile: `AJOB2B-1_5_4-person_relational` {#person-profile-relational}

**Type:** Relational

| Field path | Description |
|---|---|
| `_id` | Person record ID. |
| `email` | Email address. |
| `firstName` | First name. |
| `lastName` | Last name. |
| `jobTitle` | Job title. |
| `personType` | Person type. |
| `isLead` | Whether the person is a lead. |
| `isAnonymous` | Whether the person is anonymous. |
| `sourceType` | CRM source system name. |
| `sourceID` | External CRM record ID. |
| `customAttributes` | JSON-serialized custom attribute key/value pairs. |
| `isDeleted` | Soft-delete flag. |
| `lastUpdatedDate` | Last modification time. |

### Buying group: `AJOB2B-1_5_4-buying_group` {#buying-group}

**Type:** Relational

| Field path | Description |
|---|---|
| `_id` | Buying group record ID. |
| `buyingGroupName` | Buying group name. |
| `accountID` | Related account identifier. |
| `engagementScore` | Engagement score. |
| `completenessScore` | Completeness score. |
| `solutionInterest` | Solution interest label. |
| `buyingGroupStatus` | Current status. |
| `buyingGroupStage` | Buying group stage. |
| `isDeleted` | Soft-delete flag. |
| `lastUpdatedDate` | Last modification time. |

>[!NOTE]
>
>The 1.5.4 export schema includes `buyingGroupStage`, but the current export does not populate it consistently.

### Person events: `AJOB2B-1_5-person_event` {#person-events}

**Type:** Standard XDM

Each row represents a person-level web, email, or other supported activity. The `eventType` identifies the activity, and each event type has its own field set.

#### `directMarketing.emailSent`

This event records an email sent to a person.

| Field path | Description |
|---|---|
| `_id` | Activity instance ID. |
| `eventType` | `directMarketing.emailSent`. |
| `timestamp` | When the activity occurred. |
| `personID` | Person identifier. |
| `personKey.sourceID` | Source person ID. |
| `personKey.sourceType` | Source type. |
| `personKey.sourceInstanceID` | Sandbox or instance ID. |
| `personKey.sourceKey` | Composite person key. |
| `directMarketing.emailSent.mailingKey.sourceID` | Mailing asset ID. |
| `directMarketing.emailSent.mailingKey.sourceType` | Source type. |
| `directMarketing.emailSent.mailingKey.sourceInstanceID` | Instance ID. |
| `directMarketing.emailSent.mailingKey.sourceKey` | Composite mailing key. |
| `directMarketing.emailSent.mailingName` | Mailing name. |
| `_experience.journeyOrchestration.stepEvents.journeyID` | Journey ID, when attributed. |
| `_experience.journeyOrchestration.stepEvents.nodeID` | Journey node ID, when attributed. |

#### `directMarketing.emailDelivered`

This event records email delivery to a person.

| Field path | Description |
|---|---|
| `_id` | Activity instance ID. |
| `eventType` | `directMarketing.emailDelivered`. |
| `timestamp` | When the activity occurred. |
| `personID` | Person identifier. |
| `personKey.sourceID` | Source person ID. |
| `personKey.sourceType` | Source type. |
| `personKey.sourceInstanceID` | Sandbox or instance ID. |
| `personKey.sourceKey` | Composite person key. |
| `directMarketing.mailingKey.sourceID` | Mailing asset ID. |
| `directMarketing.mailingKey.sourceType` | Source type. |
| `directMarketing.mailingKey.sourceInstanceID` | Instance ID. |
| `directMarketing.mailingKey.sourceKey` | Composite mailing key. |
| `directMarketing.mailingName` | Mailing name. |
| `directMarketing.email` | Email address. |
| `_experience.journeyOrchestration.stepEvents.journeyID` | Journey ID, when attributed. |
| `_experience.journeyOrchestration.stepEvents.nodeID` | Journey node ID, when attributed. |

#### `directMarketing.emailUnsubscribed`

This event records an email unsubscribe.

| Field path | Description |
|---|---|
| `_id` | Activity instance ID. |
| `eventType` | `directMarketing.emailUnsubscribed`. |
| `timestamp` | When the activity occurred. |
| `personID` | Person identifier. |
| `personKey.sourceID` | Source person ID. |
| `personKey.sourceType` | Source type. |
| `personKey.sourceInstanceID` | Sandbox or instance ID. |
| `personKey.sourceKey` | Composite person key. |
| `directMarketing.mailingKey.sourceID` | Mailing asset ID. |
| `directMarketing.mailingKey.sourceType` | Source type. |
| `directMarketing.mailingKey.sourceInstanceID` | Instance ID. |
| `directMarketing.mailingKey.sourceKey` | Composite mailing key. |
| `directMarketing.mailingName` | Mailing name. |
| `directMarketing.email` | Email address. |
| `_experience.journeyOrchestration.stepEvents.journeyID` | Journey ID, when attributed. |
| `_experience.journeyOrchestration.stepEvents.nodeID` | Journey node ID, when attributed. |

#### `directMarketing.emailOpened`

This event records an email open.

| Field path | Description |
|---|---|
| `_id` | Activity instance ID. |
| `eventType` | `directMarketing.emailOpened`. |
| `timestamp` | When the activity occurred. |
| `personID` | Person identifier. |
| `personKey.sourceID` | Source person ID. |
| `personKey.sourceType` | Source type. |
| `personKey.sourceInstanceID` | Sandbox or instance ID. |
| `personKey.sourceKey` | Composite person key. |
| `directMarketing.mailingKey.sourceID` | Mailing asset ID. |
| `directMarketing.mailingKey.sourceType` | Source type. |
| `directMarketing.mailingKey.sourceInstanceID` | Instance ID. |
| `directMarketing.mailingKey.sourceKey` | Composite mailing key. |
| `directMarketing.mailingName` | Mailing name. |
| `directMarketing.email` | Email address. |
| `_experience.journeyOrchestration.stepEvents.journeyID` | Journey ID, when attributed. |
| `_experience.journeyOrchestration.stepEvents.nodeID` | Journey node ID, when attributed. |
| `device.isMobileDevice` | Whether the device is mobile. |
| `device.model` | Device or client hint. |
| `environment.browserDetails.userAgent` | User agent. |
| `environment.operatingSystem` | Platform or operating system. |

#### `directMarketing.emailClicked`

This event records a click on a link in an email.

| Field path | Description |
|---|---|
| `_id` | Activity instance ID. |
| `eventType` | `directMarketing.emailClicked`. |
| `timestamp` | When the activity occurred. |
| `personID` | Person identifier. |
| `personKey.sourceID` | Source person ID. |
| `personKey.sourceType` | Source type. |
| `personKey.sourceInstanceID` | Sandbox or instance ID. |
| `personKey.sourceKey` | Composite person key. |
| `directMarketing.mailingKey.sourceID` | Mailing asset ID. |
| `directMarketing.mailingKey.sourceType` | Source type. |
| `directMarketing.mailingKey.sourceInstanceID` | Instance ID. |
| `directMarketing.mailingKey.sourceKey` | Composite mailing key. |
| `directMarketing.mailingName` | Mailing name. |
| `directMarketing.email` | Email address. |
| `directMarketing.linkURL` | Clicked link URL. |
| `_experience.journeyOrchestration.stepEvents.journeyID` | Journey ID, when attributed. |
| `_experience.journeyOrchestration.stepEvents.nodeID` | Journey node ID, when attributed. |
| `device.isMobileDevice` | Whether the device is mobile. |
| `device.model` | Device or client hint. |
| `environment.browserDetails.userAgent` | User agent. |
| `environment.operatingSystem` | Platform or operating system. |

#### `directMarketing.emailBounced`

This event records a bounced email.

| Field path | Description |
|---|---|
| `_id` | Activity instance ID. |
| `eventType` | `directMarketing.emailBounced`. |
| `timestamp` | When the activity occurred. |
| `personID` | Person identifier. |
| `personKey.sourceID` | Source person ID. |
| `personKey.sourceType` | Source type. |
| `personKey.sourceInstanceID` | Sandbox or instance ID. |
| `personKey.sourceKey` | Composite person key. |
| `directMarketing.mailingKey.sourceID` | Mailing asset ID. |
| `directMarketing.mailingKey.sourceType` | Source type. |
| `directMarketing.mailingKey.sourceInstanceID` | Instance ID. |
| `directMarketing.mailingKey.sourceKey` | Composite mailing key. |
| `directMarketing.mailingName` | Mailing name. |
| `directMarketing.email` | Email address. |
| `directMarketing.emailBouncedCode` | Bounce category or code. |
| `directMarketing.emailBouncedDetails` | Bounce details. |
| `_experience.journeyOrchestration.stepEvents.journeyID` | Journey ID, when attributed. |
| `_experience.journeyOrchestration.stepEvents.nodeID` | Journey node ID, when attributed. |

#### `directMarketing.emailBouncedSoft`

This event records a soft email bounce.

| Field path | Description |
|---|---|
| `_id` | Activity instance ID. |
| `eventType` | `directMarketing.emailBouncedSoft`. |
| `timestamp` | When the activity occurred. |
| `personID` | Person identifier. |
| `personKey.sourceID` | Source person ID. |
| `personKey.sourceType` | Source type. |
| `personKey.sourceInstanceID` | Sandbox or instance ID. |
| `personKey.sourceKey` | Composite person key. |
| `directMarketing.mailingKey.sourceID` | Mailing asset ID. |
| `directMarketing.mailingKey.sourceType` | Source type. |
| `directMarketing.mailingKey.sourceInstanceID` | Instance ID. |
| `directMarketing.mailingKey.sourceKey` | Composite mailing key. |
| `directMarketing.mailingName` | Mailing name. |
| `directMarketing.email` | Email address. |
| `directMarketing.emailBouncedCode` | Bounce category or code. |
| `directMarketing.emailBouncedDetails` | Bounce details. |
| `_experience.journeyOrchestration.stepEvents.journeyID` | Journey ID, when attributed. |
| `_experience.journeyOrchestration.stepEvents.nodeID` | Journey node ID, when attributed. |

#### `web.webpagedetails.pageViews`

This event records a person viewing a web page.

| Field path | Description |
|---|---|
| `_id` | Activity instance ID. |
| `eventType` | `web.webpagedetails.pageViews`. |
| `timestamp` | When the activity occurred. |
| `personID` | Person identifier. |
| `personKey.sourceID` | Source person ID. |
| `personKey.sourceType` | Source type. |
| `personKey.sourceInstanceID` | Sandbox or instance ID. |
| `personKey.sourceKey` | Composite person key. |
| `web.webPageDetails.webPageKey.sourceID` | Page asset ID. |
| `web.webPageDetails.webPageKey.sourceType` | Source type. |
| `web.webPageDetails.webPageKey.sourceInstanceID` | Instance ID. |
| `web.webPageDetails.webPageKey.sourceKey` | Composite page key. |
| `web.webPageDetails.name` | Page name. |
| `web.webPageDetails.URL` | Page URL. |
| `web.webPageDetails.queryParameters` | Query string. |
| `web.webPageDetails.webPageID` | Page ID. |
| `environment.browserDetails.userAgent` | User agent. |
| `web.webReferrer.URL` | Referrer URL. |

#### `web.webinteraction.linkClicks`

This event records a person clicking a link on a web page.

| Field path | Description |
|---|---|
| `_id` | Activity instance ID. |
| `eventType` | `web.webinteraction.linkClicks`. |
| `timestamp` | When the activity occurred. |
| `personID` | Person identifier. |
| `personKey.sourceID` | Source person ID. |
| `personKey.sourceType` | Source type. |
| `personKey.sourceInstanceID` | Sandbox or instance ID. |
| `personKey.sourceKey` | Composite person key. |
| `web.webInteraction.webInteractionKey.sourceID` | Interaction asset ID. |
| `web.webInteraction.webInteractionKey.sourceType` | Source type. |
| `web.webInteraction.webInteractionKey.sourceInstanceID` | Instance ID. |
| `web.webInteraction.webInteractionKey.sourceKey` | Composite interaction key. |
| `web.webInteraction.linkID` | Link ID. |
| `web.webInteraction.linkURL` | Destination URL. |
| `web.webPageDetails.queryParameters` | Query string. |
| `web.webPageDetails.webPageID` | Page ID. |
| `environment.browserDetails.userAgent` | User agent. |
| `web.webReferrer.URL` | Referrer URL. |

#### `web.formFilledOut`

This event records a person submitting a web form.

| Field path | Description |
|---|---|
| `_id` | Activity instance ID. |
| `eventType` | `web.formFilledOut`. |
| `timestamp` | When the activity occurred. |
| `personID` | Person identifier. |
| `personKey.sourceID` | Source person ID. |
| `personKey.sourceType` | Source type. |
| `personKey.sourceInstanceID` | Sandbox or instance ID. |
| `personKey.sourceKey` | Composite person key. |
| `web.fillOutForm.webFormKey.sourceID` | Form asset ID. |
| `web.fillOutForm.webFormKey.sourceType` | Source type. |
| `web.fillOutForm.webFormKey.sourceInstanceID` | Instance ID. |
| `web.fillOutForm.webFormKey.sourceKey` | Composite form key. |
| `web.fillOutForm.webFormID` | Form ID. |
| `web.fillOutForm.webFormName` | Form name. |
| `web.webPageDetails.queryParameters` | Query string. |
| `web.webPageDetails.webPageID` | Page ID. |
| `environment.browserDetails.userAgent` | User agent. |
| `web.webReferrer.URL` | Referrer URL. |

#### `leadOperation.interestingMoment`

This event records an interesting moment associated with a person.

| Field path | Description |
|---|---|
| `_id` | Activity instance ID. |
| `eventType` | `leadOperation.interestingMoment`. |
| `timestamp` | When the activity occurred. |
| `personID` | Person identifier. |
| `personKey.sourceID` | Source person ID. |
| `personKey.sourceType` | Source type. |
| `personKey.sourceInstanceID` | Sandbox or instance ID. |
| `personKey.sourceKey` | Composite person key. |
| `leadOperation.interestingMoment.date` | Moment date and time. |
| `leadOperation.interestingMoment.description` | Description. |
| `leadOperation.interestingMoment.source` | Source label. |
| `leadOperation.interestingMoment.type` | Type label. |
| `_experience.journeyOrchestration.stepEvents.journeyID` | Journey ID, when attributed. |
| `_experience.journeyOrchestration.stepEvents.nodeID` | Journey node ID, when attributed. |

### Relational person events: `AJOB2B-1_5_4-person_event_relational` {#relational-person-events}

Rows represent supported person activities: web, email, journey, and interesting-moment events. Interpret each row with `eventType` and `activityTypeID`. Only fields for that event type are populated. Some rows have a null `_id`.

**Type:** Relational

The dataset contains multiple activity types. The following table lists the union of fields across those types. Each row populates only the fields relevant to its `eventType` and `activityTypeID`.

>[!NOTE]
>
>`_id` The schema requires it, but the 1.5.4 query reads it only from the Kafka `record_content` payload. For MLM-sourced activity rows that payload is null, so `_id` is null as well.

Journey-attribution fields (`journeyID`, `journeyNodeID`, `journeyStepID`, and others) are populated for journey events: `person.journeyAdd`, `person.journeyRemove`, `person.journeyStart`, `person.journeyEnd`, `person.journeyNodeTransition`, and `person.journeySplitNode`.

These fields are also populated for `person.attributeChanged` events fired by a journey **[!UICONTROL Update person profile]** node.

Attribute-change fields (`attributeName`, `attributeID`, `attributeNewValue`, `attributeOldValue`, `attributeChangeReason`) are populated for `person.attributeChanged` only.

| Field path | Description |
|------------|-------------|
| `_id` | Activity instance id ([!DNL Adobe Marketo Engage] `activityKey`). |
| `timestamp` | When the activity occurred. |
| `eventType` | XDM event type string. Values: `web.webpagedetails.pageViews`, `web.formFilledOut`, `web.webinteraction.linkClicks`, `directMarketing.emailSent`, `directMarketing.emailDelivered`, `directMarketing.emailBounced`, `directMarketing.emailBouncedSoft`, `directMarketing.emailUnsubscribed`, `directMarketing.emailOpened`, `directMarketing.emailClicked`, `leadOperation.interestingMoment`, `person.attributeChanged`, `person.journeyAdd`, `person.journeyRemove`, `person.journeyStart`, `person.journeyEnd`, `person.journeyNodeTransition`, `person.journeySplitNode`. |
| `activityTypeID` | Numeric [!DNL Adobe Marketo Engage] activity type id (as string). |
| `personID` | Composite source key of the person. Marked as identity in namespace `b2b_person`. |
| `journeyID` | Composite source key of the journey (null for non-journey events). |
| `journeyNodeID` | Composite source key of the journey node (null for non-journey events). |
| `previousJourneyNodeID` | Prior journey node (populated for `person.journeyNodeTransition` and `person.journeySplitNode`). |
| `newJourneyNodeID` | Destination journey node id (`person.journeyNodeTransition` and `person.journeySplitNode`). Usually equals `journeyNodeID`. |
| `journeyStepID` | Runtime step / node id inside the journey definition (populated on journey activities). |
| `journeyChoiceNumber` | Split-choice number for `person.journeySplitNode`. Integer. |
| `journeyEntryCount` | Number of times this person has entered the journey (populated on journey add / start events). Integer. |
| `journeyProgramID` | Program (journey) id emitting the activity. |
| `activitySource` | Producer label, such as `[!DNL Adobe Journey Optimizer B2B Edition]` or `[!DNL Adobe Marketo Engage] Flow Action`. |
| `campaignID` | [!DNL Adobe Marketo Engage] campaign id when the activity is campaign-attributed. |
| `attributeName` | Attribute label whose value changed (`person.attributeChanged` only). |
| `attributeID` | Attribute id whose value changed (`person.attributeChanged` only). |
| `attributeNewValue` | New attribute value, coerced to string (`person.attributeChanged` only). |
| `attributeOldValue` | Prior attribute value, coerced to string (`person.attributeChanged` only). |
| `attributeChangeReason` | Reason label for the change (`person.attributeChanged` only). |
| `assetID` | Primary asset id (mailing/page/form id). |
| `assetName` | Primary asset name. |
| `recipientEmail` | Recipient email address. Only activity types **27** (Email Soft Bounce) and **48** (Sales Email Soft Bounce) populate this field. They are the only two of the 12 `directMarketing.email*` activity types whose raw [!DNL Adobe Marketo Engage] payload includes the recipient address. Activity type 8 (hard bounce) shares the `directMarketing.emailBounced` event type with type 48, but its payload does not include the Email attribute. Use `activityTypeID` to distinguish these records. Other email activity types, including sent, delivered, opened, clicked, unsubscribed, hard-bounced, and their sales-email variants, do not provide the recipient address. Join this dataset to `person` or `person_relational` on `personID` to retrieve it. `assetName` contains the email template or asset name, not the recipient address. |
| `bouncedCode` | Bounce category code (emailBounced / emailBouncedSoft only). |
| `bouncedDetails` | Detailed bounce reason (emailBounced / emailBouncedSoft only). |
| `isMobileDevice` | Mobile device flag (emailOpened / emailClicked only). |
| `deviceModel` | Device model (emailOpened / emailClicked only). |
| `operatingSystem` | OS or platform (emailOpened / emailClicked only). |
| `userAgent` | Browser or client user agent (email opens/clicks and all web events). |
| `clickedLinkUrl` | Clicked email link URL (emailClicked only). |
| `webPageUrl` | Web page URL (`web.webpagedetails.pageViews` only). |
| `queryParameters` | URL query parameters (pageViews, formFilledOut, linkClicks). |
| `webPageID` | [!DNL Adobe Marketo Engage] web page id (pageViews, formFilledOut, linkClicks). |
| `referrerUrl` | Referrer URL (pageViews, formFilledOut, linkClicks). |
| `formID` | [!DNL Adobe Marketo Engage] form id (`web.formFilledOut` only). |
| `linkID` | [!DNL Adobe Marketo Engage] link id (`web.webinteraction.linkClicks` only). |
| `interestingMomentDate` | Moment date (`leadOperation.interestingMoment` only). |
| `interestingMomentDescription` | Free-text description (interestingMoment only). |
| `interestingMomentSource` | Source / campaign (interestingMoment only). |
| `interestingMomentType` | Category / type (interestingMoment only). |
| `isDeleted` | Soft-delete flag. |
| `lastUpdatedDate` | Last modification time. |

#### Field reference by activity type

The preceding table lists all columns across the activity types in this dataset. Each row contains values only in columns relevant to its `activityTypeID`. Activity types 8 and 48 both emit `directMarketing.emailBounced`, so `eventType` alone cannot differentiate them. The following tables are organized by `activityTypeID` and include the corresponding `eventType`.

##### `web.webpagedetails.pageViews` (Activity type 1)

This activity records a person viewing a web page.

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `assetID` | Page id. |
| `assetName` | Page name. |
| `webPageUrl` | Page URL. |
| `queryParameters` | Query string. |
| `webPageID` | [!DNL Adobe Marketo Engage] web page id. |
| `referrerUrl` | Referrer URL. |
| `userAgent` | Browser or client user agent. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |

##### `web.formFilledOut` (Activity type 2)

This activity records a person submitting a web form.

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `assetID` | Form id. |
| `assetName` | Form name. |
| `formID` | [!DNL Adobe Marketo Engage] form id. |
| `queryParameters` | Query string. |
| `webPageID` | [!DNL Adobe Marketo Engage] web page id. |
| `referrerUrl` | Referrer URL. |
| `userAgent` | Browser or client user agent. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |

##### `web.webinteraction.linkClicks` (Activity type 3)

This activity records a person clicking a link on a web page.

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `assetID` | Interaction / link id. |
| `assetName` | Destination URL. |
| `linkID` | [!DNL Adobe Marketo Engage] link id. |
| `queryParameters` | Query string. |
| `webPageID` | [!DNL Adobe Marketo Engage] web page id. |
| `referrerUrl` | Referrer URL. |
| `userAgent` | Browser or client user agent. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |

##### `directMarketing.emailSent` (Activity types 6, 39)

This activity records an email sent to a person.

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `assetID` | Mailing id. |
| `assetName` | Mailing name. |
| `campaignID` | [!DNL Adobe Marketo Engage] campaign id, when campaign-attributed. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |

##### `directMarketing.emailDelivered` (Activity types 7, 45)

This activity records an email delivered to a person.

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `assetID` | Mailing id. |
| `assetName` | Mailing name. |
| `campaignID` | [!DNL Adobe Marketo Engage] campaign id, when campaign-attributed. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |

##### `directMarketing.emailUnsubscribed` (Activity type 9)

This activity records a person unsubscribing from email.

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `assetID` | Mailing id. |
| `assetName` | Mailing name. |
| `campaignID` | [!DNL Adobe Marketo Engage] campaign id, when campaign-attributed. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |

##### `directMarketing.emailOpened` (Activity types 10, 40)

This activity records a person opening an email.

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `assetID` | Mailing id. |
| `assetName` | Mailing name. |
| `isMobileDevice` | Mobile device flag. |
| `deviceModel` | Device model. |
| `operatingSystem` | OS or platform. |
| `userAgent` | Browser or client user agent. |
| `campaignID` | [!DNL Adobe Marketo Engage] campaign id, when campaign-attributed. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |

##### `directMarketing.emailClicked` (Activity types 11, 41)

This activity records a person clicking a link in an email.

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `assetID` | Mailing id. |
| `assetName` | Mailing name. |
| `clickedLinkUrl` | Clicked link URL. |
| `isMobileDevice` | Mobile device flag. |
| `deviceModel` | Device model. |
| `operatingSystem` | OS or platform. |
| `userAgent` | Browser or client user agent. |
| `campaignID` | [!DNL Adobe Marketo Engage] campaign id, when campaign-attributed. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |

##### `directMarketing.emailBounced`: hard bounce (Activity type 8)

This activity records a hard bounce for an email sent to a person.

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `assetID` | Mailing id. |
| `assetName` | Mailing name. |
| `bouncedCode` | Bounce category code. |
| `bouncedDetails` | Detailed bounce reason. |
| `campaignID` | [!DNL Adobe Marketo Engage] campaign id, when campaign-attributed. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |

This activity type shares the `directMarketing.emailBounced` event type with activity type 48. Its raw payload does not include the Email attribute, so it has no `recipientEmail` value. Use `activityTypeID` to distinguish the two types.

##### `directMarketing.emailBounced`: sales email soft bounce (Activity type 48)

This activity records a soft bounce for a sales email.

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `assetID` | Mailing id. |
| `assetName` | Mailing name. |
| `recipientEmail` | Recipient email address. |
| `bouncedCode` | Bounce category code. |
| `bouncedDetails` | Detailed bounce reason. |
| `campaignID` | [!DNL Adobe Marketo Engage] campaign id, when campaign-attributed. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |

##### `directMarketing.emailBouncedSoft` (Activity type 27)

This activity records a soft bounce for a marketing email.

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `assetID` | Mailing id. |
| `assetName` | Mailing name. |
| `recipientEmail` | Recipient email address. |
| `bouncedCode` | Bounce category code. |
| `bouncedDetails` | Detailed bounce reason. |
| `campaignID` | [!DNL Adobe Marketo Engage] campaign id, when campaign-attributed. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |

##### `leadOperation.interestingMoment` (Activity type 46)

This activity records an interesting moment associated with a person.

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `interestingMomentDate` | Moment date/time. |
| `interestingMomentDescription` | Free-text description. |
| `interestingMomentSource` | Source label. |
| `interestingMomentType` | Type label. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |

`assetID` / `assetName` are not populated for this activity type.

##### `person.attributeChanged` (Activity type 13)

This activity records an attribute change triggered by a journey.

This event is exported only when a journey's **[!UICONTROL Update person profile]** node fires it. Unattached type 13 rows are filtered out to avoid sending unrelated attribute changes to [!DNL Adobe Experience Platform].

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `attributeName` | Attribute label whose value changed. |
| `attributeID` | Attribute id whose value changed. |
| `attributeNewValue` | New attribute value, coerced to string. |
| `attributeOldValue` | Prior attribute value, coerced to string. |
| `attributeChangeReason` | Reason label for the change. |
| `journeyID` | Journey identifier. |
| `journeyNodeID` | Journey node identifier. |
| `journeyStepID` | Runtime journey step id. |
| `journeyProgramID` | Journey program id. |
| `activitySource` | Producer label. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |

##### `person.journeyAdd`, `person.journeyStart` (Activity types 182, 184)

These activities record a person being added to or starting a journey.

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `journeyID` | Journey identifier. |
| `journeyNodeID` | Journey node identifier. |
| `journeyStepID` | Runtime journey step id. |
| `journeyEntryCount` | Number of times this person has entered the journey. |
| `journeyProgramID` | Journey program id. |
| `activitySource` | Producer label. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |

##### `person.journeyRemove`, `person.journeyEnd` (Activity types 183, 185)

These activities record a person being removed from or ending a journey.

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `journeyID` | Journey identifier. |
| `journeyNodeID` | Journey node identifier. |
| `journeyStepID` | Runtime journey step id. |
| `journeyProgramID` | Journey program id. |
| `activitySource` | Producer label. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |

##### `person.journeySplitNode` (Activity type 186)

This activity records the branch a person takes at a journey split node.

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `journeyID` | Journey identifier. |
| `journeyNodeID` | Journey node identifier (the split node). |
| `previousJourneyNodeID` | Node the person was at before the split. |
| `newJourneyNodeID` | Node the person moved to (usually equals `journeyNodeID`). |
| `journeyStepID` | Runtime journey step id. |
| `journeyChoiceNumber` | Which branch of the split was taken. |
| `journeyProgramID` | Journey program id. |
| `activitySource` | Producer label. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |

##### `person.journeyNodeTransition` (Activity type 600)

This activity records a person transitioning between journey nodes.

| Field path | Description |
|------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Common fields. |
| `journeyID` | Journey identifier. |
| `journeyNodeID` | Current journey node identifier. |
| `previousJourneyNodeID` | Node the person transitioned from. |
| `newJourneyNodeID` | Node the person transitioned to (usually equals `journeyNodeID`). |
| `journeyStepID` | Runtime journey step id. |
| `journeyProgramID` | Journey program id. |
| `activitySource` | Producer label. |
| `isDeleted`, `lastUpdatedDate` | Common fields. |



## Customer-owned datasets {#customer-owned-datasets}

Some customer records are written to a customer-owned [!DNL Adobe Experience Platform] dataset instead of one of the standard [!DNL Adobe Journey Optimizer B2B Edition] datasets. Those dataset names and field lists vary by customer. Only the standardized identity values are consistent across implementations.
