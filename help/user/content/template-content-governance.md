---
title: Template Content Governance
description: Learn how to lock content elements within your email templates so that you can govern how they can be altered for use in account journeys.
feature: Templates, Email Authoring, Content
role: User
exl-id: 0cf852cd-491c-4478-8d5e-51fd2cc2625a
---
# Template content governance

Within many Marketing organizations, there are content professionals that design email campaigns. A given design can be used as a foundation for custom account journeys across the organization. To ensure adherence to approved content designs, you can use content governance features to lock template components. With content locking activated in the email template, marketers can alter only the permitted elements to keep it aligned with the content strategy.

For example, you might lock the header and footer that is designed for brand communications continuity. You could also lock the column that contains the main body section, but allow authors to modify the text so that it meets their purpose within the account journey design.

## Activate content governance for the template

After you use the visual designer to [author the structural and content components](./email-template-authoring.md) for your email template, enable governance and apply specific content locking as needed. 

1. In the visual designer, access the layers/containers and elements using the _Navigation tree_. 

   Click the _Navigation tree_ icon ( ![Link icon](../assets/do-not-localize/icon-navigation-tree.svg) ) to the left of the canvas to display the tree.

1. In the tree, select the root **[!UICONTROL Body]** component.

   The properties panel to the right of the canvas displays the _[!UICONTROL Settings]_ tab by default.

1. Enable the **[!UICONTROL Governance]** option.

   ![Enable governance for an email template](./assets/governance-template-enable.png){width="800" zoomable="yes"}

   With this option enabled, the default _[!UICONTROL Mode]_ is **[!UICONTROL Read only]**. With this mode set at the root level, all elements in the template are locked. The tree structure on the left displays the _Read only_ icon ( ![Read only icon](../assets/do-not-localize/icon-tree-lock.svg) ) next to the root and all child elements.

1. To enable specific content locking within the template, change the **[!UICONTROL Mode]** to **[!UICONTROL Content locking]**.

   With this mode set at the root level, all elements in the template are unlocked. The tree structure on the left displays the _Content locking_ icon ( ![Content locking icon](../assets/do-not-localize/icon-tree-content-lock.svg) ) next to the root element. Apply content locking to containing (structural) and individual content components as needed.

   To allow journey email authors to add structural or content elements, turn on **[!UICONTROL Enable content addition]**. Choose the type of additions that you want to allow:

   * **[!UICONTROL Allow structure & content addition]** - Choose this option if you want to allow authors to add both structural and content elements.

   * **[!UICONTROL Allow content addition only]** - Choose this option if you want to allow authors to add only content elements.

   ![Enable content additions](./assets/governance-template-content-additions.png){width="600" zoomable="yes"}

   With this mode set at the root level, all elements in the template are locked. The tree structure on the left displays the _Read only_ icon ( ![Read only icon](../assets/do-not-localize/icon-tree-lock.svg) ) next to the root and all child elements.
<!-- 

   
- ![Link icon](../assets/do-not-localize/icon-navigation-tree.svg)
- ![Read only icon](../assets/do-not-localize/icon-tree-lock.svg)
- ![Content edit icon](../assets/do-not-localize/icon-tree-content-lock.svg)
- ![Content edit icon](../assets/do-not-localize/icon-tree-edit-text.svg)
- ![Edit element](../assets/do-not-localize/icon-edit.svg) -->

## Apply locking to a structure

Using the structural inheritance model, plan the layout and structure of your email template according to the governance that you want to apply. Use the structural components as containers to group items in ways that make them easy to designate as locked or editable. When the email template design is in place, review the structure and apply locking features according to your plan.

Applying a lock type at the structure level provides a default setting for its child components. You can then apply a specific locking setting at the column or content element level as needed.

1. Click the _Navigation tree_ icon ( ![Link icon](../assets/do-not-localize/icon-navigation-tree.svg) ) to the left of the canvas to display the tree.

1. Select the structure in the tree.

   The properties panel to the right of the canvas displays the _[!UICONTROL Settings]_ tab by default.

1. Set the **[!UICONTROL Lock type]**:

   * **[!UICONTROL Locked]** - With this setting, all child components are locked by default. The tree structure on the left displays the _Read only_ icon ( ![Read only icon](../assets/do-not-localize/icon-tree-lock.svg) ) next to all child components.

   * **[!UICONTROL Editable]** - With this setting, all child components are editable by default. The tree structure on the left does not display icons next to the child components.

   ![Apply content locking to a structural component](./assets/governance-template-structure-locking.png){width="800" zoomable="yes"}

## Set locking for a child component

1. Select the component in the tree.

   The properties panel to the right of the canvas displays the _[!UICONTROL Settings]_ tab by default.

1. Enable the **[!UICONTROL Use specific locking]** option.

1. Choose the type of governance to apply:

   * **[!UICONTROL Editable]** - Allows full editorial control of the component during email authoring.
   * **[!UICONTROL Editable content only]** - Allows email authors to change the content, but not the component itself.
   * **[!UICONTROL Locked]** - Prevents any changes to the component during email authoring.

      For a locked component, you can allow the removal of the component during email authoring by turning on the **[!UICONTROL Allow delete]** option.

   ![Apply content locking to a child component](./assets/governance-template-component-locking.png){width="800" zoomable="yes"}
