---
title: Variant Split Paths
description: Learn how to use variant split path nodes to randomly distribute accounts across multiple journey paths using percentage-based allocation in Journey Optimizer B2B Edition.
feature: Account Journeys
solution: Journey Optimizer B2B Edition
role: User
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a limited beta release"
autotag-review: '2026-07-06T23:50:12.985Z'
TQID: 'https://experienceleague.adobe.com/42lSbF7J-yEzFYbFFhs2sSQ4j4NfRtENlIz-R-HcPx8'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
subfeature_v2:
  - id: c31bc6c7-76bc-467b-80c0-7315a4e3f6be
    internal-label: Account Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Variant split paths

Use a _Variant split paths_ node to randomly distribute accounts across two or more journey paths based on percentage allocations that you define. This node is useful for exploratory testing of different messaging, timing, or engagement tactics across segments of your account audience, without applying conditional rules. It is not suitable for controlled A/B experiments that require consistent per-account path assignment.

>[!AVAILABILITY]
>
>The variant split path node is currently available to select customers as a limited beta release, for **_account journeys only_**. Support for person journeys is planned for a future release. Contact your Adobe representative to get access.

## Comparison to split paths {#compare-split-paths}

Both _[Split paths](./split-merge-paths-nodes.md)_ and _Variant split paths_ divide accounts into multiple journey branches, but they use different mechanisms:

| Aspect | Split paths | Variant split paths |
| -------- | ----------- | ------------------- |
| **Assignment logic** | _Conditional rule-based_ - Each account is evaluated against defined conditions and proceeds along the first path it matches. | _Percentage-based random assignment_ - Accounts are distributed across paths according to configured percentages with no filtering conditions. |
| **Determinism** | _Deterministic_ - Same account always follows the same path as long as it matches the same conditions. | Not deterministic — the same account may follow different paths on re-entry. |
| **Use case** | Segment by known account or buying group attributes; priority-ordered evaluation. | Randomly distribute accounts for testing messaging, timing, or tactics across your account audience. |
| **Other accounts path** | _Supported_ - Accounts that do not match any defined path can be routed to a default path. | _Not applicable_ — Every account is assigned to one of the defined paths. |

## Split by account {#split-by-account}

When an account reaches a variant split paths node, the node assigns it to exactly one path based on configured percentages. The assignment uses a quota-based algorithm that tracks how many accounts have been assigned to each path and adjusts over time to maintain the configured ratios.

* Each account is assigned to exactly one path.
* Assignment is random and quota-based. The algorithm adjusts allocations dynamically to approach the configured percentages across the overall population.
* The node supports 2 to 20 paths. Each path has a configurable name and an integer percentage from 1 to 99. The sum of all path percentages must equal exactly 100%.

>[!IMPORTANT]
>
>**Quota-based algorithm: not deterministic**
>
>The distribution algorithm uses quota-based random assignment. This algorithm is **not deterministic**: the same account may be assigned to a different path each time it enters or re-enters the journey. Path assignment depends on the current quota state at the time of evaluation, not on a fixed property of the account. See [Limitations](#limitations) for details on what use cases this affects.

### Distribution algorithm {#distribution-algorithm}

The variant split paths node uses a **_quota-based random assignment_** algorithm. When an account reaches the node, the runtime evaluates how many accounts were already assigned to each path during the current journey instance and routes the account to the path that is furthest below its configured quota. There are two key properties for the algorithm:

* Distribution closely tracks the configured percentages at all account volumes. Because the algorithm actively maintains quota counts, actual distribution only drifts by at most one account per path due to rounding when totals do not divide evenly.
* The algorithm uses a pessimistic lock during quota evaluation to serialize assignments, which ensures accurate count tracking under concurrent execution.

### Limitations {#limitations}

Review these limitations before using variant split paths in your journeys.

>[!CAUTION]
>
>**Path assignment is not deterministic.**
>
>The quota-based algorithm does not guarantee that the same account always follows the same path. If an account exits and re-enters the journey, it may be assigned to a different path depending on the quota state at the time of re-entry. Do not use variant split paths for use cases that require consistent per-account path assignment across journey instances.

| Limitation | Description |
| ---------- | ----------- |
| **Not suitable for controlled experiments** | Because path assignment is not deterministic, variant split paths is **not suitable** for A/B experiments or attribution scenarios that require a given account to consistently receive the same treatment. Use cases that depend on per-account consistency — such as measuring response rates or attributing outcomes to a specific experience — may produce unreliable results. |
| **Minor rounding drift** | When the total account count is not evenly divisible by the configured percentages, distribution may be off by at most one account per path. This is expected rounding behavior and is not an error. |
| **Path assignment is not idempotent** | Re-entering the journey may produce a different path assignment for the same account. If your journey design assumes that an account always follows the same path after the split node, this assumption does not hold. |
| **Account journeys only** | Variant split paths is supported in account journeys only. Person journeys are not currently supported. |
| **No conditional filtering** | Unlike _Split paths_, variant split paths does not apply conditions. Every account that reaches the node is assigned to a path. |

## Split by people {#split-by-people}

In an account journey, you can also use a variant split paths node to randomly distribute the _people within accounts_ across percentage-based paths. This is useful when you want to test different content or experiences at the person level while accounts continue moving through the journey. The variant split path by people node operates with the following guardrails:

* The node functions as a _grouped node_, which is a split-merge combination. The split paths automatically close at a corresponding merge node so that all people can move forward without losing their account context.
* Each person in the account is assigned to exactly one path based on the configured percentages.
* The same quota-based algorithm used for accounts applies to people. The path assignment is not deterministic and the same person may follow a different path on re-entry.
* Only _[!UICONTROL Take an action]_ nodes for people are supported within the paths. The paths cannot be split further.

>[!BEGINSHADEBOX "Distribution behavior across people"]

People within an account are processed as a batch. The number assigned to each path is calculated as `floor(percentage / 100 × people_in_account)`, and the **last configured path receives all remaining people**. This means:

* When an account has an odd number of people, the last path receives one more person than earlier paths.
* For accounts with a single person, that person is always assigned to the first path regardless of configured percentages.
* For accounts with very few people (fewer than 10), the per-account distribution may differ noticeably from the configured percentages. Distribution converges toward the configured ratios when measured across many accounts.

>[!NOTE]
>
>This rounding behavior applies per account batch, not across all accounts in the journey. The last path systematically receives slightly more people than configured when account sizes are odd. This is expected behavior.

>[!ENDSHADEBOX]

## Add a variant split paths node {#add-variant-split-paths-node}

1. Navigate to the journey map.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Variant split paths]**.

   ![Add journey node - variant split paths](./assets/node-variant-split-paths-add.png){width="300" zoomable="no"}

   The added node has two paths to start.

1. In the node properties on the right, choose either **[!UICONTROL Accounts]** or **[!UICONTROL People]** for the split.

   If you are using a split path by people, a _Close variant split paths_ node is automatically inserted to close the grouped split.

   ![Journey canvas - variant split by people with auto-inserted close node](./assets/node-variant-split-paths-people-canvas.png){width="700" zoomable="yes"}

1. Review or update the **[!UICONTROL Label]** for each path.

   Path labels appear as edge labels on the journey canvas and help distinguish paths in journey analytics.

   ![Variant split paths node - path name configuration](./assets/node-variant-split-paths-names.png){width="600" zoomable="yes"}
   
1. Set the **[!UICONTROL Percentage]** for each path.

   Values must be integers from 1 to 99.

   ![Variant split paths node - path percentage configuration](./assets/node-variant-split-paths-config.png){width="500" zoomable="yes"}

   The running total indicator shows the sum of all path percentages. The total must equal exactly 100% before you can publish the journey. An error state is displayed when the total does not equal 100%.

   ![Variant split paths node - validation error when total does not equal 100%](./assets/node-variant-split-paths-validation-error.png){width="500" zoomable="yes"}

   To distribute percentages evenly across all paths, click **[!UICONTROL Distribute evenly]**. The system calculates equal shares and adjusts any rounding to ensure the total equals 100%.

1. To define additional paths, click **[!UICONTROL Add path]** for each one.

   The node supports up to 20 paths. As you add more paths, adjust the _[!UICONTROL Percentage]_ so that the total equals 100%. 
   
   You can remove a path by clicking the _Delete_ ( ![Delete icon](../assets/do-not-localize/icon-delete-outline.svg) ) icon in the path card. A path can be removed only when at least two paths remain.

### Validation rules {#validation-rules}

The following rules apply to variant split path configuration. Violations block journey publish.

| Rule | Requirement |
| ---- | ----------- |
| Minimum paths | 2 |
| Maximum paths | 20 |
| Percentage per path | Integer from 1 to 99 |
| Total percentage | Must equal exactly 100% |
