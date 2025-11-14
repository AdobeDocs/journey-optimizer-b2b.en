---
title: Completeness Scores for Buying Groups
description: Calculate buying group completeness scores using role-based thresholds, customizable member requirements, and completeness settings in Journey Optimizer B2B Edition.
feature: Buying Groups
role: User
---

# Completeness scores {#completeness-scores}

>[!CONTEXTUALHELP]
>id="ajo-b2b_buying_group_completeness_score"
>title="Completeness score"
>abstract="Completeness scores reflect how well the buying group membership is aligned for a sales-ready buying group."

A completeness score is a percentage that indicates how well a buying group is populated with the required members across its defined roles. These scores are based on role member thresholds that you configure in the roles template and the actual number of members assigned to each role in the buying group. The resulting scores help marketers evaluate sales readiness and identify gaps in buying group composition. Score calculation occurs automatically as buying group membership changes.

![Buying group completeness scores](./assets/buying-group-details-page-completeness-scores.png){width="800" zoomable="yes"}

There are two types of completeness scores:

* **Buying group completeness score** - The buying group completeness score is a percentage between 0% to 100% and represents the overall completeness of the buying group based on role-level completeness calculations.

   The buying group completeness score is displayed in the [Buying group details](./buying-group-details.md) page. This score provides an at-a-glance view of whether the buying group has the required stakeholders in place for sales engagement.

* **Role completeness score** - The role completeness score is a percentage for each individual role within a buying group, based on the number of members assigned to that role.

   The role completeness score for each role is displayed in the buying group details page when you edit roles and adjust completeness settings. These scores help you identify which specific roles need additional members to reach the sales-ready threshold.

   The details page displays the first two role completeness scores with an n_+ link for any additional roles. Click the link to view the additional role completeness scores.

Completeness scores reflect the current state of buying group membership and update automatically as members are added or removed. Displayed scores are shown as whole percentages (for example, a score of 66.67% is displayed as 67%).

## Evaluate sales readiness

Adobe Journey Optimizer B2B Edition equips marketers with tools that ensure buying groups align with real decision-making processes. You can define complete buying groups using customizable role member thresholds that reflect your organization's sales methodology. By setting minimum and maximum member requirements for each role, you establish clear criteria for what constitutes a sales-ready buying group.

The buying group completeness score provides an accurate measure of sales readiness for the group. For example, to complete an opportunity for a specific solution, you might need at least two decision makers, one influencer, and at least one practitioner. The completeness score calculation accounts for each of these role-specific requirements, providing a view of overall buying group readiness.

## Measure journey effectiveness

Buying group completeness acts as a key performance indicator (KPI) for journey effectiveness. The goal for a specific journey may be to increase buying group completeness by a certain percentage or to achieve a minimum threshold before triggering sales-ready alerts. 

In a large enterprise, you might identify one person per role. However, that person may not be the right contact for the sale, or you may need multiple contacts in critical roles. For example, a large organization may have several information technology (IT) decision makers distributed across departments or business units. Identifying one decision maker may not be enough for a complex enterprise sale.

After you analyze the current buying group completeness, you can adjust the required number of contacts for each role in the roles template. These adjustments allow you to tune your buying group strategy based on real-world patterns and sales outcomes.

<!-- ## Analyze audiences for journey optimization

Marketers can view the starting buying group completeness score of target account audiences to find the best performance indicators for a solution. This visibility enables marketers to:

* Determine if they need to adjust the completeness score requirements for each role to make journeys more effective.
* Identify which buying groups are closest to sales-ready status and prioritize them for acceleration campaigns.
* Segment buying groups by completeness score ranges and create tailored nurture strategies for different maturity levels.

>[!BEGINSHADEBOX]

The buying group completeness score is available to use for filtering in [journey split-path-by-account nodes](../journeys/split-merge-paths-nodes.md#account-path-filters) and for audience segmentation. Role completeness can be used to create personalized content that addresses specific gaps in buying group composition.

>[!ENDSHADEBOX] -->

## Role completeness calculation {#role-completeness-calculation}

>[!CONTEXTUALHELP]
>id="ajo-b2b_buying_group_role_completeness_calculation"
>title="Role completeness calculation"
>abstract="Role completeness scores are calculated as a percentage based on the number of members assigned to a role."

Journey Optimizer B2B Edition calculates the completeness score for each individual buying group role as a percentage. Base this score on how many members are assigned to the role, compared to [the number required in the roles template](./buying-groups-role-templates.md#change-the-completeness-score-settings) for completion.

The role completeness calculation is a linear percentage between zero and the specified threshold (members required):

* If the number of assigned members is **zero**, the role completeness is **0%**.
* If the number of assigned members is **at or above the threshold**, the role completeness is **100%**.
* If the number of assigned members is **between one and the threshold**, the completeness is calculated proportionally.

### Role completeness formula

The role completeness percentage is calculated using the following formula:

```text
Role Completeness % = ((Assigned Members - Threshold) / (Threshold)) × 100
```

Where:

* `Assigned Members` = Current number of members in the role
* `Threshold` = Members required value set in the roles template

### Role completeness examples

The following examples illustrate role completeness calculations with different threshold configurations:

| Role | Members required | Assigned members | Calculation | Role completeness |
|------|------------------|------------------|-------------|-------------------|
| Decision Maker | 3 | 0 | None | 0% |
|  |  | 1 | 1/3 × 100 | 33% |
|  |  | 2 | 2/3 × 100 | 66% |
|  |  | 3 | At threshold | 100% |
|  |  | 4 | Above threshold | 100% |
| Influencer | 5 | 0 | None | 0% |
|  |   | 1 | 1/5 × 100 | 20% |
|  |   | 2 | 2/5 × 100 | 40% |
|  |   | 3 | 3/5 × 100 | 60% |
|  |   | 4 | 4/5 × 100 | 80% |
|  |   | 5 | At threshold | 100% |
|  |   | 6 | Above threshold | 100% |

## Buying group completeness calculation {#buying-group-completeness-calculation}

The buying group completeness score aggregates the individual role completeness scores. This calculation provides a holistic view of buying group readiness across all defined roles.

### Buying group completeness formula

The buying group completeness percentage is calculated using the following formula:

```text
Buying Group Completeness % = Σ(Role Completeness %) / Number of defined roles
```

Where:

* `Role Completeness %` = Individual role completeness percentage (0-100%)
* `Σ` = Sum across all roles in the buying group

<!--

## Use completeness scores in journeys

Use buying group completeness scores and role-level completeness scores to optimize your account journeys and personalize engagement strategies.

### Split paths by completeness

Use completeness thresholds in [journey split-path-by-account nodes](../journeys/split-merge-paths-nodes.md#account-path-filters) to route buying groups through different journey paths based on their readiness. For example:

* **High completeness path** (≥70%) - Buying groups that are nearly sales-ready can be routed to sales teams or receive call-to-action campaigns
* **Medium completeness path** (40-69%) - Buying groups in active development receive nurture campaigns focused on filling specific role gaps
* **Low completeness path** (<40%) - Newly formed buying groups receive awareness and education content to build initial engagement

### Trigger actions based on completeness milestones

Set up journey events that trigger specific actions when buying groups reach completeness milestones. FOr example:

* Alert sales teams when a buying group reaches 70% completeness.
* Send a _stakeholder alignment_ campaign when completeness increases by 20% or more within a defined timeframe.
* Trigger an automated assessment when a buying group stalls at the same completeness level for an extended period.

By leveraging completeness scores throughout the journey, you create more targeted, efficient campaigns that align with the actual composition and maturity of your buying groups.

-->