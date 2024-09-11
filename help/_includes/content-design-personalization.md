---
title: Content authoring - personalization
description: Reused section about using personalization for content authoring
---
# Content authoring - personalization

Journey Optimizer B2B Edition uses an inline simple syntax that allows you to create expressions with personalized content enclosed by double curly braces `{}`. You can add multiple expressions in the same content or field without restrictions.

Examples:

* Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}`

* `Hello {{profile.person.name.fullName}}`

When processing the message (email and SMS), Journey Optimizer B2B Edition replaces the expression with the data contained in the Experience Platform database. So, the first example becomes _Hello John Doe_.

The following example outlines steps to personalize content using lead/account attributes and system tokens.

1. Select the text component and click the _Add personalization_ icon in the toolbar.

   ![Click the Personalize icon](../assets/content-design-shared/visual-designer-personalize-icon.png){width="600"}

   This action opens the _Edit Personalization_ dialog.

1. Click **+** or **...** to add a token to the blank space.

   ![Construct personalized text using tokens](../assets/content-design-shared/visual-designer-personalize-dialog.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.
