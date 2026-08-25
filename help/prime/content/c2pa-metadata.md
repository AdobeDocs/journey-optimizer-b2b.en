---
title: C2PA Metadata
description: Learn how Adobe Journey Optimizer B2B Prime automatically applies C2PA metadata to images generated with generative AI, and what this means for your content.
feature: Assets, Content
role: User
badgeBeta: label="Beta" type="informative" tooltip="This feature is part of a limited beta release."
autotag-review: '2026-07-31T22:31:06.899Z'
TQID: 'https://experienceleague.adobe.com/fBPnAmupve3xMSw5fZPQBDTUfr-rwiH2-R3wbKvox-E'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a65c8aea-b21a-41ce-9ed7-6b517a69fd0b
    internal-label: Generative AI
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
    internal-label: Content management
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
  - id: c8402946-ff35-44c5-ab98-74c1bba0975f
    internal-label: Assets
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# C2PA metadata

Marketing organizations are more concerned than ever about content transparency, AI disclosure, and preventing the tampering of assets. The Content Authenticity Initiative (CAI) at Adobe builds tools compliant with the [Coalition for Content Provenance and Authenticity](https://c2pa.org/specifications/specifications/1.1/specs/C2PA_Specification.html#_trust_model) (C2PA) technical standard. _C2PA metadata_ is encrypted, tamper-evident information that can help viewers to understand the lineage of content and ensure the integrity of brand assets. This information includes:

* Issuer or Signer — Information about the entity or company that issued the digital signature to certify or sign the asset.
* Issue Date — The date on which the C2PA metadata was applied to the asset.
* Credit and Usage — Information about the producer of the asset, including name, social media handles, or other identity-related information.
* Process — Records of any edits or modifications made to the asset.
* Device Details — Information about the app or device used to create or edit the asset.
* AI Tool Used — If generative AI was used to create the asset, the name of the model used may be included.
* Other Pertinent Information — Additional data is also included to help offer more context about the history of an asset.

For comprehensive information about the asset history, you can use the Adobe Content Authenticity [inspection tool](https://contentauthenticity.adobe.com/inspect).

C2PA metadata persists with the image file. When an image that was generated or edited with generative AI is uploaded to or exported from [!DNL Adobe Journey Optimizer B2B Prime], its C2PA metadata is preserved.

For additional details about automatic attachment of C2PA metadata across Adobe CX Enterprise applications, see [_Generative AI content transparency_](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/overview/content-transparency){target="_blank"} in the AI in CX Enterprise guide.

>[!NOTE]
>
>Some methods of importing images into your content, such as extracting an image from a PDF or from an embedded (base64) source, might not preserve the original C2PA metadata. In these cases, C2PA metadata cannot be read from the source and none is created for the result.

>[!BEGINSHADEBOX]

## C2PA metadata persistence through channels {#channels}

When you include images in your email or WhatsApp messages, the C2PA metadata for the delivered images is also persisted:

* **Email** - When you use a _Send email_ journey action, add the image to your email content from the _Assets_ library. When the email is delivered, the recipient can download the image from the message and the C2PA metadata is intact.
* **WhatsApp** - Add the image to your WhatsApp message template in your Meta business account. You can add it directly from your system, or download an image file from the _Assets_ library. Use the template for a _Send WhatsApp_ journey action. When the WhatsApp message is delivered, the recipient can download the image from the message and the C2PA metadata is intact. 

>[!ENDSHADEBOX]

## Image generation {#generate}

>[!INFO]
>
>New laws are emerging around generative AI transparency, and Adobe is working to meet applicable requirements across jurisdictions. C2PA metadata is the provenance tool Adobe uses to meet the requirements of these laws.

When you use generative AI to create an image for your email content in [!DNL Journey Optimizer B2B Prime], C2PA metadata is automatically attached to the generated image and no action is required on your part. Generative AI tools produce a combined C2PA metadata element for variants of images with existing metadata, including the original source.

>[!NOTE]
>
>[!DNL Journey Optimizer B2B Prime] does not currently support manual image editing actions. C2PA metadata workflows for these actions are not applicable at this time.
