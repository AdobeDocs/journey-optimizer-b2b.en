---
title: Content Credentials
description: Learn how Adobe Journey Optimizer B2B Prime automatically applies Content Credentials to images generated with generative AI, and what this means for your content.
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
# Content Credentials

Marketing organizations are more concerned than ever about content transparency, AI disclosure, and preventing the tampering of assets. The Content Authenticity Initiative (CAI) at Adobe builds tools compliant with the [Coalition for Content Provenance and Authenticity](https://c2pa.org/specifications/specifications/1.1/specs/C2PA_Specification.html#_trust_model) (C2PA) technical standard. _Content Credentials_, encrypted, tamper-evident metadata, can help viewers understand the lineage of content and ensure the integrity of brand assets. This information includes:

* Issuer or Signer — Information about the entity or company that issued the digital signature to certify or sign the asset.
* Issue Date — The date on which the Content Credential was applied to the asset.
* Credit and Usage — Information about the producer of the asset, including name, social media handles, or other identity-related information.
* Process — Records of any edits or modifications made to the asset.
* Device Details — Information about the app or device used to create or edit the asset.
* AI Tool Used — If generative AI was used to create the asset, the name of the model used may be included.
* Other Pertinent Information — Additional data may also be included to help offer more context about the history of an asset.

For a complete view, [Verify](https://contentcredentials.org/verify) can offer a more comprehensive insight into asset history.

Content Credentials persist with the image file. When an image that was generated with generative AI is uploaded to or exported from [!DNL Adobe Journey Optimizer B2B Prime], its Content Credentials are preserved.

>[!NOTE]
>
>Some methods of importing images into your content, such as extracting an image from a PDF or from an embedded (base64) source, might not preserve the original Content Credentials. In these cases, Content Credentials cannot be read from the source and none are created for the result.

## Image generation {#generate}

>[!INFO]
>
>New laws are emerging around generative AI transparency, and Adobe is working to meet applicable requirements across jurisdictions. Content Credentials are the provenance tool Adobe uses to meet the requirements of these laws.

When you use generative AI to create an image for your email content in [!DNL Journey Optimizer B2B Prime], Content Credentials are automatically attached to the generated image and no action is required on your part. Generative AI tools produce a combined Content Credentials element for variants of images with existing credentials, including the original source.

>[!NOTE]
>
>[!DNL Journey Optimizer B2B Prime] does not currently support manual image editing actions. Content Credentials workflows for these actions are not applicable at this time.
