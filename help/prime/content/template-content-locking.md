---
title: Content locking for email templates
description: Use governance settings in Journey Optimizer B2B Prime to lock content in email templates at the structure or component level, controlling what email authors can edit.
badgeBeta: label="Beta" type="informative" tooltip="This feature is par of a limited beta release."
---

# Content locking for email templates

Content locking allows template authors to define governance rules that restrict which parts of an email template can be modified when the template is used in a journey. This helps brand and compliance teams protect key design elements — such as headers, logos, and legal content — while allowing marketing teams to customize the message within the approved structure.

>[!NOTE]
>
>Content locking is an editor-level governance feature. It controls what authors can edit in the email design space but does not prevent changes made through the API.

Only users with the **[!UICONTROL Manage content templates]** permission can configure governance settings.

## Governance modes {#modes}

When you enable governance on a template, select one of two modes:

| Mode | Description |
| ---- | ----------- |
| **[!UICONTROL Content locking]** | Selectively lock specific structures or components. Unlocked areas remain editable by authors. |
| **[!UICONTROL Read only]** | Lock the entire template. Authors can apply it to an email but cannot modify any part of its content. |

## Enable governance {#enable}

1. Open the template in the email design space.
1. In the right rail, click the **[!UICONTROL Body]** component to select it.
1. Toggle on **[!UICONTROL Governance]**.
1. From the mode dropdown, select **[!UICONTROL Content locking]** or **[!UICONTROL Read only]**.

If you selected **[!UICONTROL Content locking]**, continue with locking individual elements.

### Lock a structure {#lock-structure}

1. On the canvas, select the structure (column layout) you want to protect.
1. In the right rail, enable the **[!UICONTROL Lock structure]** toggle.

All content nested within a locked structure is automatically locked. To allow a specific component inside a locked structure to remain editable, select the component and enable **[!UICONTROL Editable]** in the right rail.

### Lock a component {#lock-component}

Within an editable structure, you can lock individual content components.

1. Select the component on the canvas.
1. In the right rail, enable the **[!UICONTROL Lock content]** toggle.

### Allow content additions {#allow-additions}

When using **[!UICONTROL Content locking]** mode, you can allow authors to add new content to the template while keeping locked elements protected:

1. Enable **[!UICONTROL Allow content addition]**.
1. Choose whether authors can add both structures and content components, or content components only.

## Identify locked elements {#identify}

The **[!UICONTROL Navigation tree]** in the left rail shows lock and pencil icons to help authors quickly identify what they can and cannot modify:

* A **lock icon** indicates an element that is locked.
* A **pencil icon** indicates an element that is editable.

Locked elements are visually indicated in the canvas when an author opens the template.

## Considerations

Governance settings are saved with the template. Any email created from a governed template inherits its locking configuration at the time it is applied. Updating governance settings on a template does not affect emails previously created from it.
