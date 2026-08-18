---
title: C2PA Metadata
description: Learn how Adobe Journey Optimizer B2B Edition automatically applies C2PA metadata to images generated or edited with generative AI tools, and what this means for your content.
feature: Assets, Content
role: User
autotag-review: '2026-07-31T22:15:54.535Z'
TQID: 'https://experienceleague.adobe.com/9XCqPWz62uDDLFAyxARfD2jErYx2aOiOB5fAOGLLTbo'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a65c8aea-b21a-41ce-9ed7-6b517a69fd0b
    internal-label: Generative AI
  - id: bef5003b-cad2-4f40-bdb2-a80426d52ef5
    internal-label: AI Assistant
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
    internal-label: Content management
subfeature_v2:
  - id: c8402946-ff35-44c5-ab98-74c1bba0975f
    internal-label: Assets
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# C2PA metadata

Marketing organizations are more concerned than ever about content transparency, AI disclosure, and preventing the tampering of assets. The Content Authenticity Initiative (CAI) at Adobe builds tools compliant with the [Coalition for Content Provenance and Authenticity](https://c2pa.org/specifications/specifications/1.1/specs/C2PA_Specification.html#_trust_model) (C2PA) technical standard. _C2PA metadata_ is encrypted, tamper-evident information that helps viewers to understand the lineage of content and ensure the integrity of brand assets. This information includes:

* Issuer or Signer - Information about the entity or company that issued the digital signature to certify or sign the asset.
* Issue Date - The date on which the C2PA metadata was applied to the asset.
* Credit and Usage - Information about the producer of the asset, including name, social media handles, or other identity-related information.
* Process - Records of any edits or modifications made to the asset.
* Device Details - Information about the app or device used to create or edit the asset.
* AI Tool Used - If generative AI was used to edit or create the asset, the name of the model used may be included.
* Other Pertinent Information - Additional data may also be included to help offer more context about the history of an asset.

For comprehensive information about the asset history, you can use the Adobe Content Authenticity [inspection tool](https://contentauthenticity.adobe.com/inspect).

C2PA metadata persists with the image file. When an image that was generated or edited with generative AI is uploaded to or exported from [!DNL Adobe Journey Optimizer B2B Edition], its C2PA metadata is preserved.

>[!NOTE]
>
>Some methods of importing images into your content, such as extracting an image from a PDF or from an embedded (base64) source, might not preserve the original C2PA metadata. In these cases, C2PA metadata cannot be read from the source and none is created for the result.

>[!BEGINSHADEBOX]

## C2PA metadata persistence through channels {#channels}

When you include images in your email or WhatsApp messages, the C2PA metadata for the delivered images is also persisted:

* **Email** - When you use a _Send email_ journey action, add the image to your email content from the _Assets_ library. When the email is delivered, the recipient can download the image from the message and the C2PA metadata is intact.
* **WhatsApp** - Add the image to your WhatsApp message template in your Meta business account. You can add it directly from your own system, or download an image file from the _Assets_ library. Use the template for a _Send WhatsApp_ journey action. When the WhatsApp message is delivered, the recipient can download the image from the message and the C2PA metadata is intact. 

>[!ENDSHADEBOX]

## Actions that affect C2PA metadata {#cc-workflows}

>[!INFO]
>
>New laws are emerging around generative AI transparency, and Adobe is working to meet applicable requirements across jurisdictions. C2PA metadata is the provenance tool Adobe uses to meet the requirements of these laws.

When you generate or edit an image with generative AI tools in [!DNL Journey Optimizer B2B Edition], C2PA metadata is automatically attached to that image and no action is required on your part.

### Generate an image {#generate}

**_Example:_** Generate a banner image for an email from a text prompt describing the desired visual. C2PA metadata is attached to the generated image.

When you create a new image from a text prompt, from a reference image, or generate a similar image, C2PA metadata is always attached.

### Crop an image {#crop}

**_Examples:_**

* Crop a generated banner image to fit a web page. The C2PA metadata is preserved through the crop. 
* Use an uploaded stock photo as an email background and crop it to fit the screen. If the stock photo carries no generative AI information, C2PA metadata is not created.

When you make an adjustment to an image file, such as cropping it to requested dimensions, it retains its C2PA metadata only if the source image already had it. Cropping recreates the image pixels, which normally removes that C2PA metadata, so AI Assistant reads it from the source image before cropping, then recreates and re-attaches it to the cropped result. Cropping itself does not add a new generative AI action; it preserves the existing one.

### Add a text overlay

**_Example:_** Produce a promotional headline as a text overlay on a generated background image for a landing page. The C2PA metadata from the background image is preserved.

When you render generated text on top of a background image, C2PA metadata is attached in the resulting image only if the background image already had C2PA metadata. Rendering the overlay produces a new image, so the image editing tool reads the C2PA metadata from the background and re-attaches it to the result. The overlay step does not add a new generative AI action.

### Overlay an image

**_Examples:_**

* Create an email header by combining a generated product image with a generated background. The result carries C2PA metadata reflecting both generative AI sources.
* Combine two uploaded brand photos into one collage image. Since neither source image carries a generative AI action, C2PA metadata is not created.

When you composite two or more images together and any of the source images have C2PA metadata, the combined image retains it, merged into a single C2PA metadata element. Compositing produces a new image from the sources, which normally removes that C2PA metadata. But the image editing tools read the source metadata before compositing, then build a single combined C2PA metadata element that lists every source that contributed a generative AI action.

<!--

In [!DNL Adobe Journey Optimizer B2B Edition], you can see C2PA metadata directly within the _Assets_ library. When you open the asset details, any image with C2PA metadata (such as those created with GenAI services) shows the manifest details in a dedicated panel. If the asset is downloaded, published, or shared, the C2PA metadata remains intact with the asset.

_To access C2PA metadata:_

1. In the left navigation, expand **[!UICONTROL Content Management]** and select **[!UICONTROL Assets]**.

   This action opens a listing page with all the assets listed.

1. Navigate to a folder, and select the desired asset.

1. In the right panel, ??? where is it.

-->
