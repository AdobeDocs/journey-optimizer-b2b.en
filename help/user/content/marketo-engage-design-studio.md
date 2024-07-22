---
title: Marketo Engage Design Studio assets
description: Learn about using the Marketo Engage Design Studio asset management integration in Journey Optimizer B2B Edition.
feature: Assets, Integrations
---
# Marketo Engage Design Studio assets

When Marketo Engage Design Studio is the as the asset source for Journey Optimizer B2B Edition, you can easily manage and use the available assets for your account journeys.

## Browse and access assets

To access Adobe Marketo Engage Design Studio assets from within Journey Optimizer B2B Edition, go to the left navigation and click **[!UICONTROL Content Management]** > **[!UICONTROL Assets]**. This action opens a listing page with all the assets listed.

You can also view the assets by folder by clicking the _Show Folders_ icon on the top left. This action opens the folder structure.

You can sort the table by any of the columns by clicking the column title.

Search for an image asset within the selected folder by entering a string in the search bar.

Customize the columns you wish to be listed in the table, by clicking on the 'Customize table' icon on the top right

Select the columns you want to display in the listing and click **[!UICONTROL Apply]**.

## Add assets

From Journey Optimizer B2B Edition, you can add image assets to the Adobe Marketo Engage Design Studio by clicking **[!UICONTROL Add Assets]** at the top right. The maximum file size is 100 MB.

You can add assets from your local system of up to 10 files at a time. You can also select the destination folder to store the assets using the folder selector. You have the option to overwrite files when you upload one or more files with an existing file name.

The file names of the selected images are displayed in the dialog. Asset file names must be unique (across folders), and if a file with the name already exists an error message is displayed. Names can have a maximum of 100 characters, and cannot contain special characters (such as `;`, `:`, `\`, and `|`) .

## View asset details

Click the name of any asset to open the asset details page.

## View asset used-by references

Within the asset details page, click the **[!UICONTROL Used By]** tab to view details of where the asset is currently used within Journey Optimizer B2B Edition, across emails, email templates, and fragments.

>[!IMPORTANT]
>
>Any asset that is currently _IN USE_ in any of the emails, email templates, or fragments **cannot** be deleted.

References are displayed by category: _Email_, _Email template_, or _Fragment_. Emails in Journey Optimizer B2B Edition are embedded and and authored within journeys, so the parent journey of the email that uses the asset is displayed in references.

Clicking the link directs you to the corresponding email, email template, or fragment where the asset is used.

## Delete assets

Any asset that is currently _IN USE_ in any of the emails, email templates, or fragments cannot be deleted, so ensure that you check the used-by references before initiating an asset removal. Also, a delete action cannot be undone, so check before initiating a removal action.

You can delete an asset using either of the following methods:

* Asset details > More > Delete
* Assets listing > Ellipsis next to the asset > Delete

This action opens a confirmation dialog. You can abort the process by clicking **[!UICONTROL Cancel]**, or click **[!UICONTROL Delete]** to confirm deletion.

If the asset is currently in use, the action opens a informational dialog that alerts you that it cannot be deleted. You must click **[!UICONTROL OK]**, which aborts the deletion.

## Replace assets

You can replace an asset using either of the following methods:

* Asset details > More > Replace
* Assets listing > Ellipsis next to the asset > Replace

This action opens a confirmation dialog. You can abort the process by clicking **[!UICONTROL Cancel]**. To proceed, select a file from your local system and click **[!UICONTROL Replace]**. If you select multiple files in your local system, the first file selected is used for the replacement.

If the file to be replace is currently in use, an informational dialog alerts you that the new image file will replace the image in all places where it is used (emails, email templates and fragments).

## Download assets

You can download an asset using either of the following methods:

* Asset details > More > Download
* Assets listing > Ellipsis next to the asset > Download

This action opens a confirmation dialog.

You can abort the process by clicking **[!UICONTROL Cancel]**, or click **[!UICONTROL Download]** to initiate downloading the asset to your local system.

## Apply bulk actions on assets

From the listing page (Content Management > Assets), select multiple assets at a time by selecting each checkbox to the left. A message banner appears at the bottom when you select multiple assets.

You can take the following bulk actions:

### Move assets

You will see a Move Assets dialog, which lists the names of the selected assets and allows you to select the 'target' folder where you want to move these assets into. Once selected, the folder path updates in the modal next to "Selected assets will move to:" And you will get a confirmation toast after successfully moving the assets

### Delete assets

You can delete up to a maximum of 20 assets can be selected at a time to bulk delete those
You will see a delete confirmation dialog. If any of the assets are currently in use, the Delete (of that particular asset) will be aborted and you will see the below message

## Apply folder-level actions



## Create a new folder

From the Assets listing page, click **[!UICONTROL Create Folder]** button at the top right.

In the dialog, enter the file name and select the destination (parent) folder for the new folder.

Folder names must be unique, with a maximum of 100 characters, and cannot contain special characters, such as `;`, `:`, `\`, `|`.



Actions from the folder structure panel:

Click Show Folder on the top left
Click the ellipsis (...) next to any of the folders to apply folder-level actions


You can take the following actions at the folder level:

Add Assets

Opens the same modal as indicated in this section & the same rules apply

Create folder
Opens the same modal as indicated in this section & the same rules apply

Rename
Opens a modal similar to the one below, the same folder name restrictions as mentioned earlier apply:

Move
Opens a modal similar to the one below, select the target folder where you want the selected folder to be moved into:
If you try to move a folder inside a sub-folder (within the selected folder itself), you will see the below error message

Delete
This opens up a modal similar to the one below, you can either abort deletion or confirm deletion

Convert to Archive folder

Select this option to Archive a folder (images in archived folders are not searchable)
Any archived folder can be unarchived at any time by clicking on the ellipsis > Unarchive folder
In either case you will get a confirmation toast once the action is completed

Use Assets in email content

Assets can be used in your email/ email template / visual fragment, from the visual content editor UI.

Once in the visual editor UI, select the 'Assets Picker' from the left nav
