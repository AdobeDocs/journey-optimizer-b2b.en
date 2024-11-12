---
title: Protocols for tracking and email delivery
description: Learn how to configure protocols in Marketo Engage for use by Journey Optimizer B2B Edition for tracking and email channel features.
feature: Setup
audience: administrator
---
# Protocols for tracking and email delivery

Adobe Journey Optimizer B2B Edition leverages the email channel functions and event tracking in Market Engage. To ensure that email delivery works as expected for organizations that use restrictive firewall or proxy server settings, a systems administrator must add certain domains and IP address ranges to the allowlist. 

>[!NOTE]
>
>If your organization is already using the connected Marketo Engage instance to run their marketing operations, these protocols and configurations should already be in place.

Make sure that the following domains (including the asterisk) are added to the allowlist to enable all Marketo Engage resources and web sockets:

* `*.experience.adobe.com`
* `*.adobe.net`
* `*.marketo.com`
* `*.marketodesigner.com`
* `*.mktoweb.com`

Work through the following steps to ensure tracking and email delivery:

1. [Create DNS records for landing pages and email](#create-dns-records-for-landing-pages-and-email)
1. [Set up SPF and DKIM](#set-up-spf-and-dkim)
1. [Set up DMARC](#set-up-dmarc)
1. [Set up MX records for your domain](#set-up-mx-records-for-your-domain)
1. [Add Outbound IP addresses to allowlists](#outbound-ip-addresses)

## Create DNS records for landing pages and email

Connecting a CNAME record allows you to host web versions of emails, landing pages, and blogs with consistent branding that improves your traffic and conversions. It is highly recommended that you add the CNAMEs to your root domain host for Marketo Engage to host your marketing-focused web assets. 

As an administrator, you should work with your Marketing team to plan and implement two CNAME records. The first one is for landing page URLs, so that the landing pages appear in URLs that reflect your domain and not Adobe Marketo Engage (the actual host). The second one is for the tracking links that are included in the emails sent through Marketo Engage.

### Add the CNAME for landing pages

Add the landing page CNAME to your DNS record, so that `[YourLandingPageCNAME]` points to the unique account string that is assigned to your landing pages. Log in to your domain registrar's site and enter the landing page CNAME and account string. This entry usually involves three fields:

* Alias: Enter `[YourLandingPageCNAME]`
* Type: CNAME
* Point to: Enter `[MunchkinID].mktoweb.com`

### Add the CNAME for email tracking links

Add the email CNAME so that `[YourEmailCNAME]` points to `[MktoTrackingLink]`, which is the default tracking link that Marketo Engage assigned, in the format:

`[YourEmailCNAME].[YourDomain].com` IN CNAME `[MktoTrackingLink]`

For example:  

`pages.abc.com IN CNAME mkto-a0244.com`

>[!NOTE]
>
>The `[MktoTrackingLink]` value must be the Default Branding Domain.

### Provision the SSL certificate

Contact [Adobe Support](https://experienceleague.adobe.com/home?lang=en&support-tab=home#support){target="_blank"} to start the process of provisioning an SSL Certificate.

This process can take up to three business days to complete. 

## Set up SPF and DKIM

Your marketing team should provide the DKIM (Domain Keys Identified Mail) information to be added to your DNS resource record. Follow these steps to configure DKIM and SPF (Sender Policy Framework), and then notify your Marketing team when it is updated.

1. To set up SPF, add the following line to the DNS entries:

   ```
   [CompanyDomain] IN TXT v=spf1 mx ip4:[CorpIP]  
   include: mktomail.com ~all
   ```
  
   If you already have an existing SPF record in the DNS entry, simply add the following to it:
   
   ```
   include: mktomail.com
   ```

   Replace `CompanyDomain` with the main domain of your website (such as `company.com/`) and `CorpIP` with the IP address of your corporate email server (such as `255.255.255.255`). If you plan to send email from multiple domains through Marketo Engage, add this line for each domain (on one line).

1. For DKIM, create DNS resource records for each domain. 

   Add the host records and TXT Values for each domain:

   `[DKIMDomain1]`: Host Record is `[HostRecord1]` and the TXT Value is `[TXTValue1]`.

   `[DKIMDomain2]`: Host Record is `[HostRecord2]` and the TXT Value is `[TXTValue2]`.

   Copy the `HostRecord` and `TXTValue` for each DKIM domain after following the [instructions](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/email-marketing/deliverability/set-up-a-custom-dkim-signature){target="_blank"} in the Marketo Engage documentation. You can verify the domains in Journey Optimizer B2B Edition (see [SPF/DKIM](../admin/configure-channels-emails.md#spfdkim)).

## Set up DMARC

DMARC (Domain-based Message Authentication, Reporting, and Conformance) is an authentication protocol that is used to help organizations protect their domain from unauthorized use. It extends the existing authentication protocols, such as SPF and DKIM, to inform recipient servers about the actions to take if an authentication failure occurs on their domain. DMARC is optional, but is strongly recommended because to helps protect your brand and reputation. Major providers, such as Google and Yahoo, started requiring the use of DMARC for bulk senders beginning February 2024.

For DMARC to function, you must have at least one of the following DNS TXT records:

* A Valid SPF
* A Valid DKIM Record for your FROM: domain (recommended for Marketo Engage and Journey Optimizer B2B Edition)

You must also have a DMARC-specific DNS TXT record for your `FROM:` domain. Optionally, you can define an email address that specifies where DMARC reports should go within your organization for report monitoring.

### Example DMARC workflow

>[!TIP]
>
>It is a best practice to implement DMARC as a _slow rollout_. Escalate your DMARC policy from `p=none`, to `p=quarantine`, and then to `p=reject` as you gain understanding of the potential impact, and set your DMARC policy to relaxed alignment on SPF and DKIM.

If you receive DMARC reports, you should do the following:

1. Use `p=none` and analyze the feedback and reports you receive. The reports tell the receiver to perform no actions against messages that fail authentication, and send email reports to the sender.

   * If legitimate messages are failing authentication, review and fix the issues with SPF/DKIM.

   * Determine if SPF or DKIM are aligned and passing authentication for all legitimate email.

   * Review the reports to ensure that the results are what is expected based on your SPF/DKIM policies.

1. Adjust the policy to `p=quarantine`, which tells the receiving email server to quarantine emails that fail authentication (typically placing those messages in the spam folder).

   Review reports to ensure that the results are what you expect.

1. If you are satisfied with the behavior of messages at the `p=quarantine` level, you can adjust policy to (`p=reject`). 

   The reject policy tells the receiver to deny (bounce) any email for the domain that fails authentication. With this policy enabled, only email that is verified as 100% authenticated by your domain has a chance at inbox placement.

   >[!CAUTION]
   >
   >Use this policy with caution and determine if it's appropriate for your organization.

### DMARC reporting

DMARC offers the ability to receive reports regarding emails that fail SPF/DKIM. There are two different reports generated by ISP servicers as part of the authentication process. Senders can receive these reports through the RUA/RUF tags in their DMARC policy.

* **Aggregate Reports (RUA)**: Does not contain any PII (Personally Identifiable Information) that could be GDPR (General Data Protection Regulation) sensitive.

* **Forensic Reports (RUF)** - Contain email addresses that are GDPR sensitive. Before you implement this report, verify your organizational policy for handling information that needs to be GDPR compliant.

The main use of these reports is to receive an overview of emails that are attempted spoofing. They are highly technical reports and are best digested through a third-party tool.

### Example DMARC records

* Bare minimum record: `v=DMARC1; p=none`

* Record that directs to an email address to receive reports: `v=DMARC1; p=none;  rua=mailto:emaill@domain.com;  ruf=mailto:email@domain.com`

### DMARC tags

DMARC records have multiple components called _DMARC tags_. Each tag has a value that specifies a certain aspect of DMARC.

| Tag name  | Use                    | Function  | Example  | Default value                     |
|-----------|------------------------|-----------|----------|-----------------------------------|
| `v`       | Required               | Specifies the version. There is only one version, so it has a fixed value of `v=DMARC1`  | V=DMARC1 DMARC1  | DMARC1                            |
| `p`       | Required               | Specifies the DMARC policy, which directs the receiver to report, quarantine, or reject email that fails authentication checks. | `p=none`, `p=quarantine`, or `p=reject`  | -  |
| `fo`      | Optional               | Allows the domain owner to specify reporting options. | `0`: Generate report if both SPF and DKIM fail  <br> `1` - Generate report if either SPF or DKIM fails <br> `d` - Generate report if DKIM fails <br> `s` - Generate report if SPF fails | `1` (recommended for DMARC reports) |
| `pct`     | Optional               | Specifies the percentage of messages subjected to filtering.  | `pct=20`    | `100`   |
| `rua`     | Optional (recommended) | Designates where aggregate reports are delivered. | `rua=mailto:aggrep@example.com` | - |
| `ruf`     | Optional (recommended) | Designates where forensic reports are delivered.  | `ruf=mailto:authfail@example.com` | - |
| `sp`      | Optional               | Specifies the DMARC policy for subdomains of the parent domain. | `sp=reject` | - |
| `adkim`   | Optional               | Specifies either a strict (`s`) or relaxed (`r`) alignment. Relaxed alignment means that the domain is used in the DKIM signature and can be a subdomain of the `From:` address. Strict alignment means that the domain is used in the DKIM signature and must be an exact match of the domain used in the `From:` address. | `adkim=r` | `r` |
| `aspf`    | Optional               | Can either be strict (`s`) or relaxed (`r`). Relaxed mode means that the Return-Path domain can be a subdomain of the `From:` address. Strict mode means that the Return-Path domain must be an exact match with the `From:` address. | `aspf=r` | `r` |

For detailed information about DMARC and all of its options, refer to [https://dmarc.org/](https://dmarc.org/){target="_blank"}.

### DMARC implementation for Marketo Engage

There are two types of alignment for DMARC:

* **DKIM** (Domain Keys Identified Mail) alignment: The domain specified in an email's `From:` header matches with the DKIM-Signature. The DKIM signature contains a `d=` value where the domain is specified for matching with the `From:` header domain. 

   DKIM alignment validates if the sender is authorized to send mails from the domain and verifies that no content has been changed during email transit. To implement DKIM-aligned DMARC: 

   * Set up DKIM for the MAIL FROM domain of your message. Use the [instructions](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/email-marketing/deliverability/set-up-a-custom-dkim-signature){target="_blank"} in the Marketo Engage documentation.

   * Configure DMARC for the DKIM MAIL FROM domain.

   >[!NOTE]
   >
   >DKIM alignment is recommended to use for Marketo Engage.

* **SPF** (Sender Policy Framework) alignment: The domain in the `From:` header must match the domain in the Return-Path: header. If both DNS domains are the same, the SPF matches (aligns) and gives a pass result. To implement SPF-aligned DMARC: 

   * Set up the branded Return-Path domain.

      * Configure the appropriate SPF record.
      * Change the MX record to point back to the default MX for the datacenter your mail is sent from

   * Configure DMARC for the branded Return-Path domain.

   >[!NOTE]
   >
   >Strict SPF alignment is not supported or recommended for Marketo Engage.

### Dedicated IPs and shared pool

If you send mail through Marketo Engage over a dedicated IP and have not implemented a branded return-path (or are not sure if you have), open a ticket with [Adobe Support](https://experienceleague.adobe.com/home?lang=en&support-tab=home#support){target="_blank"}.

If you are sending mail through Marketo Engage using a shared pool of IPs, you can check if you qualify for Trusted IPs by [applying for the Trusted IP sending range program](https://na-sjg.marketo.com/lp/marketoprivacydemo/Trusted-IP-Sending-Range-Program.html){target="_blank"}. The branded return-path is included when sending from Marketo Engage Trusted IPs. If approved for this program, reach out to Adobe Support to set up the branded return-path.

   Trusted IPs are a shared pool of IPs that are reserved for lower volume users sending less than 75k per month and do not qualify for a dedicated IP. These users must also meet best practice requirements.

   If you send more than 100,000 messages per month and want to send email through Marketo Engage using shared IPs, contact the Adobe Account Team (your account manager) to purchase a dedicated IP.

## Set up MX records for your domain

An MX record allows you to receive mail to the domain that you're sending email from to process replies and auto-responders. If you're sending from your corporate domain, it is probably already configured. If not, you can usually set it up to map to your corporate domain MX record.

## Outbound IP addresses

An outbound connection is one made by Marketo Engage to a server on the Internet on your behalf. Your IT organization and some partners/vendors may use allowlists to restrict access to servers. If so, you must provide them with Marketo Engage outbound IP address blocks to add to their allowlists.

### Webhooks

Marketo Engage webhooks are an outbound integration mechanism. When a Smart Campaign executes a _Call Webhook_ flow action, it makes an HTTP request to an external web service. If the web service publisher uses an allowlist on the firewall of the network where the external web service is located, the publisher must add the IP address blocks listed below to their allowlist. For more information, see [Create a webhook](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/additional-integrations/create-a-webhook){target="_blank"} and [Call Webhook](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/core-marketo-concepts/smart-campaigns/flow-actions/call-webhook){target="_blank"} in the Marketo Engage documentation.

### CRM sync

Marketo Engage [Salesforce CRM Sync](/help/marketo/product-docs/crm-sync/salesforce-sync/sfdc-sync-details/add-an-existing-salesforce-field-to-the-marketo-sync.md){target="_blank"} and [Microsoft Dynamics Sync](/help/marketo/product-docs/crm-sync/microsoft-dynamics-sync/understanding-the-microsoft-dynamics-sync.md){target="_blank"} are integration mechanisms that make outbound HTTP requests to APIs published by your CRM vendor. Ensure that your IT organization does not block any of the IP address blocks below from accessing your CRM vendor APIs. For more information, see [Add an Existing Salesforce Field to the Marketo Sync](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/crm-sync/salesforce-sync/sfdc-sync-details/add-an-existing-salesforce-field-to-the-marketo-sync){target="_blank"} and [Understanding the Microsoft Dynamics Sync](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/crm-sync/microsoft-dynamics/understanding-the-microsoft-dynamics-sync){target="_blank"} in the Marketo Engage documentation.

## Outbound IP address blocks

The following lists cover all Marketo Engage servers that make outbound calls. Refer to these lists for configuring an IP allowlist, server, firewall, access control list, security group, or third-party service to receive outgoing connections from Marketo Engage.

| IP Block (CIDR Notation) | Individual IP address |
| ------------------------ | --------------------- |
| <ul><li>`94.236.119.0/26`</li><li>`103.237.104.0/22`</li><li>`130.248.172.0/24`</li><li>`130.248.173.0/24`</li><li>`130.248.244.88/29`</li><li>`185.28.196.0/22`</li><li>`192.28.144.0/20`</li><li>`192.28.160.0/19`</li><li>`199.15.212.0/22`</li></ul> | <ul><li>`13.237.155.207`</li><li>`13.55.192.247`</li><li>`18.200.201.81`</li><li>`34.247.24.245`</li><li>`35.165.244.220`</li><li>`44.235.171.179`</li><li>`52.20.211.99`</li><li>`52.64.109.86`</li><li>`54.160.246.246`</li><li>`54.212.167.17`</li><li>`54.220.138.65`</li><li>`54.237.141.197`</li><li>`130.248.168.16`</li><li>`130.248.168.17`</li></ul> |
