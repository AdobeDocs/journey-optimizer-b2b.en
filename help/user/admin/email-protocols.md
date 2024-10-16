---
title: Configure protocols for email delivery and tracking
description: Learn how to configure protocols in Marketo Engage for use by Journey Optimizer B2B Edition for email channel features.
feature: Setup
---
# Configure protocols for email delivery

Adobe Journey Optimizer B2B Edition leverages the email channel functions and event tracking in Market Engage. To ensure that email delivery works as expected for organizations that use restrictive firewall or proxy server settings, a systems administrator must add certain domains and IP address ranges to the allowlist. 

Make sure that following domains (including the asterisk) are added to the allowlist to enable all Marketo Engage resources and websockets:

* `*.experience.adobe.com`
* `*.adobe.net`
* `*.marketo.com`
* `*.marketodesigner.com`
* `*.mktoweb.com`

To learn more, see [Ensure Email Deliverability](https://experienceleague.adobe.com/en/docs/marketo/using/getting-started/initial-setup/setup-steps#ensure-email-deliverability) in the Marketo Engage documentation.


## Create DNS records for landing pages and email

**Tracking Link CNAMEs**

Your marketing team should have sent you two requests for new CNAME records. The first is for landing page URLs, so that the landing pages appear in URLs that reflect your domain and not Marketo Engage (the actual host). The second is for the tracking links that are included in the emails they send from Marketo Engage.

`1` **Add CNAME for Landing Pages**

Add the landing page CNAME they sent you to your DNS record, so that `[YourLandingPageCNAME]` points to the unique Account String that is assigned to your Marketo Engage Landing Pages. Log in to your domain registrar's site and enter the landing page CNAME and Account String. Typically, this involves three fields:

* Alias: Enter `[YourLandingPageCNAME]` (provided by marketing)
* Type: CNAME  
* Point to: Enter `[MunchkinID].mktoweb.com` (provided by marketing)

`2` **Add CNAME for Email Tracking Links**

Add the email CNAME marketing sent you, so that `[YourEmailCNAME]` points to [MktoTrackingLink], the default tracking link that Marketo Engage assigned, in the format:  
`[YourEmailCNAME].[YourDomain].com` IN CNAME `[MktoTrackingLink]`

For example:  

`pages.abc.com IN CNAME mkto-a0244.com`

>[!NOTE]
>
>`[MktoTrackingLink]` must be the Default Branding Domain.

`3` **Notify Your Marketing Team**

Notify your marketing team when you've completed this process.

`4` **Contact [Adobe Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} to start the process of provisioning an SSL Certificate.**

This process can take up to 3 business days to complete.

## Allowlist IPs for test emails

When your Marketing group uses Marketo Engage to send test emails (a best practice before sending out email blasts), the test emails are sometimes blocked by anti-spam systems that rely on sender IP addresses to verify that the email is valid. To ensure that those test emails arrive, add these IP addresses to your corporate allowlist:

* 94.236.119.0/26
* 103.237.104.0/22
* 130.248.172.0/24
* 130.248.173.0/24
* 130.248.244.88/29
* 185.28.196.0/22
* 192.28.144.0/20
* 192.28.160.0/19
* 199.15.212.0/22

Some anti-spam systems use the email Return-Path field instead of the IP address for allowisting. In those cases, the best approach is to allowlist '&#42;.mktomail.com', as Marketo Engage uses several mailbox subdomains. Other anti-spam systems allowlist based on the From address. In these situations, be sure to include all the sending ('From') domains that your Marketing group uses to communicate with people/leads.

>[!NOTE]
>
>Google Apps employs a unique technology and requires allowlisting IP ranges. See [Allowlisting with Google Apps](https://nation.marketo.com/t5/knowledgebase/allowlisting-with-google-apps/ta-p/248203).

## Step 3: Set up SPF and DKIM {#step-set-up-spf-and-dkim}

Your marketing team should have also sent you DKIM (Domain Keys Identified Mail) information to be added to your DNS resource record (also listed below). Follow the steps to successfully configure DKIM and SPF (Sender Policy Framework), then notify your marketing team that this has been updated.

1. To set up SPF, add the following line to our DNS entries:

   `[CompanyDomain]` IN TXT v=spf1 mx ip4:`[CorpIP]`  
   include: mktomail.com ~all
  
   If we already have an existing SPF record in our DNS entry, simply add the following to it:  
   include: mktomail.com

   Replace CompanyDomain with the main domain of your website (ex: "`(company.com/)`") and CorpIP with the IP address of your corporate email server (ex. "255.255.255.255"). If you are going to be sending email from multiple domains through Marketo Engage, you should have your IT staff add this line for each domain (on one line).

1. For DKIM, create DNS Resource Records for each domain we'd like to set up. Below are the Host Records and TXT Values for each domain we'll be signing for:

   `[DKIMDomain1]`: Host Record is `[HostRecord1]` and the TXT Value is `[TXTValue1]`.

   `[DKIMDomain2]`: Host Record is `[HostRecord2]` and the TXT Value is `[TXTValue2]`.

   Copy the HostRecord and TXTValue for each DKIMDomain you've set up after following the [instructions here](/help/marketo/product-docs/email-marketing/deliverability/set-up-a-custom-dkim-signature.md){target="_blank"}. Don't forget to verify each domain in Admin > Email > DKIM after your IT staff has completed this step.

## Set up DMARC {#set-up-dmarc}

DMARC (Domain-based Message Authentication, Reporting, and Conformance) is an authentication protocol that is used to help organizations protect their domain from unauthorized use. It extends the existing authentication protocols, such as SPF and DKIM, to inform recipient servers about the actions to be taken if a failure in authentication occurs on their domain. DMARC is optional, but is strongly recommended because to helps protect your organization's brand and reputation. Major providers, such as Google and Yahoo, started requiring the use of DMARC for bulk senders beginning February 2024.

For DMARC to function, you must have at least one of the following DNS TXT records:

* A Valid SPF
* A Valid DKIM Record for your FROM: Domain (recommended for Marketo Engage and Journey Optimizer B2B Edition)

You must also have a DMARC-specific DNS TXT record for your FROM: Domain. Optionally, you can define an email address of your choosing that indicates where DMARC reports should go within your organization for report monitoring.

>[!TIP]
>
>It is a best practice to implement DMARC as a _slow rollout_. Escalate your DMARC policy from `p=none`, to `p=quarantine`, and then to `p=reject` as you gain understanding of the potential impact, and set your DMARC policy to relaxed alignment on SPF and DKIM.

### Example DMARC workflow

If you're configured to receive DMARC reports, you should do the following:

* Analyze the feedback and reports you receive and use (p=none), which tells the receiver to perform no actions against messages that fail authentication, but still send email reports to the sender.

* Review and fix issues with SPF/DKIM if legitimate messages are failing authentication.

* Determine if SPF or DKIM are aligned and passing authentication for all legitimate email.

* Review reports to ensure the results are what you expect based on your SPF/DKIM policies.

1. Adjust the policy to `p=quarantine`, which tells the receiving email server to quarantine email that fails authentication (typically placing those messages in the spam folder).

1. Review reports to ensure that the results are what you expect.

1. If you're satisfied with the behavior of messages at the `p=quarantine` level, you can adjust policy to (`p=reject`). 

   The reject policy tells the receiver to completely deny (bounce) any email for the domain that fails authentication. With this policy enabled, only email that's verified as 100% authenticated by your domain will even have a chance at inbox placement.

>[!CAUTION]
>
>Use this policy with caution and determine if it's appropriate for your organization.

### DMARC reporting

DMARC offers the ability to receive reports regarding emails that fail SPF/DKIM. There are two different reports generated by ISP servicers as part of the authentication process. Senders can receive these reports through the RUA/RUF tags in their DMARC policy.

* **Aggregate Reports (RUA)**: Does not contain any PII (Personally Identifiable Information) that could be GDPR (General Data Protection Regulation) sensitive.

* **Forensic Reports (RUF)** - Contain email addresses that are GDPR sensitive. Before you implement this report, make sure you know the organizational policy for handling information that needs to be GDPR compliant.

The main use of these reports is to receive an overview of emails that are attempted spoofing. These are highly technical reports and are best digested through a third-party tool.

### Example DMARC records

* Bare Minimum Record: `v=DMARC1; p=none`

* Record directing to an email address to receive reports: `v=DMARC1; p=none;  rua=mailto:emaill@domain.com;     ruf=mailto:email@domain.com`

### DMARC tags

DMARC records have multiple components called DMARC tags. Each tag has a value that specifies a certain aspect of DMARC.

| Tag name  | Use                    | Function  | Example  | Default value                     |
|-----------|------------------------|-----------|----------|-----------------------------------|
| `v`       | Required               | Specifies the version. There is only one version, so it has a fixed value of `v=DMARC1`  | V=DMARC1 DMARC1  | DMARC1                            |
| `p`       | Required               | Specifies the DMARC policy, which directs the receiver to report, quarantine, or reject email that fails authentication checks. | `p=none`, `p=quarantine`, or `p=reject`  | -  |
| `fo`      | Optional               | Allows the domain owner to specify reporting options. | `0`: Generate report if both SPF and DKIM fail  <br> `1` - Generate report if either SPF or DKIM fail <br> `d` - Generate report if DKIM fails <br> `s` - Generate report if SPF fails | `1` (recommended for DMARC reports) |
| `pct`     | Optional               | Specifies the percentage of messages subjected to filtering.  | `pct=20`    | `100`   |
| `rua`     | Optional (recommended) | Designates where aggregate reports are delivered. | `rua=mailto:aggrep@example.com` | - |
| `ruf`     | Optional (recommended) | Designates where forensic reports are delivered.  | `ruf=mailto:authfail@example.com` | - |
| `sp`      | Optional               | Specifies the DMARC policy for subdomains of the parent domain. | `sp=reject` | - |
| `adkim`   | Optional               | Specifies either a strict (`s`) or relaxed (`r`) alignemnt. Relaxed alignment means that the domain is used in the DKIM signature and can be a subdomain of the `From:` address. Strict alignment means that the domain is used in the DKIM signature and must be an exact match of the domain used in the `From:` address. | `adkim=r` | `r` |
| `aspf`    | Optional               | Can either be strict (`s`) or relaxed (`r`). Relaxed mode means that the ReturnPath Domain can be a subdomain of the `From:` address. Strict mode means that the Return-Path domain must be an exact match with the `From:` address. | `aspf=r` | `r` |

For detailed information about DMARC and all of its options, refer to [https://dmarc.org/](https://dmarc.org/){target="_blank"}.

### DMARC implementation for Marketo Engage

There are two types of alignment for DMARC:

* **DKIM** (DomainKeys Identified Mail) alignment: The domain specified in an email's From: header matches with the DKIM-Signature. The DKIM signature contains a `d=` value where the domain is specified for matching with the From: header domain. 

   DKIM alignment is different from SPF alignment as it validates if the sender is authorized to send mails from the domain and verifies that no content has been changed during email transit.

   To set up DKIM-aligned DMARC: 

   * Set up DKIM for the FROM: Domain of your message. Use the instructions [in the Marketo Engage documentation](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/email-marketing/deliverability/set-up-a-custom-dkim-signature){target="_blank"}.

   * Configure DMARC for the FROM:/DKIM Domain that was configured earlier.

   >[!NOTE]
   >
   >It is recommended to use DKIM alignment for Marketo Engage.

* **SPF** (Sender Policy Framework ) alignment: The domain in the From: header must match the domain in the Return-Path: header. If both DNS domains are the same, the SPF matches (aligns) and gives a pass result.

   To set up SPF-aligned DMARC: 

   * Set up Branded Return-Path Domain.

      * Configure the appropriate SPF record.
      * Change the MX record to point back to the default MX for the datacenter your mail is sent from

   * Configure DMARC for the Branded Return-Path Domain.


* If you send mail from Marketo Engage through a dedicated IP and have not implemented a branded return-path (or are not sure if you have), open a ticket with [Adobe Support](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

* If you're sending mail from Marketo Engage through a shared pool of IPs, you can see if you qualify for Trusted IPs by [applying here](http://na-sjg.marketo.com/lp/marketoprivacydemo/Trusted-IP-Sending-Range-Program.html){target="_blank"}. Branded return-path is offered for free to those sending from Marketo Engage Trusted IPs. If approved for this program, reach out to Adobe Support to set up branded return-path.

   * Trusted IPs: A shared pool of IPs reserved for lower volume users sending <75K/month who do not qualify for a dedicated IP. These users must also meet best practice requirements as well.

* If you're sending mail from Marketo Engage through shared IPs and you do not qualify for Trusted IPs and send more than 100,000 messages per month, you'll need to contact the Adobe Account Team (your account manager) to purchase a dedicated IP.

* Strict SPF alignment is not supported or recommended within Marketo Engage.

#### MX Records for your domain

An MX record allows you to receive mail to the domain that you're sending email from to process replies and auto-responders. If you're sending from your corporate domain, it is probably already configured. If not, you can usually set it up to map to your corporate domain MX record.

#### Outbound IP Addresses

An outbound connection is one made by Marketo Engage to a server on the internet on your behalf. Some partners/vendors you work with, or your own IT organization, may use allowlists to restrict access to servers. If so, you must provide them with Marketo Engage outbound IP address blocks to add to their allowlists.

##### Webhooks

Marketo Engage [Webhooks](/help/marketo/product-docs/administration/additional-integrations/create-a-webhook.md){target="_blank"} are an outbound integration mechanism. When a [Call Webhook](/help/marketo/product-docs/core-marketo-concepts/smart-campaigns/flow-actions/call-webhook.md){target="_blank"} flow action is executed as part of a smart campaign, an HTTP request is made to an external web service. If the web service publisher uses an allowlist on the firewall of the network where the external web service is located, then the publisher must add the IP address blocks listed below to their allowlist.

##### CRM Sync

Marketo Engage [Salesforce CRM Sync](/help/marketo/product-docs/crm-sync/salesforce-sync/sfdc-sync-details/add-an-existing-salesforce-field-to-the-marketo-sync.md){target="_blank"} and [Microsoft Dynamics Sync](/help/marketo/product-docs/crm-sync/microsoft-dynamics-sync/understanding-the-microsoft-dynamics-sync.md){target="_blank"} are integration mechanisms that make outbound HTTP requests to APIs published by your CRM vendor. You must ensure that your IT organization does not block any of the IP address blocks below from accessing your CRM vendor APIs.

##### Outbound IP address blocks

The following lists cover all Marketo Engage servers that make outbound calls. Refer to these lists for configuring an IP allowlist, server, firewall, access control list, security group, or third-party service to receive outgoing connections from Marketo Engage.

**_IP Block (CIDR Notation)_**:

* 94.236.119.0/26
* 103.237.104.0/22
* 130.248.172.0/24
* 130.248.173.0/24
* 130.248.244.88/29
* 185.28.196.0/22
* 192.28.144.0/20
* 192.28.160.0/19
* 199.15.212.0/22

**_Individual IP address_**:

* 13.237.155.207
* 13.55.192.247
* 18.200.201.81
* 34.247.24.245
* 35.165.244.220
* 44.235.171.179
* 52.20.211.99
* 52.64.109.86
* 54.160.246.246
* 54.212.167.17
* 54.220.138.65
* 54.237.141.197
* 130.248.168.16
* 130.248.168.17