---
title: List Page Reference
TOCTitle: List Page
ms:assetid: 0e85eff8-88ad-4278-a023-9c623124e56d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc519455(v=AX.60)
ms:contentKeyID: 35244883
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# List Page Reference 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A list page in Enterprise Portal displays a list of entities of a specific type, such as customers or items. List pages are a primary way to access data in Enterprise Portal. The process of creating a list page for Enterprise Portal is very different from creating the other types of pages. You do not manually create and design the page in SharePoint. Instead, each list page in Enterprise Portal is created based on the list page form that is defined in the AOT. This is the same list page form that is used to define the list page in the Microsoft Dynamics AX client.

## Creating a List Page

Several steps are required to create a list page form that can be used for both the Microsoft Dynamics AX client and Enterprise Portal. See [List Page Forms](list-page-forms.md) for detailed information about how to complete the steps to create a list page form.

While the same list page form is used for both the Microsoft Dynamics AX client and Enterprise Portal, there are some differences that you must know about when you define a list that will be used for Enterprise Portal.

### Hyperlink field

Typically, the field in the first column of the grid for the list page in Enterprise Portal is a hyperlink field that the user clicks to display the details for that record. To enable a hyperlink field for the list page, you must select the field in the design for the grid of the list page form. Set the **HyperLinkDataSource** property for the field to indicate the data source that will provide record context information that is passed with the hyperlink. Set the **HyperLinkMenuItem** property to the menu item that indicates what resource the hyperlink is accessing. The menu item you use must have its **WebMenuItemName** property set to the name of the web menu item that indicates the Enterprise Portal page to open when the hyperlink is clicked.

### Action pane content

To create the content for the action pane that is used in Enterprise Portal, you use techniques similar to those to create an action pane for a form in the Microsoft Dynamics AX client. See the topics in [Action Pane Buttons](action-pane-buttons.md) for more information.

When creating the buttons for the action pane, be aware of the following limitations for Enterprise Portal:

  - The DropDialogButton is not supported by Enterprise Portal.

  - The CommandButton supports only **Delete** and **Export to Excel** operations for Enterprise Portal.

In most cases, the same action pane buttons can be used for the Microsoft Dynamics AX client and Enterprise Portal. Some actions can be performed only in the Microsoft Dynamics AX client or in Enterprise Portal. Sometimes the same action can be performed, but is accomplished in a different way in the client or in Enterprise Portal. When this situation occurs, you will have separate buttons for the action pane. The **DisplayTarget** property for the button, group, or tab on the action pane indicates whether the item will appear in the Microsoft Dynamics AX client, Enterprise Portal, or in both locations.

The action pane buttons access menu items that are defined in the AOT. For the action pane button to be visible in Enterprise Portal, the menu item being accessed must have the **WebMenuItemName** property set to the name of the web menu item that is to be accessed. If no web menu item has been specified, the button will not appear on the action pane in Enterprise Portal.

When you use an action pane button to open a page in Enterprise Portal that requires context, some properties may have to be set on the action pane button so that the context is passed. The following table lists the properties that you may have to set:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NeedsRecord</p></td>
<td><p>When set to <strong>Yes</strong>, the button is active only when a record is selected in the list. The context for the record is passed when the button is clicked.</p></td>
</tr>
<tr class="even">
<td><p>CopyCallerQuery</p></td>
<td><p>When set to <strong>Yes</strong>, the query for the calling form is copied to the target form.</p></td>
</tr>
<tr class="odd">
<td><p>SendExternalContext</p></td>
<td><p>When set to Yes, the external record context of the form is sent as the external record context for the menu item.</p></td>
</tr>
</tbody>
</table>


### FactBox area

The FactBox area of the list page displays Part resources (Info Parts, Form Parts, and Cue Groups) that you have created for the list page. These parts have some functional differences depending on whether they are used in a list page for the Microsoft Dynamics AX client or for Enterprise Portal.

Info Parts can be used in the FactBox area of a list page with little change needed for Enterprise Portal. If the Info Part has an action defined that works on the Microsoft Dynamics AX client, make sure that you have a corresponding action for Enterprise Portal. If you do not have a corresponding action, set the **DisplayTarget** property for the Info Part action so that action is displayed only on the client.

Form Parts that are used in the FactBox area for list pages have different behavior on the Microsoft Dynamics AX client and on Enterprise Portal. On the client, the Form Part displays the specified form resource. On Enterprise Portal, the Form Part displays the specified ManagedContentItem (User Control). If you want to use a Form Part in Enterprise Portal, make sure that you have defined the User Control that will display the content of the Form Part. You must also set the ManagedContentItem property for the Form Part to specify the User Control to display.

Cue Groups that are used in the FactBox area for list pages do not need any changes to their definition to work in Enterprise Portal. Because of how the Cue Groups access data from within Enterprise Portal, you must perform an incremental CIL (Common Intermediate Language) generation for the cues in the Cue Group to work. If the CIL has not been generated, the queries used for the cues will not run. The cues will display (-1) to indicate that a processing error occurred.

## Deploying a List Page to Enterprise Portal

When you deploy a list page to Enterprise Portal, a page is created in SharePoint. This page is fully configured. It will contain the necessary web parts, including the List web part, to display the list page content in Enterprise Portal.

### To deploy a list page to Enterprise Portal

1.  In the AOT, expand the **Menu Items** node.

2.  Expand the **Display** node and locate the menu item that is used to display the list page on the Microsoft Dynamics AX client.

3.  Right-click the menu item, and then click **Deploy to EP**.

4.  In the **Deploy to EP** window, select the web module that you want to deploy the list page to in Enterprise Portal. Click **OK**. The list page will be created on the Enterprise Portal and added to the Enterprise Portal document library for the site that you specified.
    

    > [!NOTE]
    > <P>If the list page already exists in the SharePoint library for the module, you will be asked whether to overwrite the page. Click <STRONG>OK</STRONG> to overwrite the existing page.</P>



You only have to deploy the list page one time. It is not required to redeploy the list page every time that you change it. When you do change the form resource for the list, you will have to clear the caches for Enterprise Portal for the changes to be seen. See [Troubleshooting: Enterprise Portal Development](troubleshooting-enterprise-portal-development.md) for more information about how to clear the caches for Enterprise Portal.

## Adding a list page to Enterprise Portal navigation

When you deploy a list page to Enterprise Portal, a URL Web Menu Item is created that has the same name as the menu item used to access the list in the Microsoft Dynamics AX client. You can add this URL Web Menu Item to the navigation for Enterprise Portal to provide access to the list page. For more information about how to add pages to the navigation, see [How to: Add Pages to Navigation](how-to-add-pages-to-navigation.md).

