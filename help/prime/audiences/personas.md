---
title: Derived Personas
description: Use derived personas in Journey Optimizer B2B Prime to target people lists and journey paths. Learn default persona mappings and the Derived Persona filter.
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a limited beta release"
autotag-review: '2026-06-23T22:01:21.605Z'
TQID: 'https://experienceleague.adobe.com/OZ4GDkaqg9a5Aikic-m-f0MtHSpc3BO0h41fTAL1Rww'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
  - id: c3d6e661-d372-4e98-9fd9-eac771e7e4ee
    internal-label: Decisioning
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Derived personas

Persona classification transforms raw customer data into semantic buyer understanding that AI can use to generate context and drive personalized decisions across every channel and journey. This unified profile empowers:

* _Journey branching_ – Split paths route leads by persona, engagement depth, and role
* _Journey arbitration_ – Determines which nurture a lead belongs to right now, avoiding message collisions across concurrent programs
* _Content personalization_ – Content that is role-specific narratives ("for an executive" vs. "for a practitioner")
* _Sales Qualifier context_ – BDRs get a one-screen brief showing "who this person is, what they care about, where they are in the buyer journey"

## Default personas {#default-ersonas}

For the Beta release of Journey Optimizer B2B Prime, the following default personas are defined according to the job title attribute:

| Persona | Job titles |
| ------- | ---------- |
| [!UICONTROL CXO / EVP] | CEO, CIO, CTO, CMO, CFO, Executive Vice President of Strategy |
| [!UICONTROL SVP / VP] | SVP of Marketing, VP of Sales, SVP of Operations, VP of Product, VP of IT |
| [!UICONTROL Senior Manager / Manager] | Senior Marketing Manager, IT Manager, Operations Manager, Sales Manager, HR Manager |
| [!UICONTROL Individual Contributor] | Account Executive, Software Engineer, Marketing Specialist, Customer Success Representative |
| [!UICONTROL Analyst] | Business Analyst, Data Analyst, Market Research Analyst, Financial Analyst, Operations Analyst |
| [!UICONTROL Developer] | Front-End Developer, Back-End Developer, Full-Stack Developer, Mobile App Developer, DevOps Engineer |
| [!UICONTROL Professional Staff] | HR Specialist, Legal Counsel, Compliance Officer, Project Manager, Procurement Specialist |
| [!UICONTROL Consultant] | Management Consultant, IT Consultant, Business Process Consultant, Marketing Consultant |
| [!UICONTROL Other] | Industry Specialist, Independent Advisor, Freelance Consultant, Subject Matter Expert |

>[!NOTE]
>
>In the General Availablity release, you will be able to edit any of these default personas according to the needs of your organization. It will also support custom persona definitions and mapping.

## Filter by derived persona {#derived-persona-filter}

Journey Optimizer B2B Prime derives a persona for each person record by evaluating the record's attributes against the defined personas. You can use the inferred result — the _Derived Persona_ — as a filter when defining the audience for a people list or for segmenting in a person journey.

The _[!UICONTROL Derived Persona]_ filter appears in the filter panel under the **[!UICONTROL Person attributes]** category.

### People lists {#people-lists}

When you add or remove members from a [static people list](./people-lists.md#static-list), or when you define the membership rules for a [dynamic people list](./people-lists.md#dynamic-lists), you can filter by Derived Persona to target all people whose attributes match a specific configured persona.

![Derived persona filtering for a people list](./assets/derived-persona-filter-people-list.png){width="750" zoomable="yes"}

**Static list — Add members**

1. Open the static list and click **[!UICONTROL Add people]** at the top right.

1. In the filter dialog, expand **[!UICONTROL People attributes]** and drag **[!UICONTROL Derived Persona]** onto the canvas.

1. In the filter condition, choose **[!UICONTROL is]** and select one or more personas from the list.

1. Click **[!UICONTROL Done]** to apply the filter and qualify matching people into the list.

**Dynamic list — Set membership rules**

1. Open the dynamic list and select the **[!UICONTROL Rules]** tab.

1. Click **[!UICONTROL Edit rules]**.

1. In the filter dialog, expand **[!UICONTROL People attributes]** and drag **[!UICONTROL Derived Persona]** onto the canvas.

1. In the filter condition, choose **[!UICONTROL is]** and select one or more personas from the list.

1. Click **[!UICONTROL Done]** to save the rule.

   Membership is updated automatically as person records are evaluated against the rule.

### Person journeys {#person-journeys}

When you configure segmentation for a person journey in a [_Split paths_ node](../marketing/split-merge-paths-nodes.md), you can use a derived persona as a person profile filter to control which people enter the journey path.

![Derived persona filtering for a split path condition](./assets/derived-persona-filter-split-path.png){width="750" zoomable="yes"}

1. Click the **[!UICONTROL Split paths]** node in the journey canvas.

1. In the node properties panel on the right, click **[!UICONTROL Apply condition]** or **[!UICONTROL Edit condition]** for a path.

1. In the filter dialog, expand **[!UICONTROL People attributes]** and drag **[!UICONTROL Derived Persona]** onto the canvas.

1. In the filter condition, choose **[!UICONTROL is]** and select one or more personas from the list.

1. Click **[!UICONTROL Done]** to save the filter for the path.
