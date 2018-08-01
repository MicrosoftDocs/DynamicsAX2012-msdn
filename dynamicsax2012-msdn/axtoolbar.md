---
title: AxToolbar
TOCTitle: AxToolbar
ms:assetid: 68cb60e9-7545-41b3-9f7a-9b7f39faa652
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc571972(v=AX.60)
ms:contentKeyID: 28119433
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# AxToolbar [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The AxToolbar component provides access to the actions that can be performed for the items in a page. The AxToolbar component has the same function as the [Toolbar Web Part](toolbar-web-part.md). Consider using an AxToolbar component in a User Control when you do not want to rely on having a Toolbar web part on the page where the User Control will be used.

## Properties

The AxToolbar component has the following properties:

### Accessibility

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
<td><p>AccessKey</p></td>
<td><p>Not used for Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>TabIndex</p></td>
<td><p>The tab order of the control.</p></td>
</tr>
</tbody>
</table>


### Appearance

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
<td><p>BackColor</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>BorderColor</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>BorderStyle</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>BorderWidth</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>CssClass</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>Font</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>ForeColor</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
</tbody>
</table>


### Behavior

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
<td><p>Enabled</p></td>
<td><p>Specifies whether the toolbar is enabled.</p></td>
</tr>
<tr class="even">
<td><p>EnableTheming</p></td>
<td><p>Indicates whether the control can be themed.</p></td>
</tr>
<tr class="odd">
<td><p>EnableViewState</p></td>
<td><p>Specifies whether the control automatically saves its state for use in round-trips.</p></td>
</tr>
<tr class="even">
<td><p>SkinID</p></td>
<td><p>The SkinId of the control skin that provides the skin of the control</p></td>
</tr>
<tr class="odd">
<td><p>ToolTip</p></td>
<td><p>Not used for Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>Visible</p></td>
<td><p>Indicates whether the control is visible and rendered.</p></td>
</tr>
</tbody>
</table>


### Data

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
<td><p>Expressions</p></td>
<td><p>The expressions that are bound to properties of the control.</p></td>
</tr>
<tr class="even">
<td><p>DataMember</p></td>
<td><p>The table or view from the data set that is being used for the toolbar.</p></td>
</tr>
<tr class="odd">
<td><p>DataSourceID</p></td>
<td><p>Specifies the AxDataSource component that will be used by the toolbar to access data.</p></td>
</tr>
</tbody>
</table>


### Layout

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
<td><p>Height</p></td>
<td><p>The height of the control.</p></td>
</tr>
<tr class="even">
<td><p>Width</p></td>
<td><p>The width of the control.</p></td>
</tr>
</tbody>
</table>


### Microsoft Dynamics AX

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
<td><p>Menu Item Help</p></td>
<td><p>Specifies whether the help text is displayed for each menu item.</p></td>
</tr>
<tr class="even">
<td><p>Web Menu Name</p></td>
<td><p>Specifies the Web Menu item in the AOT that defines the items displayed in the toolbar.</p></td>
</tr>
</tbody>
</table>


### Misc

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
<td><p>ID</p></td>
<td><p>The programmatic name of the control</p></td>
</tr>
<tr class="even">
<td><p>CausesValidation</p></td>
<td><p>Specifies whether the controls in the validation group specified by the <strong>ValidationGroup</strong> property will be validated when a toolbar item is clicked.</p></td>
</tr>
<tr class="odd">
<td><p>ValidationGroup</p></td>
<td><p>The name of the validation group for which the validation controls will be validated when a toolbar item is clicked. Each validation control has a <strong>ValidationGroup</strong> property that specifies which validation group it is part of.</p></td>
</tr>
</tbody>
</table>


## Events

The AxToolbar component has the events listed in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Event</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ActionMenuItemClicked</p></td>
<td><p>Occurs after an item in the toolbar menu has been clicked and the action has been performed.</p></td>
</tr>
<tr class="even">
<td><p>ActionMenuItemClicking</p></td>
<td><p>Occurs after an item in the toolbar menu has been clicked, but before the action has been performed.</p></td>
</tr>
<tr class="odd">
<td><p>DataBinding</p></td>
<td><p>Occurs when the server control binds to a data source.</p></td>
</tr>
<tr class="even">
<td><p>DataBound</p></td>
<td><p>Occurs after the server control binds to a data source.</p></td>
</tr>
<tr class="odd">
<td><p>Disposed</p></td>
<td><p>Occurs when a server control is released from memory, which is the last stage of the server control lifecycle when an ASP.NET page is requested.</p></td>
</tr>
<tr class="even">
<td><p>Init</p></td>
<td><p>Occurs when the server control is initialized, which is the first step in its lifecycle.</p></td>
</tr>
<tr class="odd">
<td><p>Load</p></td>
<td><p>Occurs when the server control is loaded into the System.Web.UI.Page object.</p></td>
</tr>
<tr class="even">
<td><p>PreRender</p></td>
<td><p>Occurs after the System.Web.UI.Control object is loaded by prior to rendering.</p></td>
</tr>
<tr class="odd">
<td><p>SetMenuItemProperties</p></td>
<td><p>Occurs before the menu items in the toolbar are displayed, allowing the properties to be set.</p></td>
</tr>
<tr class="even">
<td><p>Unload</p></td>
<td><p>Occurs when the server control is unloaded from memory.</p></td>
</tr>
</tbody>
</table>


## Defining Toolbar Content with Code

In most cases, you define the content displayed by a toolbar by using Web Menu and Web Menu Item resources in the AOT. If you need the toolbar content to be more dynamic, you can define the toolbar content with code you add to the User Control that displays the toolbar. You do this by implementing a method that returns an IWebMenuGenerator object for the User Control. This method defines the contents of the toolbar.

The following using statements reference the namespaces that are required to define toolbar content with code.

using Microsoft.Dynamics.Framework.Portal.UI.WebControls;

using Microsoft.Dynamics.AX.Framework.Services.Client;

The following example is the GenerateToolbar() private method for a User Control. It defines the content for an AxToolbar component that is also part of the User Control. The toolbar contains a top-level item and a menu. The menu contains an item and a submenu with two additional items. After the contents of the toolbar have been defined, the completed structure is returned from the method.

``` csharp
// This is a private method that creates the content of a web menu
// that is used for an AxToolbar component.
private IWebMenuGenerator<WebMenuGeneratorEventArgs> GenerateToolbar()
{
    WebMenuItemMetadataHierarchicalContainer toolbar;
    WebMenuItemMetadataHierarchicalContainer menu;
    WebMenuItemMetadataHierarchicalContainer subMenu;
    URLWebMenuItemMetadata workOrderDetails;
    URLWebMenuItemMetadata roomDetails;
    URLWebMenuItemMetadata roomAdd;
    URLWebMenuItemMetadata MicrosoftLink;

    // Create the container that holds the toolbar menu items.
    toolbar = new WebMenuItemMetadataHierarchicalContainer("Toolbar");

    // Add a top-level item to the toolbar.
    MicrosoftLink = new URLWebMenuItemMetadata("Microsoft", "Microsoft", "Link to Microsoft.com", "http://www.microsoft.com");
    toolbar.AddWebMenuItem(MicrosoftLink);

    // Create the container that will hold the menu.
    menu = new WebMenuItemMetadataHierarchicalContainer("Facility", "Facility", "");

    // Define a menu item to add to the menu. This menu item uses an existing
    // web menu item that is defined in the AOT.
    workOrderDetails = new URLWebMenuItemMetadata(MetadataCache.GetURLWebMenuItemMetadata("WorkOrderDetails"));
    menu.AddWebMenuItem(workOrderDetails);

    // Create the container that will act as a submenu.
    subMenu = new WebMenuItemMetadataHierarchicalContainer("Rooms", "Rooms", "Actions for rooms");

    // Define two menu items that will appear in the submenu.
    roomDetails = new URLWebMenuItemMetadata(MetadataCache.GetURLWebMenuItemMetadata("RoomDetails"));
    roomAdd = new URLWebMenuItemMetadata(MetadataCache.GetURLWebMenuItemMetadata("RoomAdd"));

    // Add these menu items to the submenu.
    subMenu.AddWebMenuItem(roomDetails);
    subMenu.AddWebMenuItem(roomAdd);

    // Add the submenu to the menu.
    menu.AddSubMenu(subMenu);

    // Add the menu to the main toolbar.
    toolbar.AddSubMenu(menu);

    // Return the completed menu structure to use for the toolbar.
    return new WebMenuItemMetadataHierarchicalContainerGenerator(toolbar);
}
```

The contents of the AxToolbar component should be loaded when the page containing the User Control is loaded. In the Page\_Load() method for the User Control, the WebMenuGeneratorConstructor for the AxToolbar component is used to create the content. Notice how the toolbar structure returned from the private method in the previous example is used by the constructor of the toolbar.

``` csharp
protected void Page_Load(object sender, EventArgs e)
{
    // Load the contents of the AxToolbar component.
    this.AxToolBar1.WebMenuGeneratorConstructor = this.GenerateToolbar;
}
```

