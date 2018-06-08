---
title: Page Changes
TOCTitle: Page Changes
ms:assetid: 523ff5e6-7e2d-4b83-8310-bfe1f686858b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh272125(v=AX.60)
ms:contentKeyID: 36542035
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Page Changes 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Several features added for Microsoft Dynamics AX 2012 and Enterprise Portal will influence how you design pages for your Enterprise Portal application. The following sections discuss each of these features and how they affect the Enterprise Portal application that you are converting.

## List Pages

The framework used to create list pages in Microsoft Dynamics AX 2012 has been improved. The same list page definition that you create for the Microsoft Dynamics AX client can also be used for Enterprise Portal.

List pages that you created in Enterprise Portal for Microsoft Dynamics AX 2009 can still be used. You may have to change the data set and User Control for the list page to accommodate any changes in the tables accessed by the list page. For instance, the table being accessed may now use surrogate keys.

Because of the enhanced usability, we recommend that you update your lists to use the improved list page framework. If your list pages appear in the Microsoft Dynamics AX client, you must use the new list page framework. It is reasonable to use these same list pages in your Enterprise Portal application.

See [List Page Forms](list-page-forms.md) for detailed information about how to complete the steps to create a list page form. See [List Page Reference](list-page-reference.md) for specific information about how to use list pages in Enterprise Portal.

## Cues

If you have cues that you created in Microsoft Dynamics AX 2009, you will have to re-create the cues in Microsoft Dynamics AX 2012. The framework used for cues has changed significantly. Refer to the topics in [Cues and Cue Groups](cues-and-cue-groups.md) for information about how to implement cues in Microsoft Dynamics AX 2012. See [Cues Web Part](cues-web-part.md) for information about how to use the revised web part to display cues in Enterprise Portal.

## Action Pane

Pages in Enterprise Portal now use the Action Pane (SharePoint Ribbon) to provide access to the actions the user can perform on the page. If a page in your Enterprise Portal application uses a toolbar to display commands, consider revising the page to display the commands on the Action Pane instead. See [Action Pane Web Part](action-pane-web-part.md) for more information about how to use an Action Pane.

## Modal Dialogs

In Enterprise Portal for Microsoft Dynamics AX 2009, most pages were opened in-line. The new page replaced the existing content in the browser window. SharePoint 2010 allows for pages to be opened as modal dialogs. In Enterprise Portal for Microsoft Dynamics AX 2012, most entity overview and task pages are now displayed as modal dialogs. By using a modal dialog, the context of the previous page (such as a list page) is maintained when the user finishes the task in the modal dialog. We recommend that you use a modal dialog to display the entity overview and task pages for your Enterprise Portal application.

Properties for the web menu item used to access a page control whether the page is displayed as a modal dialog. See [How to: Create Web Menu Items](how-to-create-web-menu-items.md) for more information about opening pages as modal dialogs.

## Web Parts

Several web parts are no longer available for Enterprise Portal. The following web parts were removed because the X++ Web Framework and X++ Reports are no longer available for Enterprise Portal:

  - Generic Web Part

  - Web Form

  - Web Menu

The Box Menu web part is no longer available. Use the [Left Navigation Web Part](left-navigation-web-part.md) instead.

