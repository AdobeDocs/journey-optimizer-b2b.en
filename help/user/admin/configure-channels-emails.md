---
title: Email Channel Configurations
description: Configure email delivery settings, communication limits, and authentication protocols to optimize deliverability in Journey Optimizer B2B Edition.
feature: Setup, Channels
role: Admin
exl-id: fb16b5e5-f1a5-4e59-b8c6-56985f03225a
---
# Email channel configurations

Adobe Journey Optimizer B2B Edition leverages the channel functions and event tracking in Marketo Engage. Administrators should ensure that the delivery and tracking configurations are in place to enable channel delivery for Marketers. For information about the protocols needed for email delivery and tracking through Marketo Engage, see [Protocols for tracking and email delivery](../start/email-protocols.md).

## Delivery settings

The default email settings are used when Marketers create an email in an account journey. To review the email delivery settings, go to **[!UICONTROL Administration]** > **[!UICONTROL Channels]**. Under _[!UICONTROL Email]_ in the navigation panel, select **[!UICONTROL Delivery Settings]**.

![Access the email delivery settings](./assets/config-email-delivery-email-header.png){width="800" zoomable="yes"}

The settings are read-only in Journey Optimizer B2B Edition. Click **[!UICONTROL Edit settings]** at the top right to access the configuration options in the connected Marketo Engage instance.

>[!NOTE]
>
>To access and edit these settings in Adobe Marketo Engage, you must have Product Administrator permissions.

Select each of the following tabs to review the current settings.

### [!UICONTROL Email header parameters] {#email-header}

The email header parameters define the default values for the following:

* **[!UICONTROL From Email]** - The email address listed in the _From_ field in the email header.

* **[!UICONTROL From Label]** - The displayed name for the email sender address.

* **[!UICONTROL Unsubscribe HTML]** - The HTML (for supported email clients) that is displayed in non-operational emails to explain unsubscribe actions to the recipient. This text and links are appended to the bottom.

* **[!UICONTROL Unsubscribe Text]** - The plain text that is displayed in non-operational emails to explain unsubscribe actions to the recipient. This text and links are appended to the bottom.

* **[!UICONTROL View as web page HTML]** - The HTML (for supported email clients) used for _View as Web Page_, which provides a link to show an email in a browser.

* **[!UICONTROL View as web page text]** - The plain text used for _View as Web Page_, which provides a link to show an email in a browser.

### [!UICONTROL Branding domains] {#branding-domains}

To review the branding domains, click the **[!UICONTROL Branding domains]** tab.

![Access the branding domains settings](./assets/config-email-delivery-branding-domains.png){width="700" zoomable="yes"}

This setting defines your primary domain for one or more workspaces in the connected Marketo Engage instance. New emails use this domain as the default, but marketers can [override it on a per-email basis](../content/add-email.md#define-the-email-settings). For more information about defining the default branding domain, refer to the [Marketo Engage documentation](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/add-multiple-branding-domains/edit-your-default-branding-domain){target="_blank"}.

>[!NOTE]
>
>If you are marketing multiple brands and want each to have its own branded tracking links, you can add an additional branding domain. For more information about adding multiple branding domains, refer to the [Marketo Engage documentation](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/add-multiple-branding-domains/add-an-additional-branding-domain){target="_blank"}.

### [!UICONTROL Custom header options] {#custom-header-options}

To review the custom header options, click the **[!UICONTROL Custom header options]** tab.

![Access the custom header options](./assets/config-email-delivery-custom-header.png){width="700" zoomable="yes"}

When _[!UICONTROL Strict Transport Security]_ is enabled, it guarantees that tracking links are served over HTTPS (only for subscriptions with tracking links secured by SSL).

## Communication limits

Communication limits control the amount of email your organization sends. It is a best practice to set limits so that you don't overwhelm recipients with too many emails from your organization.

To review the current settings, go to **[!UICONTROL Administration]** > **[!UICONTROL Channels]**. Under _[!UICONTROL Email]_ in the navigation panel, select **[!UICONTROL Communication limits]**.

![Access the communication limits settings](./assets/config-email-communication-limits.png){width="700" zoomable="yes"}

Click **[!UICONTROL Edit settings]** at the top right to access the configuration options in the connected Marketo Engage instance. 

>[!NOTE]
>
>To access and edit these settings in Adobe Marketo Engage, you must have Product Administrator permissions.

For more information about configuring the communication limits, refer to the [Marketo Engage documentation](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/enable-communication-limits){target="_blank"}.

## SPF/DKIM

Improve your email delivery rates by incorporating SPF (Sender Policy Framework) and DKIM (Domain Keys Identified Mail) into your DNS settings. These technologies assure your recipients that your emails are not spam. To help prevent recipients' spam filters from rejecting emails, ensure that SPF and DKIM are set up for your domains. 

To review the current settings, go to **[!UICONTROL Administration]** > **[!UICONTROL Channels]**. Under _[!UICONTROL Email]_ in the navigation panel, select **[!UICONTROL SPF/DKIM]**.

![Access the SPF/DKIM configuration](./assets/config-email-spf-dkim.png){width="700" zoomable="yes"}

The settings are read-only in Journey Optimizer B2B Edition. Click **[!UICONTROL Edit settings]** at the top right to access the configuration options in the connected Marketo Engage instance. 

>[!NOTE]
>
>To access and edit these settings in Adobe Marketo Engage, you must have Product Administrator permissions. 

### SPF setup

The network administrator should add the following line to your DNS entries:

`[domain] IN TXT v=spf1 mx ip4:[corpIP] include:mktomail.com ~all`

In this entry, replace `[domain]` with the primary domain of your website (such as `company.com`) and `[corpIP]` with the IP address of your corporate email server (such as `255.255.255.255`). If you send emails from multiple domains through Marketo Engage, add this entry for each domain on a single line.

If you already have an SPF record in your DNS entry, add the following to it:

`include:mktomail.com`

### DKIM setup

DKIM is an authentication protocol that is used by email receivers to validate the sender of the email message. It often improves the deliverability of emails to the inbox because a receiver can be confident that the message is not a forgery. 

When you have the public key in your DNS record and the sending domain activated in the connected Marketo Engage instance, custom DKIM signing is used for your outgoing messages. The custom DKIM signing includes an encrypted digital signature with each email that is sent. The receivers are then able to decrypt the digital signature by looking up the _public key_ in your sending domain's DNS. If the key in the email corresponds with the key in the DNS record, the receiving mail server is more likely to accept the email sent through Marketo Engage.

For more information about configuring a custom DKIM signature for email delivery, refer to the [Marketo Engage documentation](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/email-marketing/deliverability/set-up-a-custom-dkim-signature){target="_blank"}.

## Bot activity

Email bot activity can erroneously inflate your email open and click data. 

Marketo Engage uses two methods for confirming bot activity:

* **Match with Interactive Advertising Bureau (IAB) list** - Activities that match anything on the IAB UA/IP (User Agent/IP address) list are marked as bots.

* **Match with Proximity Pattern** - When two or more activities happen at the same time (within a second), they are identified as bots. This method considers the following attributes for comparison:

   * Lead ID (should be the same)
   * Email asset (should be the same)
   * Link click or email open
   * Time difference (should be less than one second)

For email link click and email open activities, new attributes are populated with the following values:

* Activities that are identified as bots have _Bot Activity_ as `True` and _Bot Activity Pattern_ as the identified pattern/method.
* Activities that are identified as not being bots have _Bot Activity_ as `False` and _Bot Activity Pattern_ as `N/A`.
* Activities that happen before the attributes were introduced have _Bot Activity_ as empty (null) and _Bot Activity Pattern_ as empty (null)

To review the current settings, go to **[!UICONTROL Administration]** > **[!UICONTROL Channels]**. Under _[!UICONTROL Email]_ in the navigation panel, select **[!UICONTROL Bot activity]**. 

![Access the bot activity configuration for email delivery](./assets/config-email-bot-activity.png){width="700" zoomable="yes"}

The settings are read-only in Journey Optimizer B2B Edition. Click **[!UICONTROL Edit settings]** at the top right to access the configuration options in the connected Marketo Engage instance. 

>[!NOTE]
>
>To access and edit these settings in Adobe Marketo Engage, you must have Product Administrator permissions. 

For more information about configuring the bot activity options, refer to the [Marketo Engage documentation](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/filtering-email-bot-activity#select-filter-type){target="_blank"}.
