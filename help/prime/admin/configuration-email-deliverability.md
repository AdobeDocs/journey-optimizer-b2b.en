---
title: Email deliverability and channel configuration
description: Configure subdomain delegation, DMARC, SPF, DKIM, IP pools, and email channel configurations for Journey Optimizer B2B Prime.
hide: true
---
# Email deliverability and channel configuration

[!DNL Adobe Journey Optimizer B2B Edition] Prime brings a modern, enterprise-grade email authoring and delivery experience to B2B marketers. This release introduces redesigned email design tools and a complete set of email deliverability controls.

The following information is for administrators who configure sending infrastructure to support marketers and email authors. It describes deliverability features, roles and permissions, and how to configure subdomains, authentication, IP pools, and channel configurations.

For detailed information about creating emails and authoring email content in the email design space, see [Email authoring](../content/email-authoring.md).

## Email channel overview {#overview}

* **Visual drag-and-drop email design tools** -  Design your email content with structures, content components, themes, dark-mode support, and reusable visual fragments.
* **Email channel configurations** - Manage the sender identity, reply behavior, marketing vs. transactional message types, and tracking.
* **Email deliverability controls** - Set up your email deliverability channel, including subdomain delegation (Fully Delegated and CNAME methods), DMARC, SPF/DKIM auto-configuration, and shared IP pool support.
* **Send Email action** - From a journey, add a Send email action, including personalization using profile attributes (Handlebars syntax).
* **Marketo Design Studio assets** — choose images and assets from a one-time copy of your Marketo Engage asset library directly inside the email canvas.
* **Reusable templates and fragments** — Save common headers, footers, CTAs, and full email layouts and reuse them across journeys.
* **Role-Based Access Control (RBAC)** — apply granular permissions for creating, editing, approving, and sending email.

## Key concepts {#key-concepts}

Before configuring email, review these concepts that apply to email channel features throughout the product.

| Concept | What it means in [!DNL Journey Optimizer B2B Edition] Prime |
| ------- | ---------------------- |
| **_Channel configuration_** | A reusable set of email-sending settings — including sender identity, reply-to address, subdomain, IP pool, email type (marketing or transactional), and tracking — that you attach to email actions in journeys. You can have multiple named channel configurations for different brands, business units, or send types. |
| **_Subdomain_** | A delegated portion of your sending domain (for example, `mail.contoso.com`) used to send email through Prime. Subdomains isolate your B2B marketing reputation from corporate or transactional mail. |
| **_IP pool_** | A group of IP addresses associated with one or more subdomains. Prime supports a shared IP pool managed by Adobe in this release; dedicated IP pools are on the GA roadmap. |
| **_Email design space_** | The visual canvas and design tools used to compose email content. It includes drag-and-drop layout components, templates, fragments, themes, and a personalization editor. |
| **_Template_** | A reusable email layout that is available for creating a new email. It can be either a built-in sample template provided by Adobe or a custom-built template created by your team. |
| **_Visual fragment_** | A reusable block of content (such as a header, footer, CTA, legal disclaimer) that can be inserted into multiple emails. Updating a fragment propagates the change to every email that uses it. |
| **_Theme_** | A reusable styling preset (colors, typography, spacing, button styles) applied across an email. |
| **_Personalization token_** | A Handlebars expression — for example, `{{profile.firstName}}` — resolved at send time using each recipient's profile data. |
| **_Send Email action_** | The journey action node that uses a channel configuration and email content to deliver an email. |

## Roles and permissions {#roles-permissions}

[!DNL Journey Optimizer B2B Edition] Prime uses role-based access control (RBAC) for email features. Permissions are managed in the Adobe Admin Console (IMS) and synced at login. Product administrators assign granular permissions to product profiles, and then attach those product profiles to users.

Access to email functionality in [!DNL Journey Optimizer B2B Edition] Prime is gated by two layers:

1. **Feature flag (LD).** A LaunchDarkly flag controls whether the entire feature is turned on for your organization. Email authoring and deliverability are gated by `dx_ajo_btob_channel_foundation`. Without this flag, the feature is hidden regardless of permissions.
2. **Functional permission.** A user-level permission that controls whether a specific user can read or write within a feature.

Most email features follow a `view-*` (read) and `manage-*` (write) pattern. A user needs the read permission to see a feature in the navigation, and the write permission to create, edit, or delete within it.

### Email authoring permissions {#email-authoring-permissions}

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **View emails** | `view-b2b-emails` | View the email list, open emails, view content (read-only). |
| **Create / edit / delete emails** | `manage-b2b-emails` | All read access plus create, edit, duplicate, and delete emails. Required to author email content within a journey. |
| **View templates** | `view-b2b-templates` | Browse and preview templates in the Templates gallery (read-only). |
| **Create / edit / delete templates** | `manage-b2b-templates` | All read access plus create, edit, and delete saved templates. |
| **View fragments** | `view-b2b-fragments` | Browse and preview visual fragments (read-only). |
| **Create / edit fragments** | `manage-b2b-fragments` | All read access plus create and edit visual fragments. |
| **Publish fragments** | `publish-b2b-fragments` | Publish a fragment so it becomes available to email authors across the organization. |
| **Manage shared assets and library items** | `manage-b2b-library-items` | Manage the underlying shared library used by templates, fragments, and emails. Often granted alongside the template/fragment manage permissions. |
| **Manage usage labels** | `manage-b2b-delete-usage-labels` | Manage data usage labels (DULE) attached to library items for governance. |
| **Manage packages** | `manage-b2b-packages` | Bundle and move templates, fragments, and emails between sandboxes. |
| **View assets (Marketo Design Studio assets in Prime)** | `view-b2b-assets` | Browse the asset picker and preview images. Read-only. |
| **Manage assets** | `manage-b2b-assets` | All read access plus future asset-management actions (Beta scope). |
| **Export message data** | `manage-b2b-message-export` | Export email-level message data and reports. |

Within a journey, the **Send email** action requires `manage-b2b-person-journeys` (to add the action and activate the journey). A user with only email permissions can author content but cannot add an email to a journey.

### Email deliverability permissions {#email-deliverability-permissions}

Deliverability features (subdomains, DMARC, IP pools, suppression lists, allowed lists, IP warmup plans, and seed lists) are administrator-level configuration. They are governed by two permissions covering the entire **[!UICONTROL Channels]** > **[!UICONTROL Email settings]** area:

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **View email settings** | `view-b2b-email-settings` | View subdomains, PTR records, IP pools, suppression list, allowed list, IP warmup plans, and seed lists (read-only). |
| **Manage email settings** | `manage-b2b-email-settings` | All read access plus delegate subdomains, configure DMARC, manage suppression and allowed lists, manage IP warmup plans and seed lists. |

Some sub-features within Email settings are gated by additional LaunchDarkly flags — Suppression list (`enable-suppression`), Allowed list (`enable-allow-list`), Seed lists (`enable-seedlist-ui`). If a sub-feature is not visible in your organization, check with your Adobe representative on flag enablement.

### Channel configuration permissions {#channel-configuration-permissions}

Channel configurations sit under **[!UICONTROL Channels]** → **[!UICONTROL General settings]**. They tie deliverability primitives (subdomain, IP pool, sender identity) to a reusable object that journey authors reference. They are governed by a single permission:

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **Manage channel configurations** | `manage-b2b-channels-configurations` | View, create, edit, and delete email channel configurations. |

## Email deliverability overview {#deliverability-overview}

Email deliverability in [!DNL Journey Optimizer B2B Edition] Prime is the set of infrastructure and authentication configurations that help email messages reach the recipient's inbox, not the spam folder, and not blocked by ISPs (Internet Service Providers).

It uses the following building blocks, configured by an administrator, typically in the following order:

1. Delegate one or more subdomains to Adobe.
1. Configure DMARC, SPF, and DKIM records on each subdomain.
1. Confirm the IP pool that will send email for your subdomain.
1. Create one or more email channel configurations that bind a subdomain, IP pool, and sender identity.
1. Use those channel configurations in journey email actions.

>[!TIP]
>
>Treat deliverability setup as a one-time administrator activity per business unit or brand. When configured, marketers and email authors do not need to revisit it.

## Subdomain delegation {#subdomain-delegation}

Subdomain delegation tells the internet that Adobe is authorized to send email on behalf of a specific subdomain (for example, `mail.contoso.com`) of your domain. Delegating a dedicated subdomain — rather than your root domain — protects your corporate mail and results in a 

* **Reputation isolation.** Marketing sends are kept separate from corporate mail. If marketing reputation dips, your transactional and corporate mail are not affected.
* **Faster IP warmup.** Dedicated subdomains help establish positive sender reputation more quickly with ISPs.
* **Modern authentication.** SPF, DKIM, and DMARC can be set up cleanly per subdomain without affecting other mail flows.
* **Compliance.** Helps meet bulk-sender requirements from Gmail, Yahoo, and other major ISPs.

>[!NOTE]
>
>Each subdomain in Prime can only be used by one Adobe product. You cannot share the same sending subdomain between Prime and another product such as Adobe Marketo Engage or Adobe Campaign — you must use distinct subdomains.

### Supported methods

Prime supports two of the three subdomain delegation methods at Alpha. The third method (Custom Delegation) is on the roadmap.

| Method | When to use | What it involves |
| ------ | ----------- | ---------------- |
| **Fully Delegated** | Recommended | Delegate full DNS authority for the subdomain to Adobe. Adobe creates and maintains MX, SPF, DKIM, DMARC, A, and CNAME records. Lowest operational overhead. Adobe handles DNS changes for you. |
| **CNAME** | For restricted policies | Keep DNS authority on your side and create CNAME records pointing to Adobe-managed records. Use this when your organization's DNS policy does not allow full delegation. You are responsible for maintaining DNS records. |
| **Custom Delegation** | Roadmap (GA) | Maintain full ownership of DNS and SSL certificates. Provides maximum control, including the ability to use your own certificates. This is targeted for the GA release. |

### Delegate a subdomain (Fully Delegated method) {#delegate-fully-delegated}

>[!PREREQUISITES]
>
>* Decide on a subdomain naming convention (for example, `mail.contoso.com` for marketing, `alerts.contoso.com` for transactional).
>* Confirm with your IT/DNS team that they can delegate the subdomain (NS records) to Adobe.
>* Create the new subdomain in your DNS provider, then wait 24–48 hours for DNS propagation before delegating to Adobe.
>* Confirm you have the Administrator role in Prime.

1. [!DNL Adobe Journey Optimizer B2B Edition] Prime, navigate to **[!UICONTROL Administration]** → **[!UICONTROL Channels]** → **[!UICONTROL Email settings]** → **[!UICONTROL Subdomains]**.
1. Click **[!UICONTROL Set up subdomain]**.
1. Enter the full subdomain name (for example, `mail.contoso.com`).
1. Choose **[!UICONTROL Fully Delegated]** as the delegation method.
1. Configure DMARC for the subdomain (see [DMARC, SPF, and DKIM](#dmarc-spf-dkim)). 

   At minimum, set up a DMARC record with a starting policy of `none` so you can monitor reports without affecting delivery.

1. Review the list of DNS records for Adobe to manage. 

   These typically include MX, SPF, DKIM, DMARC, A, and CNAME records (for tracking and mirror-page URLs).

1. Download the DNS records as a CSV file using the **[!UICONTROL Download records]** button. Share this file with your DNS team.

1. Your DNS team adds the NS records in your domain hosting solution that delegate the subdomain to Adobe.

1. After your DNS team confirms the records are in place, return to [!DNL Journey Optimizer B2B Edition] Prime and check the box confirming that you have created the required records on the hosting site.

1. Click **[!UICONTROL Submit]** to initiate a series of validation checks (pre-validation, MX, SPF, DKIM, DMARC, FBL registration).

1. Wait for the subdomain status to change to **[!UICONTROL Success]**.

   This typically takes a few minutes once DNS propagation is complete.

>[!NOTE]
>
>If validation fails, the status changes to **[!UICONTROL Failed]** and [!DNL Journey Optimizer B2B Edition] Prime displays the reason (for example, NS record not found, MX record missing, or DMARC misconfigured). Fix the underlying DNS issue, then retry submission.

### Delegate a subdomain (CNAME method) {#delegate-cname}

Use this method only if your organization's DNS policy prohibits full delegation. With CNAME, you maintain DNS records on your side.

1. In [!DNL Adobe Journey Optimizer B2B Edition] Prime, navigate to **[!UICONTROL Administration]** → **[!UICONTROL Channels]** → **[!UICONTROL Email settings]** → **[!UICONTROL Subdomains]**.
1. Click **[!UICONTROL Set up subdomain]**.
1. Enter the full subdomain name.
1. Choose **[!UICONTROL CNAME]** as the delegation method.
1. Configure DMARC for the subdomain ([DMARC, SPF, and DKIM](#dmarc-spf-dkim)).
1. Review the list of CNAME records that Prime generates — these point your subdomain's components to Adobe-managed records.
1. Download the records as CSV and share with your DNS team.
1. Your DNS team adds each CNAME record to your DNS hosting solution.
1. Once records are in place and propagated, return to Prime and confirm. Click **[!UICONTROL Submit]**.
1. Wait for status to reach **[!UICONTROL Success]**.

>[!IMPORTANT]
>
>With CNAME, Adobe cannot help you change, maintain, or troubleshoot DNS for the subdomain. Any future changes — for example, adding a new CNAME for a feature update — must be made by your DNS team.

### Subdomain guardrails {#subdomain-guardrails}

* **Default limit:** 10 subdomains per organization. Contact your Adobe representative if you need more (up to 100 depending on contract).
* **DNS propagation:** Allow 24–48 hours for changes to propagate globally. Validation can fail simply because DNS has not yet propagated.
* **Subdomain reuse:** A subdomain that is already used by another Adobe product (Marketo Engage, Adobe Campaign) cannot be reused in Prime.

## DMARC, SPF, and DKIM {#dmarc-spf-dkim}

DMARC, SPF, and DKIM are email authentication standards. Together they prove to receiving mail servers that your message is genuinely sent on behalf of your domain and has not been spoofed. Modern ISPs — Gmail, Yahoo, Microsoft — require these standards for bulk senders.

| Record | Stands for | Purpose |
| ------ | ---------- | ------- |
| **SPF** | Sender Policy Framework | Lists the mail-server IPs allowed to send mail from your domain. Receiving servers reject mail from IPs not on this list. Adobe creates and maintains the SPF record automatically when you delegate a subdomain (Fully Delegated). |
| **DKIM** | DomainKeys Identified Mail | A cryptographic signature added to every outbound email. The receiving server verifies the signature against a public key published in DNS. Adobe automatically generates DKIM keys and DNS records during subdomain delegation. |
| **DMARC** | Domain-based Message Authentication, Reporting & Conformance | Tells receiving servers what to do if SPF or DKIM fails — and gives you reports about authentication results. DMARC has three policy modes: none, quarantine, and reject. |

### DMARC policy modes

| Policy | Action | When to use |
| ------ | ------ | ----------- |
| `none` | Monitor | The receiving server does nothing if DMARC fails — but still sends a report. Use this when first delegating a subdomain to confirm authentication is working without risking message loss. |
| `quarantine` | Quarantine | The receiving server places failing messages in the spam/junk folder. |
| `reject` | Reject | The receiving server rejects (bounces) messages that fail authentication. Strictest mode. Recommended once you are confident in your authentication setup. |

### Configure DMARC {#configure-dmarc}

DMARC is configured at the time of subdomain delegation, but you can also add or update DMARC for an already-delegated subdomain.

1. Navigate to **[!UICONTROL Administration]** → **[!UICONTROL Channels]** → **[!UICONTROL Email settings]** → **[!UICONTROL Subdomains]**.

1. In the Subdomains list, locate your subdomain and check the DMARC Record column. 

   If a record is missing, an alert is displayed.

1. Open the subdomain and scroll to the DMARC record section.

   * If a DMARC record already exists on the parent domain, [!DNL Journey Optimizer B2B Edition] Prime fetches the values automatically. You can keep them or override.
   * If no record exists, choose **[!UICONTROL Manage with Adobe]** and Adobe creates and hosts the DMARC record.

1. Set the policy: `none`, `quarantine`, or `reject`. Start with `none` unless you already have a mature DMARC posture on your parent domain.

1. (Optional) Configure additional DMARC tags (`sp` for subdomain policy, `pct` for percentage, `rua` and `ruf` for report addresses).

1. If using Fully Delegated, click **[!UICONTROL Save]**.

   Adobe applies the record automatically. If using CNAME, copy the DNS record and have your DNS team add it, then confirm it in [!DNL Journey Optimizer B2B Edition] Prime.

1. Allow up to 48 hours for DNS propagation, then verify that the DMARC status indicator on the subdomain page is green/healthy.

>[!TIP]
>
>Begin with `policy=none` to monitor authentication reports, then progress to `quarantine`, and finally to `reject` once your reports show healthy SPF and DKIM alignment. Moving straight to `reject` without monitoring can cause legitimate mail to be rejected.

## IP pools {#ip-pools}

An IP pool is a named group of IP addresses used to send your email. IP pools are critical for sender reputation: each pool has its own reputation with ISPs, so a problem with one pool (for example, a marketing burst that triggers spam complaints) does not contaminate another (for example, transactional confirmations).

### Pool types

| Pool type | Availability | Description |
| --------- | ------------ | ----------- |
| **Shared IP pool** | Available at Alpha | A pool of IP addresses managed by Adobe and shared across many customers. Reputation is maintained by Adobe across the pool. Best for low-to-mid email volume and customers who do not want to manage IP warmup. |
| **Dedicated IP pool** | Roadmap (GA) | One or more IP addresses allocated exclusively to your organization. You own the reputation. Recommended for high-volume senders. Includes IP warmup planning and PTR record management. |

### Review and assign an IP pool {#review-ip-pool}

In this release, IP pools are pre-provisioned for your organization. You assign an IP pool when creating an email channel configuration.

1. Navigate to **[!UICONTROL Administration]** → **[!UICONTROL Channels]** → **[!UICONTROL Email settings]** → **[!UICONTROL IP pools]**.
1. Confirm that an IP pool with status **[!UICONTROL Active]** is available for your organization.
1. Hover over the pool to view the IP addresses and their PTR records (reverse DNS).
1. If your organization has multiple business units or brands, plan how you will use IP pools (for example, marketing-pool versus webinar-pool) before creating channel configurations.

>[!IMPORTANT]
>
>Do not mix marketing and transactional traffic on the same IP pool, even when the shared pool is available. The Email type setting on the channel configuration (Marketing vs. Transactional) governs suppression behavior, but your channel configurations should still use distinct pools where possible.

## Email channel configurations {#email-channel-configurations}

A channel configuration is the central object that ties together your sender identity, subdomain, IP pool, and tracking settings. Email actions in journeys reference a channel configuration to know how to send the message:

* **Channel:** Email.
* **Email type:** Marketing or Transactional. This setting determines whether suppression rules apply (Marketing applies them; Transactional bypasses spam-complaint suppression by default for legitimate transactional messages).
* **Header parameters:** From Name, From Email, Reply-To Name, Reply-To Email, Error Email.
* **Subdomain:** The delegated subdomain used for sending. The From Email must use this subdomain.
* **IP pool:** The IP pool used to deliver the message.
* **URL tracking:** Enable or disable click and open tracking; configure the tracking domain.
* **Tags:** Tags for organization and search.

### Create an email channel configuration {#create-email-channel-configuration}

>[!PREREQUISITES]
>
>* At least one subdomain must be delegated and Active.
>* At least one IP pool must be assigned to your organization.
>* You need the Administrator role.

1. Navigate to **[!UICONTROL Channels]** → **[!UICONTROL General settings]** → **[!UICONTROL Channel configurations]**.
1. Click **[!UICONTROL Create channel configuration]**.
1. Enter a Name (for example, "Contoso B2B Marketing — North America") and an optional Description.
1. Select the **[!UICONTROL Email]** channel.
1. Optionally select tags to categorize the configuration.
1. In the **[!UICONTROL Email type]** section, choose Marketing or Transactional.
1. In the **[!UICONTROL Subdomain]** section, select a previously delegated subdomain.
1. In the **[!UICONTROL IP pool]** section, select an Active IP pool. You can hover over the IPs to view PTR records.
1. Configure the **[!UICONTROL Header parameters]**:
   * From Name (for example, "Contoso Marketing").
   * From Email — must use the selected subdomain (for example, `marketing@mail.contoso.com`).
   * Reply-To Name and Reply-To Email — defaults to From if blank.
   * Error Email — address that receives non-delivery notifications.
1. Enable **[!UICONTROL URL Tracking]** and select the tracking domain.
1. Click **[!UICONTROL Submit]**.
1. Prime runs validation: subdomain status, MX record, SPF/DKIM/DMARC alignment, IP pool readiness, FBL registration. The configuration moves through Draft → Processing → Active.

>[!NOTE]
>
>If validation fails, the configuration moves to the **[!UICONTROL Failed]** status. Open the configuration to view the failure reason — common causes are MX record validation failure, IPs in the pool not matching the configuration, or DMARC misalignment. Resolve and resubmit.

### Edit or delete a channel configuration {#edit-channel-configuration}

You can edit channel configurations after creation, but with one important constraint:

* **Channel cannot be changed.** A configuration is bound to its channel.

When you edit a configuration that is in use:

* **For published journeys:** the change is applied at the next recurrence or the next execution. In-flight executions continue with the previous settings.
* **For transactional or real-time messages:** changes propagate within about five minutes.

To delete a configuration, first remove or update every email action that references it. [!DNL Journey Optimizer B2B Edition] Prime does not delete a configuration that is currently used by an active journey.

### Multiple channel configurations {#multiple-channel-configurations}

Most B2B organizations use multiple channel configurations to separate brands, regions, or send types. Common patterns:

* A separate marketing configuration per business unit (for example, *BU-A Marketing*, *BU-B Marketing*).
* A dedicated transactional configuration with Email Type = Transactional for product or contract notifications.
* Region-specific configurations using region-specific subdomains (for example, `mail.eu.contoso.com`, `mail.us.contoso.com`) to align with regional ISPs and compliance.

>[!TIP]
>
>Name your configurations with a clear, structured convention — for example: *[Brand] – [Region] – [Type]*. This becomes critical once you have a dozen or more configurations.

### Known limitations {#known-limitations}

* **Custom Delegation method** for subdomain delegation is not yet available — use Fully Delegated or CNAME. Custom Delegation is targeted for GA.
* **Dedicated IP pools** are not available at Alpha. The shared IP pool is the only option. Dedicated IPs ship at GA, including IP warmup planning and PTR record management.
* **HTML import via .html or .zip upload** is limited at Alpha. Full HTML import — including code editor + visual canvas dual view, validation, and inline-CSS auto-conversion — ships at Beta.
* **Native image upload and DAM in Prime** (upload, organize, edit) is on the Beta roadmap. Use Marketo Design Studio assets in this release. Re-uploads in Marketo are not reflected in Prime.
* **Test profiles, Simulate Content, and Send Proof** are not available in this release. Litmus rendering and SpamAssassin-based spam reports are on the Beta roadmap.
* **Account-level personalization and custom-object data** are not available in this release. Use profile attributes.
* **Velocity-to-Handlebars automated migration** of existing Marketo templates ships at GA.
* **Comments and collaboration on emails** (inline comments, @mentions, request-review workflow) ship in the Fast Follow-up release.
* **AEM Assets, AEM Content Fragments, and Adobe Express** integrations are on the Fast Follow-up roadmap.

<!--

### Frequently asked questions {#faq}

| Question | Answer |
| -------- | ------ |
| **Can I reuse the subdomain I already use in Marketo Engage?** | No. A subdomain can only be associated with one Adobe product at a time. Create a new subdomain (for example, mail2.contoso.com) for Prime. |
| **Why does my channel configuration show Failed?** | The most common reasons are: MX record validation failed (your subdomain DNS isn't fully configured); DMARC misalignment; or an IP pool that is in Processing and has never been associated with the selected subdomain. Open the configuration to see the specific reason. |
| **What happens if a personalization token has no value at send time?** | If you defined a fallback with the Handlebars `default` helper, the fallback is used. If not, the token resolves to an empty string. Prime warns you when a token has no fallback and the underlying attribute is not guaranteed by the audience definition. |
| **Can I personalize using account-level attributes?** | Not in this release. Personalization in Prime today supports profile attributes only. |
| **What's the maximum email size?** | 100 KB is the recommended best-practice cap for inbox rendering. Prime warns you in the editor if you exceed it. |
| **Can I migrate existing Marketo email templates into Prime?** | A guided self-serve migration tool — including Velocity-to-Handlebars conversion — is delivered at GA. In this release, you can manually rebuild templates or paste raw HTML. |
| **Will my updates to Marketo assets show up in Prime?** | No. Asset availability in Prime is based on a one-time copy from Marketo Design Studio. Re-uploaded or modified Marketo assets are not reflected in Prime today. Native asset upload and management within Prime is on the Beta roadmap. |

## Glossary {#glossary}

| Term | Definition |
| ---- | ---------- |
| **DKIM** | DomainKeys Identified Mail — cryptographic email signature. |
| **DMARC** | Domain-based Message Authentication, Reporting & Conformance. |
| **FBL** | Feedback Loop — a service ISPs offer to receive spam-complaint reports back to senders. |
| **Handlebars** | JavaScript templating language used in Prime for personalization expressions. |
| **IP pool** | Group of IP addresses used to send email. |
| **MX record** | Mail Exchange DNS record — directs incoming mail to the correct mail servers. |
| **NS record** | Name Server DNS record — used to delegate a subdomain. |
| **PTR record** | Pointer record — reverse DNS that maps an IP address back to a hostname. |
| **RBAC** | Role-Based Access Control. |
| **SPF** | Sender Policy Framework — DNS record listing authorized sending IPs. |
| **Subdomain delegation** | Granting Adobe authority over a portion of your domain (a subdomain) for sending email. |

-->
