---
title: Setup
description: Complete initial setup tasks for your Journey Optimizer B2B Prime instance, including user access configuration and email deliverability infrastructure.
autotag-review: '2026-06-12T23:06:52.179Z'
TQID: 'https://experienceleague.adobe.com/D8qXM-F4anA8IVYmdlaclUoxgTwqQptN36xYFpsuvHY'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: d6e625c1-468f-4d73-9f32-fd1edb87f96b
    internal-label: Administration
  - id: f467931a-9b22-4ca8-869f-adfbd64061ce
    internal-label: Onboarding
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
  - id: f6df9def-cdf7-4728-9ec8-3f65716828c7
    internal-label: Setup
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Setup

Complete these tasks to enable functionality in your provisioned Journey B2B Prime instance.

## Enable user access

When provisioning is complete, sandboxes are bound, and initial setup tasks are complete, configure Journey Optimizer B2B Edition and Marketo Engage access for your team and users.

<table>
<thead>
<tr>
<th colspan="2">Task</th>
<th>Details and instructions</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>Provide product access and permissions</strong> for users</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Create a Marketo Engage product profile in the Adobe Admin Console (new Marketo Engage instance only)</td>
<td><a href="./user-management.md#create-profile">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Add a user group for the profile</td>
<td><a href="./user-management.md#add-user-group">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure B2B user roles</td>
<td><a href="./user-management.md#edit-roles-for-product-permissions">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Add users or groups to the roles</td>
<td><a href="./user-management.md#add-users-to-a-role">Learn more</a></td>
</tr>
</tbody>
</table>

## Email deliverability

Before marketers can send email from journeys, configure the sending infrastructure for your organization, including subdomain delegation, email authentication, and channel settings.

<table>
<thead>
<tr>
<th colspan="2">Task</th>
<th>Details and instructions</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>Configure email deliverability and channel settings</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Delegate a subdomain to Adobe</td>
<td><a href="./admin/configuration-email-deliverability.md#delegate-fully-delegated">Fully Delegated</a> or <a href="./admin/configuration-email-deliverability.md#delegate-cname">CNAME</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure DMARC for the subdomain</td>
<td><a href="./admin/configuration-email-deliverability.md#configure-dmarc">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Review and assign an IP pool</td>
<td><a href="./admin/configuration-email-deliverability.md#review-ip-pool">Learn more</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Create an email channel configuration</td>
<td><a href="./admin/configuration-email-deliverability.md#create-email-channel-configuration">Learn more</a></td>
</tr>
</tbody>
</table>
<!-- -->

