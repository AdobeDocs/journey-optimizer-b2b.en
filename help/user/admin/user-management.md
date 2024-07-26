---
title: User management
description: Learn how to assign team members to Journey Optimizer B2B Edition product profiles.
feature: Setup
roles: Admin
exl-id: ddbdc6a5-49bc-46cd-8d9b-1d37223dffe2
---
# User management

After provisioning is complete and sandboxes are bound, complete the following steps to provide Adobe Journey Optimizer B2B Edition access for your team and users.

1. [Create a Marketo Engage product profile](#marketo-engage-profile) in the Admin Console (new Marketo Engage instance only).
1. [Create a user group](#create-user-group) in the Admin Console.
1. [Create a role](#create-role) in AEP Permissions.
1. [Add users](#add-users) in the Admin Console.

As an administrator, you can complete these tasks in the Adobe Admin Console, which is a central place to administer and manage your Adobe product licenses and users. In the Admin Console, you can create and manage users in a single location instead of within your various individual solutions. Refer to the [Admin Console overview](https://helpx.adobe.com/enterprise/using/admin-console.html) page to learn more about its functions and capabilities.

## Access the Admin Console

Before you can use the Admin Console to administer users within your team, you need to ensure that you can access the Admin Console and have the appropriate permissions.

1. As a system administrator, you should receive multiple emails from Adobe as part of the onboarding process.

   Look for the welcome email that provides the information about the organization name to which you have been granted access.

1. Click the **[!UICONTROL Get started]** link in your welcome email to navigate to the Admin Console. 

   If you cannot find the email, open a browser directly to the Admin Console at [https://adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Log in using your Adobe ID.

   Upon successful login, you see the _Overview_ page of the Adobe Admin Console.

1. If you have access to multiple organizations, ensure that you have logged in to the correct organization.

   To change your organization, click the organization name from the top right corner and choose the organization to which you need access.

1. Select **[!UICONTROL Administrators]** from the _[!UICONTROL Users]_ card to verify that you are a system administrator.

   ![Admin Console overview - click Administrators](./assets/admin-console-overview-administrators.png){width="700" zoomable="yes"}

1. Search by entering your Adobe ID email, username, first, or last name.

   * If your access is correctly configured, the search returns your record. 

   * If the value in the **[!UICONTROL ADMIN ROLE]** column shows `System`, you know that you (or the displayed user) are a system administrator.

## Create the Marketo Engage product profile {#marketo-engage-profile}

When granting users access to an Adobe solution, you do not necessarily want to give them full access. Product profiles enable each solution to have its own set of user permissions. Use the Admin Console to assign product profiles.

For more information about using product profiles for user entitlements, see [Manage product profiles for enterprise users](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) in the Admin Console documentation.

>[!NOTE]
>
>An Admin Console system administrator or Marketo Engage product administrator can perform these steps.

1. Log in to [https://adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Select the **[!UICONTROL Products]** tab.

1. Open the Market Engage instance where you want to add the profile and click New profile.

   ![Admin Console - Marketo Engage instance - New profile](./assets/admin-console-marketo-engage-instance-new-profile.png){width="700" zoomable="yes"}

1. Enter a product profile name, such as _Standard User_.

1. Click **Next** and then **Save**.

## Create a user group {#create-user-group}

A user group is a collection of users are granted a shared set of permissions. You can add or remove users in your user group. The group permissions remain the same while the users within the group change.

For more information about how user groups are used to manage permissions, see [Manage user groups](https://helpx.adobe.com/enterprise/using/user-groups.html) in the Admin Console documentation.

>[!NOTE]
>
>An Admin Console system administrator can perform these steps.

1. Log in to [https://adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Select the **[!UICONTROL Users]** tab.

1. Choose **[!UICONTROL User Groups]** in the left navigation.

1. Click **[!UICONTROL New user group]** at the top right.

1. Enter a name for the user group, such as _Standard Users_ and click **[!UICONTROL Save]**.

1. Click the user group you just created.

1. Select the **[!UICONTROL Assigned product profiles]** tab and click **[!UICONTROL Assign profile]**.

1. Click **+** and add each instance of the following products:

   * [!UICONTROL Marketo Engage]
   * [!UICONTROL Adobe Experience Platform - AEP-Default-All-Users]
   * [!UICONTROL Adobe Experience Platform Data Collection]
   * [!UICONTROL Data Collection All Access]

   ![Admin Console - user-group - add products](./assets/admin-console-user-group-add-products.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.

## Create a role in AEP Permissions {#create-role}

Permissions are unitary rights that allow you to define the authorizations assigned to a product profile. Each permission is gathered under a capability, such as journeys or buying groups, which represents the different functionalities or objects in Journey Optimizer B2B Edition.

The _Permissions_ area of Adobe Experience Platform is where administrators can define user roles and access policies to manage access permissions for features and objects within a product application. In this app, you can create and manage roles, as well as assign the desired resource permissions for these roles. Permissions also allow you to manage the labels, sandboxes, and users associated with a specific role.

For more information, see [Manage permissions for a role](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/permissions) in the Experience Platform documentation.

>[!NOTE]
>
>To complete the following steps, you must be a product administrator for Adobe Experience Platform. 

1. Go to [experience.adobe.com](https://experience.adobe.com/).

1. In the _[!UICONTROL Quick access]_ panel, select **[!UICONTROL Permissions]**.

   >[!NOTE]
   >
   >If you don't see _[!UICONTROL Permissions]_, you may need to click **[!UICONTROL View all]** and select it from the available applications.

   ![Experience Platform - access Permissions](./assets/aep-permissions.png){width="700" zoomable="yes"}

1. Select **[!UICONTROL Roles]** in the left navigation and select **[!UICONTROL Create role]**.

1. In the _[!UICONTROL Create new role]_ dialog, enter a name for the role, such as _AJO B2B_, and a description (optional).

1. Click **[!UICONTROL Confirm]**.

1. Select your sandboxes.

   ![Experience Platform - add sandboxes for the new role](./assets/aep-permissions-role-sandboxes.png){width="700" zoomable="yes"}

1. Add the profile permissions:

   * In the _[!UICONTROL Resources]_ list on the left, locate the **[!UICONTROL Profile Management]** item and click the plus (**+**) icon to add the attribute.

   * For the attribute, add the following permissions:
      * [!UICONTROL View segments]
      * [!UICONTROL Manage segments]
      * [!UICONTROL View profiles]
      * [!UICONTROL Manage profiles]
      * [!UICONTROL View B2B profile]
      * [!UICONTROL Manage B2B profile]

   ![Experience Platform - add profiles for the new role](./assets/aep-permissions-role-profiles.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]** at the top right.

1. Go to the role details and select the **[!UICONTROL User groups]** tab.

1. Click **[!UICONTROL Add Groups]**.

   ![Experience Platform - add profiles for the new role](./assets/aep-permissions-role-add-groups.png){width="700" zoomable="yes"}

1. Select the checkbox next to the user group that you created previously in the Admin Console.

1. Click **[!UICONTROL Save]**.

## Add users to the group in the Admin Console

>[!NOTE]
>
>An Admin Console system administrator or a product administrator can perform these steps.

For information about user management, see [Admin Console users](https://helpx.adobe.com/enterprise/using/user-groups.html) in the Admin Console documentation.

1. Go to [https://adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Under _[!UICONTROL Quick links]_, click **[!UICONTROL Add users]**.

1. Add each user:

   * Enter the user's email address, first name, and last name.

      ![Experience Platform - add profiles for the new role](./assets/admin-console-add-users.png){width="600" zoomable="yes"}

   * For **[!UICONTROL User groups]**, click **+**.

   * Select the user group that you created previously.
   
   * Click **[!UICONTROL Apply]**.

1. Click **[!UICONTROL Save]**.
