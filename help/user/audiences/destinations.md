---
title: Destinations
description: Learn about supported Experience Platform destinations and how to connect a destination to activate static people lists in Journey Optimizer B2B Edition.
feature: Audiences, Integrations
role: User
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
    internal-label: Integrations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: ff2b9b37-92e0-45fc-b853-379d44c08c89
    internal-label: Audience segmentation
---

# Destinations

Destinations are pre-built integrations that let you send [static people list](./people-lists-static.md) members and account journey audiences to social platforms. Activating a static list to a destination keeps membership in sync. As people are added to or removed from the list, they are correspondingly added to or removed from the destination audience and, by extension, from any campaign that the audience feeds.

There are three ways to activate people to a connected destination:

* **From a static list** - Activate an existing static list directly from the **_[!UICONTROL People lists]_** tab. See [_Activate to a destination_](./people-lists-static.md#static-list-activate).
* **From an account journey** - Add an **_[!UICONTROL Activate to destination]_** action node to a journey path so that qualifying accounts are activated to the destination when they reach that node. See [_Activate to or deactivate from a destination_](../journeys/action-nodes.md#activate-deactivate-destination).
* **From a buying group** - To fill empty roles in your buying groups, you can activate a LinkedIn Matched Audience to target prospects who match your buying group parameters. See [_LinkedIn Account Matched audience_s](../data/linkedin-account-matched-audiences.md#activate-buying-group).

>[!BEGINSHADEBOX]

## Required permissions {#required-permissions}

Full destination capability requires the following [!DNL Adobe Experience Platform] permissions.

| Category | Permission |
|--- |--- |--- |
| Sandboxes | Sandbox access |
| Dashboards | View Standard Dashboards |
| Dashboards | Manage Standard Dashboards |
| Destinations | View Destinations |
| Destinations | Manage Destinations |
| Destinations | Activate Destinations |
| Destinations | Activate Segment without Mapping |
| Destinations | Manage and Activate Dataset Destination |
| Destinations | Destination Authoring |
| Data Governance | View Data Usage Policies |
| Data Governance | Manage Data Usage Policies |
| Data Ingestion | View Sources |
| Data Ingestion | Manage Sources |
| Profile Management | View Profile Settings |
| Profile Management | Manage Profile Settings |

>[!ENDSHADEBOX]

## Supported destinations {#supported-destinations}

Before you can activate a static list, a destination must exist in the destinations catalog. On the left navigation, expand **[!UICONTROL Connections]** and select **[!UICONTROL Destinations]**. [!DNL Journey Optimizer B2B Edition] currently supports the **[!UICONTROL LinkedIn Matched Audience]** (Social) destination. See [_LinkedIn Account Matched audiences_](../data/linkedin-account-matched-audiences.md) to 

<!-- 
the following destinations:

* **[!UICONTROL Google Customer Match]** (Advertising)
* **[!UICONTROL Facebook Custom Audience]** (Social)
* **[!UICONTROL LinkedIn Matched Audience]** (Social)

![Access the available connector types](./assets/destinations-catalog.png){width="800" zoomable="yes"}

-->

>[!NOTE]
>
>The displayed catalog is not the full [!DNL Adobe Experience Platform] destinations catalog. If you access destinations directly from [!DNL Experience Platform], you see a larger catalog, but only these destinations are currently available for activation in [!DNL Journey Optimizer B2B Edition]. Additional destinations are planned for future releases.

## Set up a destination {#set-up-destination}

Each supported destination card shows **[!UICONTROL Configure new destination]**. Configuring a destination is a prerequisite for activation.

1. In the connector card, click **[!UICONTROL Configure new destination]**.

   ![Configure a new destination](./assets/destinations-configure-new.png){width="500"}

1. Select **[!UICONTROL Existing account]** or **[!UICONTROL New account]** and enter the account details, such as the account name and description.

1. Click **[!UICONTROL Connect to destination]**.

   An OAuth flow lets you sign in to the corresponding account: LinkedIn, Google, or Facebook.

   >[!IMPORTANT]
   >
   >At this point, do not enter the _[!UICONTROL Destination details]_. Only the connection is needed.

1. Complete any required field mapping between people attributes and the fields required by the destination.

1. Review the data governance and marketing action settings, then click **[!UICONTROL Save]**.

For the full setup steps, see [Create a new destination connection](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination){target="_blank"} in the [!DNL Experience Platform] documentation.

When configured, the destination is available for activation everywhere that you can select a destination in [!DNL Journey Optimizer B2B Edition].

## Activation and sync {#activation-sync}

Activation is driven by static list membership, with a bidirectional sync between the list and the destination audience:

* Adding a person to the static list activates them to the destination within 24 hours, adding them to the destination audience and, subsequently, to any campaign that the audience feeds.
* Removing a person from the static list deactivates them from the destination. They are removed from the destination audience and from any connected campaign.
* The same list can be activated to multiple destinations at once. Membership syncs to all of them.

>[!TIP]
>
>To run a LinkedIn campaign against a segment, activate the static list of those people to your LinkedIn Matched Audience destination. Everyone in the list is added to the matched audience in LinkedIn, where a campaign can target them, and the audience automatically stays current as the list changes.
