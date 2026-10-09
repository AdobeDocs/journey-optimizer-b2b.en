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

# Exported [!DNL Experience Platform] datasets

[!DNL Adobe Journey Optimizer B2B Edition] makes account, person, buying group, and journey information available in [!DNL Adobe Experience Platform]. A dataset is a collection of related records. For example, a person dataset describes people, a membership dataset connects people to accounts or journeys, and an event dataset records actions such as opening an email.

Use this guide to understand what each dataset contains, what its fields mean, and how related records connect. Dataset names follow this pattern:

**`AJOB2B-<datasetVersion>-<entity>`**

Here, `<entity>` describes the information, such as `person`, `account_relational`, or `person_event`. `<datasetVersion>` identifies the version of the dataset's field definitions. The section headings show the documented names; your [!DNL Experience Platform] environment may also contain older versions.

For the namespace and schema setup that supports these exports, see [B2B namespaces and schemas](./namespaces-schemas.md).

>[!NOTE]
>
>Adobe retains older dataset versions to avoid disrupting existing use. As a result, you might find multiple versions of the same dataset in your sandbox. If you no longer use an older dataset, you can request that Adobe remove it. Before requesting removal, confirm that the dataset is no longer in use.

## Reading this guide

- **Field name:** the exact name you see in [!DNL Experience Platform]. Dots separate levels within a field, such as `consents.marketing.email.val`.
- **Record ID:** identifies the record in that dataset.
- **Relationship:** names the dataset and field that the identifier matches. For example, `Matches AJOB2B-1_5_4-buying_group (_id)` means the field refers to a buying group's `_id`. Match the complete identifier; do not shorten it or try to rebuild it.
- **Standard Adobe format:** uses Adobe's shared field definitions.
- **Related-record format:** organizes information as records you can connect using matching identifiers.

For example, `buying_group_member.buyingGroupID` matches `buying_group._id`, and its `personID` matches `person_relational._id` or the Person dataset's `personKey.sourceKey`. These links help you understand who belongs to a buying group. [!DNL Experience Platform] does not automatically create reports or audiences from the links alone.

Some identifiers refer to information that has no separate dataset in this guide, such as a marketing program. The Relationship column notes this instead of naming a dataset that does not exist here.

`isDeleted` is `true` when the record is marked as deleted and `false` when it is not. Do not treat it as a general active-member or consent indicator. `lastUpdatedDate` describes the record's latest data update; for events, use `timestamp` to understand when the activity happened. A blank field means that information is unavailable or does not apply to that record.

The related-record datasets use version `1_5_4`. Where a field is not currently populated or needs special handling, the relevant section explains the customer-visible limitation.

An audience is a group of people who meet selected criteria. Availability for audience creation depends on your [!DNL Experience Platform] setup for combining information into person profiles. A dataset's presence in [!DNL Experience Platform] does not, by itself, mean it is available for segmentation.

## Choosing a dataset

| What you want to understand | Datasets to look for |
|---|---|
| People and their email preferences | `person` |
| Account details and person contact details | `account_relational`, `person_relational` |
| Which people are associated with an account | `account_member`, `account_person` |
| Buying groups, their members, and status changes | `buying_group`, `buying_group_member`, `buying_group_event` |
| Account journeys and participating accounts | `account_journey`, `account_journey_member`, `account_event` |
| Person journeys and participating people | `person_journey`, `person_journey_member` |
| Steps within a journey | `account_journey_node`, `person_journey_node`, `journey_node` |
| Email, web, and other supported person activities | `person_event`, `person_event_relational` |

The following sections provide the full dataset names and field details. A journey describes the overall experience; a membership connects a person or account to that journey; an event describes something that happened.

+++Entity relation diagram

![Entity relationship diagram for datasets exported to [!DNL Adobe Experience Platform]](./assets/ajo-b2b-data-model.svg)

+++

## `AJOB2B-1_5_1-person`

Each record describes a person, their identifiers, and their email marketing preference. Use it for person-level reporting and, where Profile is configured, to help build audiences.

**Format:** Standard Adobe format

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `personID` | Record ID | Identifier for the person. Use the complete value to match related records. |
| `personKey.sourceID` |  | Person identifier in the connected system. |
| `personKey.sourceInstanceID` |  | Identifier of the [!DNL Experience Platform] environment or connected account. |
| `personKey.sourceType` |  | Name of the connected product. |
| `personKey.sourceKey` |  | Complete person identifier used to match related records. |
| `identityMap` |  | Other identifiers that help [!DNL Experience Platform] recognize the same person across your connected data. |
| `consents.marketing.email.val` |  | Email marketing preference: `n` indicates an opt-out; `y` indicates no opt-out recorded in this field. This field alone does not establish permission to send marketing email. |
| `consents.marketing.email.time` |  | Date and time when the email preference was last updated. |
| `consents.marketing.email.reason` |  | Reason for the opt-out, when provided (only set when unsubscribed). |
| `isDeleted` |  | Whether this person record is marked as deleted. |

>[!NOTE]
>
>Your organization may have additional person fields beyond those listed here.

When your organization uses its own configured account or person datasets, those records can also include `isDeleted`. See [Customer-owned datasets](#customer-owned-datasets).

## `AJOB2B-1_5_4-account_member`

Each record links one account to one person. Use this dataset to report which people are associated with each account; it describes the relationship rather than either profile.

**Format:** Related-record format

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Relationship record id. |
| `accountID` | Matches `AJOB2B-1_5_4-account_relational` (`_id`) | Account identifier. |
| `personID` | Matches `AJOB2B-1_5_4-person_relational` (`_id`) | Person identifier. |
| `isDeleted` |  | Whether this record is marked as deleted. |
| `lastUpdatedDate` |  | Last modification time. |

## `AJOB2B-1_5_4-buying_group`

Each record describes a buying group associated with an account, including its name, status, solution interest, and engagement and completeness scores. The buying-group stage is not currently populated.

**Format:** Related-record format

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Buying group record id (use the complete value). |
| `buyingGroupName` |  | Buying group name. |
| `engagementScore` |  | Engagement score. |
| `completenessScore` |  | Completeness score. |
| `accountID` | Matches `AJOB2B-1_5_4-account_relational` (`_id`) | Related account identifier. |
| `solutionInterest` |  | Solution interest label. |
| `buyingGroupStatus` |  | Status. |
| `buyingGroupStage` |  | Buying group stage name. |
| `isDeleted` |  | Whether this record is marked as deleted. |
| `lastUpdatedDate` |  | Last modification time. |

>[!NOTE]
>
>**Availability note:** `buyingGroupStage` is currently blank. Do not use it to filter or group buying groups by stage.

## `AJOB2B-1_5_4-buying_group_member`

Each record links a person to a buying group and records that person's role. Use it to report buying-group composition and role coverage.

`isDeleted` does not always indicate whether a person has been removed from a buying group. Do not use this field alone to determine current membership. The role name can be blank when no role information is available.

**Format:** Related-record format

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Membership record id. |
| `buyingGroupID` | Matches `AJOB2B-1_5_4-buying_group` (`_id`) | Buying group identifier. |
| `personID` | Matches `AJOB2B-1_5_4-person_relational` (`_id`) | Person identifier. |
| `buyingGroupMemberRole` |  | Role name, when available. |
| `isDeleted` |  | Whether this record is marked as deleted. |
| `lastUpdatedDate` |  | Last modification time. |

## `AJOB2B-1_5_4-account_journey`

Each record describes an account journey, with its name, status, and start and end dates. Use it to report journey lifecycle and status for accounts.

**Format:** Related-record format

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Journey record id (use the complete value). |
| `accountJourneyName` |  | Journey name. |
| `accountJourneyStatus` |  | Status (e.g. draft, live, finished). |
| `startDate` |  | Start timestamp. |
| `endDate` |  | End timestamp. |
| `isDeleted` |  | Whether this record is marked as deleted. |
| `lastUpdatedDate` |  | Last modification time. |

## `AJOB2B-1_5_4-account_journey_member`

Each record connects an account with an account journey. Use it to identify and report which accounts are participating in each journey.

**Format:** Related-record format

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Membership record id. |
| `accountID` | Matches `AJOB2B-1_5_4-account_relational` (`_id`) | Account identifier. |
| `journeyID` | Matches `AJOB2B-1_5_4-account_journey` (`_id`) | Account journey identifier. |
| `isDeleted` |  | Whether this record is marked as deleted. |
| `lastUpdatedDate` |  | Last modification time. |

## `AJOB2B-1_5_4-person_journey`

Each record describes a person journey, with its name, status, and start and end dates. Use it to report journey lifecycle and status for person-focused journeys.

**Format:** Related-record format

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Journey record id (use the complete value). |
| `personJourneyName` |  | Journey name. |
| `personJourneyStatus` |  | Status (e.g. draft, live, finished). |
| `startDate` |  | Start timestamp. |
| `endDate` |  | End timestamp. |
| `isDeleted` |  | Whether this record is marked as deleted. |
| `lastUpdatedDate` |  | Last modification time. |

## `AJOB2B-1_5_4-person_journey_member`

Each record describes a person's membership in a journey, including the current journey node, membership and entry dates, and entry count. Use it to report enrollment, re-entry, and journey progress.

**Format:** Related-record format

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Membership record id. |
| `marketingProgramID` |  | Marketing program identifier the journey belongs to. |
| `personID` | Matches `AJOB2B-1_5_4-person_relational` (`_id`) | Person identifier. |
| `journeyID` | Matches `AJOB2B-1_5_4-person_journey` (`_id`) | Journey identifier. |
| `journeyNodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Identifier of the journey node the person is currently at. |
| `membershipDate` |  | When the person became a member of the marketing program. |
| `lastEntryDate` |  | When the person last entered the journey. |
| `reentryOpensAt` |  | When the person can re-enter the journey. |
| `entryCount` |  | Count of times the person has entered the journey. |
| `createdDate` |  | When the record was created. |
| `updatedDate` |  | When the record was last changed. |
| `isDeleted` |  | Whether this record is marked as deleted. |
| `lastUpdatedDate` |  | Last modification time. |

## `AJOB2B-1_5_4-account_journey_node`

Each record describes a step in a journey, including the kind of step and the journey it belongs to. A journey node is a step such as a start, wait, or decision. The same steps can appear in `person_journey_node`; match `accountJourneyID` to an account journey before treating a step as account-specific.

**Format:** Related-record format

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Node record id (use the complete value). |
| `accountJourneyID` | Matches `AJOB2B-1_5_4-account_journey` (`_id`) | Parent journey identifier. |
| `uuid` |  | Additional identifier for the journey step. |
| `journeyNodeTypeID` |  | Number identifying the kind of journey step. |
| `nodeType` |  | Label identifying the kind of journey step. |
| `isDeleted` |  | Whether this record is marked as deleted. |
| `createdDate` |  | When the record was created. |
| `lastUpdatedDate` |  | Last modification time. |

## `AJOB2B-1_5_4-person_journey_node`

Each record describes a step in a journey, including the kind of step and the journey it belongs to. The same steps can appear in `account_journey_node`; match `personJourneyID` to a person journey before treating a step as person-specific.

**Format:** Related-record format

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Node record id (use the complete value). |
| `personJourneyID` | Matches `AJOB2B-1_5_4-person_journey` (`_id`) | Parent journey identifier. |
| `uuid` |  | Additional identifier for the journey step. |
| `journeyNodeTypeID` |  | Number identifying the kind of journey step. |
| `nodeType` |  | Label identifying the kind of journey step. |
| `isDeleted` |  | Whether this record is marked as deleted. |
| `createdDate` |  | When the record was created. |
| `lastUpdatedDate` |  | Last modification time. |

## `AJOB2B-1_5_4-account_event`

Each record captures an account journey event: an account being added to or removed from a journey, or moving between journey nodes. Use `eventType` and `timestamp` to build an account activity timeline; `buyingGroupID` is available when the event is buying-group attributed.

**Format:** Related-record format

`eventType` provides information about what happened. The following tables describe the fields for each kind of activity.

`lastUpdatedDate` is not currently populated for these events. Use `timestamp` for the activity date.

### Account added to a journey (`account.addAccountToJourney`)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Activity identifier. |
| `eventType` |  | `account.addAccountToJourney`. |
| `timestamp` |  | When the activity occurred. |
| `accountID` | Matches `AJOB2B-1_5_4-account_relational` (`_id`) | Account identifier. |
| `journeyID` | Matches `AJOB2B-1_5_4-account_journey` (`_id`) | Journey identifier. |
| `journeyNodeID` | Matches `AJOB2B-1_5_4-account_journey_node` (`_id`) | Journey node identifier. |
| `buyingGroupID` | Matches `AJOB2B-1_5_4-buying_group` (`_id`) | Buying group identifier, when the journey add is buying-group attributed. |
| `lastUpdatedDate` |  | Record update time. Currently blank; use timestamp for the activity date. |

### Account removed from a journey (`account.removeAccountFromJourney`)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Activity identifier. |
| `eventType` |  | `account.removeAccountFromJourney`. |
| `timestamp` |  | When the activity occurred. |
| `accountID` | Matches `AJOB2B-1_5_4-account_relational` (`_id`) | Account identifier. |
| `journeyID` | Matches `AJOB2B-1_5_4-account_journey` (`_id`) | Journey identifier. |
| `journeyNodeID` | Matches `AJOB2B-1_5_4-account_journey_node` (`_id`) | Journey node identifier. |
| `buyingGroupID` | Matches `AJOB2B-1_5_4-buying_group` (`_id`) | Buying group identifier, when the journey removal is buying-group attributed. |
| `lastUpdatedDate` |  | Record update time. Currently blank; use timestamp for the activity date. |

### Account moved between journey steps (`account.changeAccountJourneyNode`)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Activity identifier. |
| `eventType` |  | `account.changeAccountJourneyNode`. |
| `timestamp` |  | When the activity occurred. |
| `accountID` | Matches `AJOB2B-1_5_4-account_relational` (`_id`) | Account identifier. |
| `journeyID` | Matches `AJOB2B-1_5_4-account_journey` (`_id`) | Journey identifier. |
| `journeyNodeID` | Matches `AJOB2B-1_5_4-account_journey_node` (`_id`) | Journey node identifier. |
| `previousJourneyNodeID` | Refers to `AJOB2B-1_5_4-account_journey_node` (`_id`); values may not match | Identifier of the previous journey step. This value may not match the corresponding step record; do not rely on it alone to connect records. |
| `buyingGroupID` | Matches `AJOB2B-1_5_4-buying_group` (`_id`) | Buying group identifier, when the node change is buying-group attributed. |
| `lastUpdatedDate` |  | Record update time. Currently blank; use timestamp for the activity date. |

## `AJOB2B-1_5_4-buying_group_event`

Each record captures a change to a buying group's status, including the new status and when it changed. The new-stage field is not currently populated.

**Format:** Related-record format

### Buying-group status changed (`buyingGroup.changeStatus`)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Activity identifier. |
| `eventType` |  | `buyingGroup.changeStatus`. |
| `timestamp` |  | When the activity occurred. |
| `buyingGroupID` | Matches `AJOB2B-1_5_4-buying_group` (`_id`) | Buying group identifier. |
| `newStatus` |  | New status value. |
| `newStage` |  | New buying-group stage. Currently blank. |
| `lastUpdatedDate` |  | Record update time. |

>[!NOTE]
>
>**Availability note:** use `newStatus` to report status changes. Do not use `newStage` to report stage changes, because it is currently blank.

## `AJOB2B-1_5-person_event`

Each record describes a person-level web, email, or other supported activity event. Use `eventType` and `timestamp` to analyze behavior over time, with event-specific details populated only for the matching event type.

**Format:** Standard Adobe format

`eventType` tells you what happened. The following tables describe the fields for each kind of activity. Details that do not apply to an event are blank.

### Email sent (`directMarketing.emailSent`)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Activity identifier. |
| `eventType` |  | `directMarketing.emailSent`. |
| `timestamp` |  | When the activity occurred. |
| `personID` | Matches `AJOB2B-1_5_1-person` (`personID`) | Person identifier. |
| `personKey.sourceID` |  | Person identifier in the connected system. |
| `personKey.sourceType` |  | Name of the connected product. |
| `personKey.sourceInstanceID` |  | Identifier of the [!DNL Experience Platform] environment or connected account. |
| `personKey.sourceKey` |  | Complete person identifier used to match related records. |
| `directMarketing.emailSent.mailingKey.sourceID` |  | Mailing asset id. |
| `directMarketing.emailSent.mailingKey.sourceType` |  | Name of the connected product. |
| `directMarketing.emailSent.mailingKey.sourceInstanceID` |  | Instance id. |
| `directMarketing.emailSent.mailingKey.sourceKey` |  | Complete email-content identifier. |
| `directMarketing.emailSent.mailingName` |  | Mailing name. |
| `_experience.journeyOrchestration.stepEvents.journeyID` | Matches `AJOB2B-1_5_4-person_journey` (`_id`) | Journey id (if attributed). |
| `_experience.journeyOrchestration.stepEvents.nodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Journey node id (if attributed). |

### Email delivered (`directMarketing.emailDelivered`)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Activity identifier. |
| `eventType` |  | `directMarketing.emailDelivered`. |
| `timestamp` |  | When the activity occurred. |
| `personID` | Matches `AJOB2B-1_5_1-person` (`personID`) | Person identifier. |
| `personKey.sourceID` |  | Person identifier in the connected system. |
| `personKey.sourceType` |  | Name of the connected product. |
| `personKey.sourceInstanceID` |  | Identifier of the [!DNL Experience Platform] environment or connected account. |
| `personKey.sourceKey` |  | Complete person identifier used to match related records. |
| `directMarketing.mailingKey.sourceID` |  | Mailing asset id. |
| `directMarketing.mailingKey.sourceType` |  | Name of the connected product. |
| `directMarketing.mailingKey.sourceInstanceID` |  | Instance id. |
| `directMarketing.mailingKey.sourceKey` |  | Complete email-content identifier. |
| `directMarketing.mailingName` |  | Mailing name. |
| `directMarketing.email` |  | Email address. |
| `_experience.journeyOrchestration.stepEvents.journeyID` | Matches `AJOB2B-1_5_4-person_journey` (`_id`) | Journey id (if attributed). |
| `_experience.journeyOrchestration.stepEvents.nodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Journey node id (if attributed). |

### Email unsubscribe (`directMarketing.emailUnsubscribed`)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Activity identifier. |
| `eventType` |  | `directMarketing.emailUnsubscribed`. |
| `timestamp` |  | When the activity occurred. |
| `personID` | Matches `AJOB2B-1_5_1-person` (`personID`) | Person identifier. |
| `personKey.sourceID` |  | Person identifier in the connected system. |
| `personKey.sourceType` |  | Name of the connected product. |
| `personKey.sourceInstanceID` |  | Identifier of the [!DNL Experience Platform] environment or connected account. |
| `personKey.sourceKey` |  | Complete person identifier used to match related records. |
| `directMarketing.mailingKey.sourceID` |  | Mailing asset id. |
| `directMarketing.mailingKey.sourceType` |  | Name of the connected product. |
| `directMarketing.mailingKey.sourceInstanceID` |  | Instance id. |
| `directMarketing.mailingKey.sourceKey` |  | Complete email-content identifier. |
| `directMarketing.mailingName` |  | Mailing name. |
| `directMarketing.email` |  | Email address. |
| `_experience.journeyOrchestration.stepEvents.journeyID` | Matches `AJOB2B-1_5_4-person_journey` (`_id`) | Journey id (if attributed). |
| `_experience.journeyOrchestration.stepEvents.nodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Journey node id (if attributed). |

### Email opened (`directMarketing.emailOpened`)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Activity identifier. |
| `eventType` |  | `directMarketing.emailOpened`. |
| `timestamp` |  | When the activity occurred. |
| `personID` | Matches `AJOB2B-1_5_1-person` (`personID`) | Person identifier. |
| `personKey.sourceID` |  | Person identifier in the connected system. |
| `personKey.sourceType` |  | Name of the connected product. |
| `personKey.sourceInstanceID` |  | Identifier of the [!DNL Experience Platform] environment or connected account. |
| `personKey.sourceKey` |  | Complete person identifier used to match related records. |
| `directMarketing.mailingKey.sourceID` |  | Mailing asset id. |
| `directMarketing.mailingKey.sourceType` |  | Name of the connected product. |
| `directMarketing.mailingKey.sourceInstanceID` |  | Instance id. |
| `directMarketing.mailingKey.sourceKey` |  | Complete email-content identifier. |
| `directMarketing.mailingName` |  | Mailing name. |
| `directMarketing.email` |  | Email address. |
| `_experience.journeyOrchestration.stepEvents.journeyID` | Matches `AJOB2B-1_5_4-person_journey` (`_id`) | Journey id (if attributed). |
| `_experience.journeyOrchestration.stepEvents.nodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Journey node id (if attributed). |
| `device.isMobileDevice` |  | Whether a mobile device was recorded for the activity. |
| `device.model` |  | Device or email-client information. |
| `environment.browserDetails.userAgent` |  | Browser or email-client information. |
| `environment.operatingSystem` |  | Operating system. |

### Email link clicked (`directMarketing.emailClicked`)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Activity identifier. |
| `eventType` |  | `directMarketing.emailClicked`. |
| `timestamp` |  | When the activity occurred. |
| `personID` | Matches `AJOB2B-1_5_1-person` (`personID`) | Person identifier. |
| `personKey.sourceID` |  | Person identifier in the connected system. |
| `personKey.sourceType` |  | Name of the connected product. |
| `personKey.sourceInstanceID` |  | Identifier of the [!DNL Experience Platform] environment or connected account. |
| `personKey.sourceKey` |  | Complete person identifier used to match related records. |
| `directMarketing.mailingKey.sourceID` |  | Mailing asset id. |
| `directMarketing.mailingKey.sourceType` |  | Name of the connected product. |
| `directMarketing.mailingKey.sourceInstanceID` |  | Instance id. |
| `directMarketing.mailingKey.sourceKey` |  | Complete email-content identifier. |
| `directMarketing.mailingName` |  | Mailing name. |
| `directMarketing.email` |  | Email address. |
| `directMarketing.linkURL` |  | Clicked link URL. |
| `_experience.journeyOrchestration.stepEvents.journeyID` | Matches `AJOB2B-1_5_4-person_journey` (`_id`) | Journey id (if attributed). |
| `_experience.journeyOrchestration.stepEvents.nodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Journey node id (if attributed). |
| `device.isMobileDevice` |  | Whether a mobile device was recorded for the activity. |
| `device.model` |  | Device or email-client information. |
| `environment.browserDetails.userAgent` |  | Browser or email-client information. |
| `environment.operatingSystem` |  | Operating system. |

### Email bounced (`directMarketing.emailBounced`)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Activity identifier. |
| `eventType` |  | `directMarketing.emailBounced`. |
| `timestamp` |  | When the activity occurred. |
| `personID` | Matches `AJOB2B-1_5_1-person` (`personID`) | Person identifier. |
| `personKey.sourceID` |  | Person identifier in the connected system. |
| `personKey.sourceType` |  | Name of the connected product. |
| `personKey.sourceInstanceID` |  | Identifier of the [!DNL Experience Platform] environment or connected account. |
| `personKey.sourceKey` |  | Complete person identifier used to match related records. |
| `directMarketing.mailingKey.sourceID` |  | Mailing asset id. |
| `directMarketing.mailingKey.sourceType` |  | Name of the connected product. |
| `directMarketing.mailingKey.sourceInstanceID` |  | Instance id. |
| `directMarketing.mailingKey.sourceKey` |  | Complete email-content identifier. |
| `directMarketing.mailingName` |  | Mailing name. |
| `directMarketing.email` |  | Email address. |
| `directMarketing.emailBouncedCode` |  | Bounce category / code. |
| `directMarketing.emailBouncedDetails` |  | Detail text. |
| `_experience.journeyOrchestration.stepEvents.journeyID` | Matches `AJOB2B-1_5_4-person_journey` (`_id`) | Journey id (if attributed). |
| `_experience.journeyOrchestration.stepEvents.nodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Journey node id (if attributed). |

### Email soft bounce (`directMarketing.emailBouncedSoft`)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Activity identifier. |
| `eventType` |  | `directMarketing.emailBouncedSoft`. |
| `timestamp` |  | When the activity occurred. |
| `personID` | Matches `AJOB2B-1_5_1-person` (`personID`) | Person identifier. |
| `personKey.sourceID` |  | Person identifier in the connected system. |
| `personKey.sourceType` |  | Name of the connected product. |
| `personKey.sourceInstanceID` |  | Identifier of the [!DNL Experience Platform] environment or connected account. |
| `personKey.sourceKey` |  | Complete person identifier used to match related records. |
| `directMarketing.mailingKey.sourceID` |  | Mailing asset id. |
| `directMarketing.mailingKey.sourceType` |  | Name of the connected product. |
| `directMarketing.mailingKey.sourceInstanceID` |  | Instance id. |
| `directMarketing.mailingKey.sourceKey` |  | Complete email-content identifier. |
| `directMarketing.mailingName` |  | Mailing name. |
| `directMarketing.email` |  | Email address. |
| `directMarketing.emailBouncedCode` |  | Bounce category / code. |
| `directMarketing.emailBouncedDetails` |  | Detail text. |
| `_experience.journeyOrchestration.stepEvents.journeyID` | Matches `AJOB2B-1_5_4-person_journey` (`_id`) | Journey id (if attributed). |
| `_experience.journeyOrchestration.stepEvents.nodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Journey node id (if attributed). |

### Web page viewed (`web.webpagedetails.pageViews`)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Activity identifier. |
| `eventType` |  | `web.webpagedetails.pageViews`. |
| `timestamp` |  | When the activity occurred. |
| `personID` | Matches `AJOB2B-1_5_1-person` (`personID`) | Person identifier. |
| `personKey.sourceID` |  | Person identifier in the connected system. |
| `personKey.sourceType` |  | Name of the connected product. |
| `personKey.sourceInstanceID` |  | Identifier of the [!DNL Experience Platform] environment or connected account. |
| `personKey.sourceKey` |  | Complete person identifier used to match related records. |
| `web.webPageDetails.webPageKey.sourceID` |  | Page asset id. |
| `web.webPageDetails.webPageKey.sourceType` |  | Name of the connected product. |
| `web.webPageDetails.webPageKey.sourceInstanceID` |  | Instance id. |
| `web.webPageDetails.webPageKey.sourceKey` |  | Complete page identifier. |
| `web.webPageDetails.name` |  | Page name. |
| `web.webPageDetails.URL` |  | Page URL. |
| `web.webPageDetails.queryParameters` |  | Additional information included in a web address. |
| `web.webPageDetails.webPageID` |  | Page id. |
| `environment.browserDetails.userAgent` |  | Browser or email-client information. |
| `web.webReferrer.URL` |  | Referrer URL. |

### Web link clicked (`web.webinteraction.linkClicks`)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Activity identifier. |
| `eventType` |  | `web.webinteraction.linkClicks`. |
| `timestamp` |  | When the activity occurred. |
| `personID` | Matches `AJOB2B-1_5_1-person` (`personID`) | Person identifier. |
| `personKey.sourceID` |  | Person identifier in the connected system. |
| `personKey.sourceType` |  | Name of the connected product. |
| `personKey.sourceInstanceID` |  | Identifier of the [!DNL Experience Platform] environment or connected account. |
| `personKey.sourceKey` |  | Complete person identifier used to match related records. |
| `web.webInteraction.webInteractionKey.sourceID` |  | Interaction asset id. |
| `web.webInteraction.webInteractionKey.sourceType` |  | Name of the connected product. |
| `web.webInteraction.webInteractionKey.sourceInstanceID` |  | Instance id. |
| `web.webInteraction.webInteractionKey.sourceKey` |  | Complete interaction identifier. |
| `web.webInteraction.linkID` |  | Link id. |
| `web.webInteraction.linkURL` |  | Destination URL. |
| `web.webPageDetails.queryParameters` |  | Additional information included in a web address. |
| `web.webPageDetails.webPageID` |  | Page id. |
| `environment.browserDetails.userAgent` |  | Browser or email-client information. |
| `web.webReferrer.URL` |  | Referrer URL. |

### Form submitted (`web.formFilledOut`)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Activity identifier. |
| `eventType` |  | `web.formFilledOut`. |
| `timestamp` |  | When the activity occurred. |
| `personID` | Matches `AJOB2B-1_5_1-person` (`personID`) | Person identifier. |
| `personKey.sourceID` |  | Person identifier in the connected system. |
| `personKey.sourceType` |  | Name of the connected product. |
| `personKey.sourceInstanceID` |  | Identifier of the [!DNL Experience Platform] environment or connected account. |
| `personKey.sourceKey` |  | Complete person identifier used to match related records. |
| `web.fillOutForm.webFormKey.sourceID` |  | Form asset id. |
| `web.fillOutForm.webFormKey.sourceType` |  | Name of the connected product. |
| `web.fillOutForm.webFormKey.sourceInstanceID` |  | Instance id. |
| `web.fillOutForm.webFormKey.sourceKey` |  | Complete form identifier. |
| `web.fillOutForm.webFormID` |  | Form id. |
| `web.fillOutForm.webFormName` |  | Form name. |
| `web.webPageDetails.queryParameters` |  | Additional information included in a web address. |
| `web.webPageDetails.webPageID` |  | Page id. |
| `environment.browserDetails.userAgent` |  | Browser or email-client information. |
| `web.webReferrer.URL` |  | Referrer URL. |

### Interesting moment recorded (`leadOperation.interestingMoment`)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Activity identifier. |
| `eventType` |  | `leadOperation.interestingMoment`. |
| `timestamp` |  | When the activity occurred. |
| `personID` | Matches `AJOB2B-1_5_1-person` (`personID`) | Person identifier. |
| `personKey.sourceID` |  | Person identifier in the connected system. |
| `personKey.sourceType` |  | Name of the connected product. |
| `personKey.sourceInstanceID` |  | Identifier of the [!DNL Experience Platform] environment or connected account. |
| `personKey.sourceKey` |  | Complete person identifier used to match related records. |
| `leadOperation.interestingMoment.date` |  | Moment date/time. |
| `leadOperation.interestingMoment.description` |  | Description. |
| `leadOperation.interestingMoment.source` |  | Name of the related product or campaign. |
| `leadOperation.interestingMoment.type` |  | Type label. |
| `_experience.journeyOrchestration.stepEvents.journeyID` | Matches `AJOB2B-1_5_4-person_journey` (`_id`) | Journey id (if attributed). |
| `_experience.journeyOrchestration.stepEvents.nodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Journey node id (if attributed). |

## `AJOB2B-1_5_4-journey_node`

Each record describes a journey step, the journey it belongs to, and the kind of step. The same steps can appear in the account- and person-journey step datasets. Match `journeyID` to the appropriate journey; do not count a step more than once because it appears in several datasets.

**Format:** Related-record format

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Node record id (use the complete value). |
| `journeyID` | Matches `AJOB2B-1_5_4-account_journey` or `AJOB2B-1_5_4-person_journey` (`_id`) | Parent journey identifier. |
| `nodeType` |  | Kind of journey step, such as a start, end, wait, or decision. |
| `isDeleted` |  | Whether this record is marked as deleted. |
| `lastUpdatedDate` |  | Last modification time. |

## `AJOB2B-1_5_4-account_relational`

Each record describes an account, including its organization details, location, size, revenue, and custom fields. Use this information to add account context to buying-group and journey reports.

**Format:** Related-record format

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Account record id (use the complete value). |
| `accountName` |  | Account name. |
| `industry` |  | Industry classification. |
| `country` |  | Country. |
| `sicCode` |  | Standard Industrial Classification code. |
| `domainName` |  | Primary web domain. |
| `primaryEmailDomain` |  | Primary email domain. |
| `street` |  | Street address. |
| `city` |  | City. |
| `state` |  | State or region. |
| `postalCode` |  | Postal / zip code. |
| `region` |  | Geographic region. |
| `phoneNumber` |  | Phone number. |
| `logoUrl` |  | URL of the account logo. |
| `annualRevenue` |  | Annual revenue. |
| `numberOfEmployees` |  | Number of employees. |
| `createdDate` |  | When the record was created. |
| `sourceType` |  | Name of the connected system that identifies the account. |
| `sourceInstanceID` |  | Identifier of your organization or account in that connected system. |
| `sourceID` |  | Account identifier in that connected system. |
| `customAttributes` |  | Custom field names and values stored together as text. |
| `isDeleted` |  | Whether this record is marked as deleted. |
| `lastUpdatedDate` |  | Last modification time. |

## `AJOB2B-1_5_4-person_relational`

Each record describes a person, including their contact information, job details, identifiers, and custom fields. Use it to add person information to membership, journey, and activity reports.

**Format:** Related-record format

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Complete person identifier used to match related records. |
| `email` |  | Email address. |
| `firstName` |  | First name. |
| `middleName` |  | Middle name. |
| `lastName` |  | Last name. |
| `jobTitle` |  | Job title. |
| `personType` |  | Person type: contact, prospect, or pending lead. |
| `isLead` |  | Whether the person is a lead. |
| `isAnonymous` |  | Whether the person is anonymous. |
| `salutation` |  | Salutation or honorific. |
| `phone` |  | Primary phone number. |
| `mobile` |  | Mobile phone number. |
| `sourceType` |  | Name of the connected system that identifies the person, such as [!DNL Marketo Engage]. |
| `sourceInstanceID` |  | Identifier of your organization or account in that connected system. |
| `sourceID` |  | Person identifier in that connected system. |
| `identityNamespace` |  | Label identifying the kind of additional person identifier. |
| `identityValue` |  | Value of the secondary identity. |
| `customAttributes` |  | Custom field names and values stored together as text. |
| `isDeleted` |  | Whether this record is marked as deleted. |
| `lastUpdatedDate` |  | Last modification time. |

## `AJOB2B-1_5_4-account_person`

Each record links an account profile to a person profile. Use it to report relationships across the account and person profile datasets.

**Format:** Related-record format

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Account-person relationship record id (use the complete value). |
| `accountID` | Matches `AJOB2B-1_5_4-account_relational` (`_id`) | Complete account identifier (references `account_relational._id`). |
| `personID` | Matches `AJOB2B-1_5_4-person_relational` (`_id`) | Complete person identifier (references `person_relational._id`). |
| `createdDate` |  | When the account-person relationship was created. |
| `isDeleted` |  | Whether this record is marked as deleted. |
| `lastUpdatedDate` |  | Last modification time. |

## `AJOB2B-1_5_4-person_event_relational`

Each record describes a supported person activity, such as viewing a web page, interacting with an email, or moving through a journey. Use `eventType` and `activityTypeID` to understand what happened. Only details relevant to that kind of activity are populated.

**Format:** Related-record format

The following field list covers all supported activity types. An individual record contains only the details that apply to its activity.

>[!NOTE]
>
>**Availability:** some activities may have a blank `_id`. Do not assume every activity has a usable record identifier. The dataset is not a guarantee of a complete activity history.

Journey details (`journeyID`, `journeyNodeID`, `journeyStepID`, and similar fields) are provided for journey activities (`person.journeyAdd`, `person.journeyRemove`, `person.journeyStart`, `person.journeyEnd`, `person.journeyNodeTransition`, `person.journeySplitNode`) and for `person.attributeChanged` activities associated with an "Update person profile" journey step.

Attribute-change fields (`attributeName`, `attributeID`, `attributeNewValue`, `attributeOldValue`, `attributeChangeReason`) are populated for `person.attributeChanged` only.

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id` | Record ID | Identifier for the activity, when available. |
| `timestamp` |  | When the activity occurred. |
| `eventType` |  | Activity label. Values: `web.webpagedetails.pageViews`, `web.formFilledOut`, `web.webinteraction.linkClicks`, `directMarketing.emailSent`, `directMarketing.emailDelivered`, `directMarketing.emailBounced`, `directMarketing.emailBouncedSoft`, `directMarketing.emailUnsubscribed`, `directMarketing.emailOpened`, `directMarketing.emailClicked`, `leadOperation.interestingMoment`, `person.attributeChanged`, `person.journeyAdd`, `person.journeyRemove`, `person.journeyStart`, `person.journeyEnd`, `person.journeyNodeTransition`, `person.journeySplitNode`. |
| `activityTypeID` |  | Activity code. Use it with `eventType` to distinguish activities that share the same event label. |
| `personID` | Matches `AJOB2B-1_5_4-person_relational` (`_id`) | Complete person identifier used to match the activity to a person record. |
| `journeyID` | Matches `AJOB2B-1_5_4-person_journey` (`_id`) | Complete journey identifier. Blank for activities not associated with a journey. |
| `journeyNodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Complete journey-step identifier. Blank for activities not associated with a journey. |
| `previousJourneyNodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Prior journey node (populated for `person.journeyNodeTransition` and `person.journeySplitNode`). |
| `newJourneyNodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Destination journey node id (`person.journeyNodeTransition` and `person.journeySplitNode`). Usually equals `journeyNodeID`. |
| `journeyStepID` |  | Identifier of the journey step associated with the activity. |
| `journeyChoiceNumber` |  | Split-choice number for `person.journeySplitNode`. Recorded as a whole number. |
| `journeyEntryCount` |  | Number of times this person has entered the journey (populated on journey add / start events). Recorded as a whole number. |
| `journeyProgramID` | No separate marketing-program dataset in this guide | Identifier of the marketing program associated with the journey activity. |
| `activitySource` |  | Name of the product or action associated with the activity. |
| `campaignID` |  | [!DNL Marketo Engage] campaign id when the activity is campaign-attributed. |
| `attributeName` |  | Name of the field that changed (`person.attributeChanged` only). |
| `attributeID` |  | Identifier of the field that changed (`person.attributeChanged` only). |
| `attributeNewValue` |  | New field value, recorded as text (`person.attributeChanged` only). |
| `attributeOldValue` |  | Previous field value, recorded as text (`person.attributeChanged` only). |
| `attributeChangeReason` |  | Reason label for the change (`person.attributeChanged` only). |
| `assetID` |  | Identifier of the related email content, page, or form. |
| `assetName` |  | Name of the related content. |
| `recipientEmail` |  | Recipient email address, when available. Populated only for activity codes **27** (soft bounce) and **48** (sales email soft bounce); blank for other email activities. For those activities, look up the person record using `personID`. `assetName` identifies the email content, not the recipient's address. |
| `bouncedCode` |  | Bounce category code (emailBounced / emailBouncedSoft only). |
| `bouncedDetails` |  | Detailed bounce reason (emailBounced / emailBouncedSoft only). |
| `isMobileDevice` |  | Whether a mobile device was recorded for an email open or click. |
| `deviceModel` |  | Device model (emailOpened / emailClicked only). |
| `operatingSystem` |  | Operating system (emailOpened / emailClicked only). |
| `userAgent` |  | Browser or email-client information, for email opens, email clicks, and web activities. |
| `clickedLinkUrl` |  | Clicked email link URL (emailClicked only). |
| `webPageUrl` |  | Web page URL (`web.webpagedetails.pageViews` only). |
| `queryParameters` |  | Additional information in a web address, for page views, form submissions, or web link clicks. |
| `webPageID` |  | [!DNL Marketo Engage] web page id (pageViews, formFilledOut, linkClicks). |
| `referrerUrl` |  | Referrer URL (pageViews, formFilledOut, linkClicks). |
| `formID` |  | [!DNL Marketo Engage] form id (`web.formFilledOut` only). |
| `linkID` |  | [!DNL Marketo Engage] link id (`web.webinteraction.linkClicks` only). |
| `interestingMomentDate` |  | Moment date (`leadOperation.interestingMoment` only). |
| `interestingMomentDescription` |  | Free-text description (interestingMoment only). |
| `interestingMomentSource` |  | Related product or campaign (interestingMoment only). |
| `interestingMomentType` |  | Category / type (interestingMoment only). |
| `isDeleted` |  | Whether this record is marked as deleted. |
| `lastUpdatedDate` |  | Last modification time. |

### Field reference by activity type

The following tables show which details apply to each activity. Other details are blank. Some activities share the same `eventType` label: codes 8 and 48 both use `directMarketing.emailBounced`. Use `activityTypeID` to distinguish them.

#### Web page viewed (`web.webpagedetails.pageViews`) (Activity type 1)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `assetID` |  | Page id. |
| `assetName` |  | Page name. |
| `webPageUrl` |  | Page URL. |
| `queryParameters` |  | Additional information included in a web address. |
| `webPageID` |  | [!DNL Marketo Engage] web page id. |
| `referrerUrl` |  | Referrer URL. |
| `userAgent` |  | Browser or email-client information. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

#### Form submitted (`web.formFilledOut`) (Activity type 2)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `assetID` |  | Form id. |
| `assetName` |  | Form name. |
| `formID` |  | [!DNL Marketo Engage] form id. |
| `queryParameters` |  | Additional information included in a web address. |
| `webPageID` |  | [!DNL Marketo Engage] web page id. |
| `referrerUrl` |  | Referrer URL. |
| `userAgent` |  | Browser or email-client information. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

#### Web link clicked (`web.webinteraction.linkClicks`) (Activity type 3)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `assetID` |  | Interaction / link id. |
| `assetName` |  | Destination URL. |
| `linkID` |  | [!DNL Marketo Engage] link id. |
| `queryParameters` |  | Additional information included in a web address. |
| `webPageID` |  | [!DNL Marketo Engage] web page id. |
| `referrerUrl` |  | Referrer URL. |
| `userAgent` |  | Browser or email-client information. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

#### Email sent (`directMarketing.emailSent`) (Activity types 6, 39)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `assetID` |  | Mailing id. |
| `assetName` |  | Mailing name. |
| `campaignID` |  | [!DNL Marketo Engage] campaign id, when campaign-attributed. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

#### Email delivered (`directMarketing.emailDelivered`) (Activity types 7, 45)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `assetID` |  | Mailing id. |
| `assetName` |  | Mailing name. |
| `campaignID` |  | [!DNL Marketo Engage] campaign id, when campaign-attributed. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

#### Email unsubscribe (`directMarketing.emailUnsubscribed`) (Activity type 9)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `assetID` |  | Mailing id. |
| `assetName` |  | Mailing name. |
| `campaignID` |  | [!DNL Marketo Engage] campaign id, when campaign-attributed. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

#### Email opened (`directMarketing.emailOpened`) (Activity types 10, 40)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `assetID` |  | Mailing id. |
| `assetName` |  | Mailing name. |
| `isMobileDevice` |  | Whether a mobile device was recorded for the activity. |
| `deviceModel` |  | Device model. |
| `operatingSystem` |  | Operating system. |
| `userAgent` |  | Browser or email-client information. |
| `campaignID` |  | [!DNL Marketo Engage] campaign id, when campaign-attributed. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

#### Email link clicked (`directMarketing.emailClicked`) (Activity types 11, 41)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `assetID` |  | Mailing id. |
| `assetName` |  | Mailing name. |
| `clickedLinkUrl` |  | Clicked link URL. |
| `isMobileDevice` |  | Whether a mobile device was recorded for the activity. |
| `deviceModel` |  | Device model. |
| `operatingSystem` |  | Operating system. |
| `userAgent` |  | Browser or email-client information. |
| `campaignID` |  | [!DNL Marketo Engage] campaign id, when campaign-attributed. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

#### Email bounced (`directMarketing.emailBounced`): hard bounce (Activity type 8)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `assetID` |  | Mailing id. |
| `assetName` |  | Mailing name. |
| `bouncedCode` |  | Bounce category code. |
| `bouncedDetails` |  | Detailed bounce reason. |
| `campaignID` |  | [!DNL Marketo Engage] campaign id, when campaign-attributed. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

This activity shares the `directMarketing.emailBounced` label with activity code 48, but `recipientEmail` is blank for code 8. Use `activityTypeID` to distinguish the two.

#### Email bounced (`directMarketing.emailBounced`): sales email soft bounce (Activity type 48)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `assetID` |  | Mailing id. |
| `assetName` |  | Mailing name. |
| `recipientEmail` |  | Recipient email address. |
| `bouncedCode` |  | Bounce category code. |
| `bouncedDetails` |  | Detailed bounce reason. |
| `campaignID` |  | [!DNL Marketo Engage] campaign id, when campaign-attributed. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

#### Email soft bounce (`directMarketing.emailBouncedSoft`) (Activity type 27)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `assetID` |  | Mailing id. |
| `assetName` |  | Mailing name. |
| `recipientEmail` |  | Recipient email address. |
| `bouncedCode` |  | Bounce category code. |
| `bouncedDetails` |  | Detailed bounce reason. |
| `campaignID` |  | [!DNL Marketo Engage] campaign id, when campaign-attributed. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

#### Interesting moment recorded (`leadOperation.interestingMoment`) (Activity type 46)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `interestingMomentDate` |  | Moment date/time. |
| `interestingMomentDescription` |  | Free-text description. |
| `interestingMomentSource` |  | Name of the related product or campaign. |
| `interestingMomentType` |  | Type label. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

`assetID` and `assetName` are not populated for this activity type.

#### Person field changed (`person.attributeChanged`) (Activity type 13)

Included only when the change is associated with a journey, such as an "Update person profile" step. Changes outside a journey are not included.

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `attributeName` |  | Name of the field that changed. |
| `attributeID` |  | Identifier of the field that changed. |
| `attributeNewValue` |  | New field value, recorded as text. |
| `attributeOldValue` |  | Previous field value, recorded as text. |
| `attributeChangeReason` |  | Reason label for the change. |
| `journeyID` | Matches `AJOB2B-1_5_4-person_journey` (`_id`) | Journey identifier. |
| `journeyNodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Journey node identifier. |
| `journeyStepID` |  | Identifier of the journey step. |
| `journeyProgramID` | No separate marketing-program dataset in this guide | Journey program id. |
| `activitySource` |  | Product or action associated with the activity. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

#### Person added to or started a journey (`person.journeyAdd`, `person.journeyStart`) (Activity types 182, 184)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `journeyID` | Matches `AJOB2B-1_5_4-person_journey` (`_id`) | Journey identifier. |
| `journeyNodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Journey node identifier. |
| `journeyStepID` |  | Identifier of the journey step. |
| `journeyEntryCount` |  | Number of times this person has entered the journey. |
| `journeyProgramID` | No separate marketing-program dataset in this guide | Journey program id. |
| `activitySource` |  | Product or action associated with the activity. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

#### Person removed from or ended a journey (`person.journeyRemove`, `person.journeyEnd`) (Activity types 183, 185)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `journeyID` | Matches `AJOB2B-1_5_4-person_journey` (`_id`) | Journey identifier. |
| `journeyNodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Journey node identifier. |
| `journeyStepID` |  | Identifier of the journey step. |
| `journeyProgramID` | No separate marketing-program dataset in this guide | Journey program id. |
| `activitySource` |  | Product or action associated with the activity. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

#### Person followed a journey branch (`person.journeySplitNode`) (Activity type 186)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `journeyID` | Matches `AJOB2B-1_5_4-person_journey` (`_id`) | Journey identifier. |
| `journeyNodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Journey node identifier (the split node). |
| `previousJourneyNodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Node the person was at before the split. |
| `newJourneyNodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Node the person moved to (usually equals `journeyNodeID`). |
| `journeyStepID` |  | Identifier of the journey step. |
| `journeyChoiceNumber` |  | Which branch of the split was taken. |
| `journeyProgramID` | No separate marketing-program dataset in this guide | Journey program id. |
| `activitySource` |  | Product or action associated with the activity. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

#### Person moved between journey steps (`person.journeyNodeTransition`) (Activity type 600)

| Field name | Relationship | What it tells you |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | Record ID: `_id`; `personID` matches `AJOB2B-1_5_4-person_relational` (`_id`) | Common fields. |
| `journeyID` | Matches `AJOB2B-1_5_4-person_journey` (`_id`) | Journey identifier. |
| `journeyNodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Current journey node identifier. |
| `previousJourneyNodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Node the person transitioned from. |
| `newJourneyNodeID` | Matches `AJOB2B-1_5_4-person_journey_node` (`_id`) | Node the person transitioned to (usually equals `journeyNodeID`). |
| `journeyStepID` |  | Identifier of the journey step. |
| `journeyProgramID` | No separate marketing-program dataset in this guide | Journey program id. |
| `activitySource` |  | Product or action associated with the activity. |
| `isDeleted`, `lastUpdatedDate` |  | Common fields. |

## Customer-owned datasets {#customer-owned-datasets}

Your organization may use its own [!DNL Experience Platform] datasets for accounts or people. When configured, [!DNL Adobe Journey Optimizer B2B Edition] can add information to those datasets instead of creating another account or person dataset.

Their names and available fields depend on your organization's setup. Use the configured account or person identifier to recognize matching records. Having records in these datasets does not automatically make them available for audiences; availability depends on your [!DNL Experience Platform] configuration.
