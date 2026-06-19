---
title: Setup Checklist
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
# Setup checklist

Complete these tasks to enable functionality in your provisioned [!DNL Journey Optimizer B2B Prime] instance.

## Enable user access {#enable-user-access}

When provisioning is complete and sandboxes are bound, configure [!DNL Journey Optimizer B2B Edition] access for your team and users.

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
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox for task"/></td>
<td>Create a Journey Optimizer B2B Edition product profile in the Admin Console (one-time/initial setup only)</td>
<td><a href="./user-management.md#create-profile">Create profile</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox for task"/></td>
<td>Add a user group in the Admin Console</td>
<td><a href="./user-management.md#add-user-group">Add user group</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox for task"/></td>
<td>Edit built-in roles or create a custom role with product permissions</td>
<td><a href="./user-management.md#edit-role-permissions">Edit roles</a> <br/> <a href="./user-management.md#create-a-custom-role">Create a custom role</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox for task"/></td>
<td>Add users or groups to roles in Adobe Experience Platform</td>
<td><a href="./user-management.md#add-users-to-a-role">Add users</a> <br/><a href="./user-management.md#add-user-groups-to-a-role">Add groups</a></td>
</tr>
</tbody>
</table>

## Email deliverability {#email-deliverability}

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
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox for task"/></td>
<td>Delegate a subdomain to Adobe (Fully delegated or CNAME)</td>
<td><a href="./admin/configuration-email-deliverability.md#delegate-fully-delegated">Fully delegated</a> <br/> <a href="./admin/configuration-email-deliverability.md#delegate-cname">CNAME</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox for task"/></td>
<td>Configure DMARC for the subdomain</td>
<td><a href="./admin/configuration-email-deliverability.md#configure-dmarc">Configure DMARC</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox for task"/></td>
<td>Review and assign an IP pool</td>
<td><a href="./admin/configuration-email-deliverability.md#review-ip-pool">Review IP pool</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox for task"/></td>
<td>Create an email channel configuration</td>
<td><a href="./admin/configuration-email-deliverability.md#create-email-channel-configuration">Configure email channel</a></td>
</tr>
</tbody>
</table>

