---
title: Dataset Queries
description: Learn how to use SQL query examples in Query Service to analyze account, buying group, person, and journey data exported by Adobe Journey Optimizer B2B Edition.
feature: Reporting, Data Management
role: Admin, Developer
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
    internal-label: Experience Platform
feature_v2:
  - id: f2da1b69-6919-4386-a5d2-9c7b5c9033db
    internal-label: Data management
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
---

# Dataset queries

Find ready-to-use SQL query examples for analyzing the account, person, buying group, and journey data that [!DNL Adobe Journey Optimizer B2B Edition] exports to [!DNL Adobe Experience Platform]. To report on accounts, buying groups, email engagement, and journey activity, run the queries in [!DNL Query Service].

For descriptions of the datasets and fields used in these queries, see [Exported datasets](./aep-exported-datasets.md).

## Prerequisites {#prerequisites}

Before you run any query on this page, make sure that you have the following:

* **Access to [!DNL Query Service]:** You must have access to [Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/home){target="_blank"} in your [!DNL Experience Platform] sandbox.
* **Available datasets:** The queries target the exported [!DNL Journey Optimizer B2B Edition] datasets. In your sandbox, go to **[!UICONTROL Datasets]** and verify that the datasets exist and contain data.
* **Schema field values:** Make sure that the fields in your queries have values in the corresponding schema. Empty fields return no results and do not produce errors.

>[!NOTE]
>
>The examples use short table names, such as `account_table` and `person_activity_table`. Replace each table name with the name of the corresponding dataset in your sandbox. Replace placeholder values, such as `Example Company` and `PASTE_COMPLETE_JOURNEY_ID_HERE`, with values from your environment.

## Run a query {#run}

To run any example on this page:

1. In [!DNL Experience Platform], select **[!UICONTROL Query Service]** > **[!UICONTROL Queries]**.
1. Paste the example into the query editor, then replace the table names and placeholder values.
1. Select **[!UICONTROL Run]**.

The examples that filter by date use the last 30 days. To change the time range, edit the `INTERVAL '30' DAY` value.

## Choose a query

Use the following table to choose a query for your reporting task.

| I want to | Go to |
|---|---|
| Review account names, industries, and locations | [Review account details](#account-details) |
| Compare buying groups by engagement | [Compare buying group engagement](#buying-group-engagement) |
| Find the people associated with an account | [Find people in an account](#account-people) |
| Track changes to buying group status | [Review buying group status changes](#buying-group-status-changes) |
| Find people who clicked an email | [Find people who clicked an email](#email-clicks) |
| Compare recent activity by type | [Compare recent person activity](#person-activity) |
| Compare account journeys by size | [Compare account counts by journey](#account-journey-counts) |
| List the accounts in a journey | [List accounts in a journey](#journey-accounts) |
| Track daily account journey activity | [Track daily account activity](#account-daily-activity) |
| Investigate the history of an account in a journey | [Review an account journey timeline](#account-timeline) |
| Compare person journeys by size and status | [Compare person counts by journey](#person-journey-counts) |
| List the people in a journey | [List people in a journey](#journey-people) |
| See where people are in a journey | [Compare person counts by step](#person-step-counts) |
| Track recent person journey activity | [Track recent journey activity](#person-journey-activity) |
| Investigate the history of a person in a journey | [Review a person journey timeline](#person-timeline) |

## Account and buying group queries

Use these queries to review the accounts, buying groups, and people available for reporting.

### Review account details {#account-details}

Review account names, industries, locations, and company sizes to understand the accounts available for reporting.

```sql
SELECT
a._id AS accountID,
a.accountName,
a.industry,
a.country,
a.numberOfEmployees
FROM account_table a
WHERE a.isDeleted = FALSE
ORDER BY a.accountName
LIMIT 100;
```

### Compare buying group engagement {#buying-group-engagement}

Compare buying groups by recorded engagement score, alongside completeness and solution interest.

```sql
SELECT
bg._id AS buyingGroupID,
bg.buyingGroupName,
bg.engagementScore,
bg.completenessScore,
bg.solutionInterest,
bg.buyingGroupStatus
FROM buying_group_table bg
WHERE bg.isDeleted = FALSE
ORDER BY bg.engagementScore DESC NULLS LAST, bg.buyingGroupName
LIMIT 100;
```

### Find people in an account {#account-people}

Find the people and job titles associated with an account to understand its contacts. Replace `Example Company` with an account name from your sandbox.

```sql
SELECT DISTINCT
a._id AS accountID,
a.accountName,
p._id AS personID,
p.firstName,
p.lastName,
p.email,
p.jobTitle
FROM account_member_table m
JOIN account_table a ON m.accountID = a._id
JOIN person_table p ON m.personID = p._id
WHERE m.isDeleted = FALSE
AND a.isDeleted = FALSE
AND p.isDeleted = FALSE
AND a.accountName = 'Example Company'
ORDER BY p.lastName, p.firstName
LIMIT 100;
```

### Review buying group status changes {#buying-group-status-changes}

Review buying group status changes in the last 30 days to understand how groups change over time.

```sql
SELECT
bg._id AS buyingGroupID,
bg.buyingGroupName,
e.timestamp AS changedAt,
e.newStatus
FROM buying_group_event_table e
JOIN buying_group_table bg ON e.buyingGroupID = bg._id
WHERE bg.isDeleted = FALSE
AND e.eventType = 'buyingGroup.changeStatus'
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
ORDER BY e.timestamp DESC
LIMIT 100;
```

## Person engagement queries

Use these queries to review email engagement and other recorded person activity.

### Find people who clicked an email {#email-clicks}

To review recent email engagement, identify people with recorded email clicks in the last 30 days.

```sql
SELECT DISTINCT
p._id AS personID,
p.firstName,
p.lastName,
p.email
FROM person_activity_table e
JOIN person_table p ON e.personID = p._id
WHERE e.isDeleted = FALSE
AND p.isDeleted = FALSE
AND e.eventType = 'directMarketing.emailClicked'
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
ORDER BY p.lastName, p.firstName
LIMIT 100;
```

### Compare recent person activity {#person-activity}

Compare recorded activity types and the number of people involved to understand recent engagement.

```sql
SELECT
e.eventType,
COUNT(*) AS recordedRows,
COUNT(DISTINCT e.personID) AS distinctPeople
FROM person_activity_table e
WHERE e.isDeleted = FALSE
AND e.personID IS NOT NULL
AND e.personID <> ''
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
GROUP BY e.eventType
ORDER BY recordedRows DESC
LIMIT 100;
```

## Account journey queries

Use these queries to analyze account journeys. Replace `PASTE_COMPLETE_JOURNEY_ID_HERE` with the `_id` value of the account journey, and `PASTE_COMPLETE_ACCOUNT_ID_HERE` with the `_id` value of the account.

### Compare account counts by journey {#account-journey-counts}

Compare account journeys by status and recorded membership count to see which journeys have the largest account populations.

```sql
SELECT
j._id AS journeyID,
j.accountJourneyName,
j.accountJourneyStatus,
COUNT(DISTINCT m.accountID) AS accountsWithRecordedMembership
FROM account_journey_table j
LEFT JOIN account_journey_member_table m
ON m.journeyID = j._id
AND m.isDeleted = FALSE
AND m.accountID <> ''
WHERE j.isDeleted = FALSE
GROUP BY j._id, j.accountJourneyName, j.accountJourneyStatus
ORDER BY accountsWithRecordedMembership DESC, j.accountJourneyName
LIMIT 100;
```

### List accounts in a journey {#journey-accounts}

Review the accounts associated with a particular journey, including their industries and countries.

```sql
SELECT DISTINCT
a._id AS accountID,
a.accountName,
a.industry,
a.country
FROM account_journey_member_table m
JOIN account_table a ON m.accountID = a._id
WHERE m.isDeleted = FALSE
AND a.isDeleted = FALSE
AND m.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
ORDER BY a.accountName, accountID
LIMIT 100;
```

### Track daily account activity {#account-daily-activity}

Track daily account additions, removals, and step changes to understand activity in a journey over the last 30 days.

```sql
SELECT
CAST(e.timestamp AS DATE) AS activityDate,
e.eventType,
COUNT(*) AS recordedRows,
COUNT(DISTINCT e.accountID) AS distinctAccounts
FROM account_activity_table e
WHERE e.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
AND e.accountID IS NOT NULL
AND e.accountID <> ''
AND e.eventType IN (
'account.addAccountToJourney',
'account.removeAccountFromJourney',
'account.changeAccountJourneyNode'
)
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
GROUP BY CAST(e.timestamp AS DATE), e.eventType
ORDER BY activityDate DESC, e.eventType
LIMIT 100;
```

### Review an account journey timeline {#account-timeline}

Investigate the recent journey history of an account by reviewing its recorded events and journey steps.

```sql
SELECT
e.timestamp AS activityAt,
e.eventType,
e.journeyNodeID,
n.nodeType,
e.previousJourneyNodeID,
e.buyingGroupID
FROM account_activity_table e
LEFT JOIN account_journey_node_table n
ON e.journeyNodeID = n._id
AND e.journeyID = n.accountJourneyID
AND n.isDeleted = FALSE
WHERE e.accountID = 'PASTE_COMPLETE_ACCOUNT_ID_HERE'
AND e.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
ORDER BY e.timestamp DESC
LIMIT 100;
```

## Person journey queries

Use these queries to analyze person journeys. Replace `PASTE_COMPLETE_JOURNEY_ID_HERE` with the `_id` value of the person journey, and `PASTE_COMPLETE_PERSON_ID_HERE` with the `_id` value of the person.

### Compare person counts by journey {#person-journey-counts}

Compare person journeys by recorded membership count, status, and dates to understand their size and lifecycle.

```sql
SELECT
j._id AS journeyID,
j.personJourneyName,
j.personJourneyStatus,
j.startDate,
j.endDate,
COUNT(DISTINCT m.personID) AS peopleWithRecordedMembership
FROM person_journey_table j
LEFT JOIN person_journey_member_table m
ON m.journeyID = j._id
AND m.isDeleted = FALSE
AND m.personID <> ''
WHERE j.isDeleted = FALSE
GROUP BY
j._id,
j.personJourneyName,
j.personJourneyStatus,
j.startDate,
j.endDate
ORDER BY peopleWithRecordedMembership DESC, j.personJourneyName
LIMIT 100;
```

### List people in a journey {#journey-people}

Review who is associated with a journey, when they last entered, and how often they have entered.

```sql
SELECT DISTINCT
m.personID,
p.firstName,
p.lastName,
p.email,
m.membershipDate,
m.lastEntryDate,
m.entryCount,
m.reentryOpensAt,
m.journeyNodeID
FROM person_journey_member_table m
LEFT JOIN person_table p
ON m.personID = p._id
AND p.isDeleted = FALSE
WHERE m.isDeleted = FALSE
AND m.personID IS NOT NULL
AND m.personID <> ''
AND m.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
ORDER BY m.lastEntryDate DESC NULLS LAST, m.personID
LIMIT 100;
```

### Compare person counts by step {#person-step-counts}

See how people are distributed across the steps recorded in their journey memberships.

```sql
SELECT
m.journeyNodeID,
n.nodeType,
COUNT(DISTINCT m.personID) AS peopleWithRecordedStep
FROM person_journey_member_table m
LEFT JOIN person_journey_node_table n
ON m.journeyNodeID = n._id
AND m.journeyID = n.personJourneyID
AND n.isDeleted = FALSE
WHERE m.isDeleted = FALSE
AND m.personID IS NOT NULL
AND m.personID <> ''
AND m.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
GROUP BY m.journeyNodeID, n.nodeType
ORDER BY peopleWithRecordedStep DESC, m.journeyNodeID
LIMIT 100;
```

### Track recent journey activity {#person-journey-activity}

Compare recorded journey starts, ends, and transitions to understand person activity in a journey over the last 30 days.

```sql
SELECT
e.eventType,
COUNT(*) AS recordedRows,
COUNT(DISTINCT e.personID) AS distinctPeople
FROM person_activity_table e
WHERE e.isDeleted = FALSE
AND e.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
AND e.personID IS NOT NULL
AND e.personID <> ''
AND e.eventType IN (
'person.journeyAdd',
'person.journeyRemove',
'person.journeyStart',
'person.journeyEnd',
'person.journeyNodeTransition',
'person.journeySplitNode'
)
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
GROUP BY e.eventType
ORDER BY recordedRows DESC, e.eventType
LIMIT 100;
```

### Review a person journey timeline {#person-timeline}

Investigate the recent journey history of a person, including step transitions, split choices, and journey attributed profile updates.

```sql
SELECT
e.timestamp AS activityAt,
e.eventType,
e.journeyNodeID,
e.previousJourneyNodeID,
e.newJourneyNodeID,
e.journeyChoiceNumber,
e.journeyEntryCount,
e.attributeName,
e.attributeOldValue,
e.attributeNewValue
FROM person_activity_table e
WHERE e.isDeleted = FALSE
AND e.personID = 'PASTE_COMPLETE_PERSON_ID_HERE'
AND e.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
ORDER BY e.timestamp DESC
LIMIT 100;
```
