---
title: Audience Management
description: Placeholder page for audiences.
autotag-review: '2026-06-12T22:47:10.727Z'
TQID: 'https://experienceleague.adobe.com/KWT9-Lr6358MQ0sLQyKAlb4SLERnBl-QQL7Cj1iXCZM'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Audience management

From the Marketing management hub, click **[!UICONTROL People lists]** in the right navigation.

![Access people lists to manage your audiences](./assets/people-lists.png){width="800" zoomable="yes"}

There are two tabs for the page where you can view and manage of **[!UICONTROL Dynamic lists]** and **[!UICONTROL Static lists]**. Click the tab to switch the list view between each type.

From this page you can:

* Create new dynamic and static lists
* Search for existing lists
* See asset information
* Access lists to review their membership

<!--
## Audience Hub

The AI Audience Hub is a centralized, AI-driven starting point for all audience-related capabilities across AJO B2B. It is designed to accelerate first-time user success while progressively unlocking advanced intelligence, insights, and control for returning and power users.

The Hub acts as:

* A guided starting point for discovering, creating, and refining person lists, account lists, and buying groups

* A visibility layer for audience health, coverage, overlap, engagement patterns, and AI-driven insights

* A control center for audience governance, optimization, reuse, and readiness for activation across journeys and sales workflows

### High level structure

Prompt-based starting point - Quick Start prompts and freeform input to help users discover, create, or optimize audiences.

1. AI insights feed - Surfaces key audience signals such as overlap, gaps, saturation risk, and optimization opportunities.

1. Adaptive audience library - A personalized view of people lists, account lists, and buying groups that adapts based on usage, relevance, and activation.

1. Optimization and arbitration nudges - Guides users to refine, split, or reuse audiences before activation.

1. Audience visibility and reporting - High-level insight into audience health, engagement patterns, and usage across active journeys.


### Empty and Error States (High-Level)

No audiences / no data - Show Quick Start prompts to help first-time users create or import person lists

Low data or incomplete audience - Explain what's missing (e.g., insufficient contacts, missing persona coverage, or low engagement data) and suggest next steps.

AI insights unavailable - Provide a graceful fallback with a clear explanation, so users understand why insights aren't shown and what actions they can take manually.
-->

## Create a people list


To create a dynamic or static list:

1. Click **[!UICONTROL Create list]** at the top right of the _[!UICONTROL People lists]_ page.
1. Select a program as the **[!UICONTROL Parent]** for the list.
1. Enter the list a **[!UICONTROL Name]** and **[!UICONTROL Description]** (optional).
1. Choose then list **[!UICONTROL Type]**:

   * **[!UICONTROL Static]** - Membership is determined by qualifying filters evaluated when you create the list. The list membership does not update unless you manually qualify or disqualify records.
   ***[!UICONTROL  Dynamic]** - Membership is dynamically determined by qualifying filters. The list membership refreshes automatically.

1. Click **[!UICONTROL Create]**.

>[!NOTE]
>
>Delete and dulicate are not currently supported for people lists in this Beta release.

## Static lists

Static list membership is defined by simple filters that reference people attributes and activities. Membership does not change unless you manually qualify or disqualify members.

>[!NOTE]
>
>Static List filter definitions are applied only once when you add to or remove members from the list. The defined filter is not available afterwards. If you want to maintain a consistent audience definition using filters, use a dynamic list instead.

### Add members

1. Open the static list and click **[!UICONTROL Add people]** at the top right.

1. In the dialog, define the rules for qualifying your leads by dragging and dropping filters from the left. 

   You can filter people using any combination of:

   * Activity history
   * Company attributes
   * Person attributes
   * Special filters such as Journey membership

1. To save your changes, click **[!UICONTROL Done]**.

1. Select the **[!UICONTROL Members]** tab. 

   After a brief time, qualifying members appear in the list.

### Remove members

1. Open the static list and click **[!UICONTROL Remove people]** at the top right.

1. In the dialog, add the filters to maatch members that you want to disqualify.

1. To save your changes, click **[!UICONTROL Done]**.

1. Select the **[!UICONTROL Members]** tab. 

   After a brief time, disqualified members leave the list.

## Dynamic lists

Dynamic list membership is defined using simple filters that reference people attributes and activities. Membership is automatically maintained by qualifying and disqualifying leads according to the filter logic.

### Define the membership logic

1. Open the static list and select the Rules tab.

1. Click the Edit rules.

1. In the dialog, define the rules for qualifying your leads by dragging and dropping filters from the left.

   You can qualify leads for the list using any combination of:

   * Activity history
   * Company attributes
   * Person attributes
   * Special filters such as Journey membership

1. To save your changes, click **[!UICONTROL Done]**.

1. Select the **[!UICONTROL Members]** tab. 

   After a brief time, qualifying members appear in the list.

To open the lead profile detail page where you can view the summary and recent activities, click the name of a person in the list.