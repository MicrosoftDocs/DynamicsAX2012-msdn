---
title: AxActionPane
TOCTitle: AxActionPane
ms:assetid: 2545d902-14ec-4790-b4e3-6669e402e22f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh608235(v=AX.60)
ms:contentKeyID: 39555624
ms.date: 04/30/2013
mtps_version: v=AX.60
---

# AxActionPane [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The AxActionPane component provides access to the actions that can be performed for the items in a page. The AxActionPane component has the same function as the [Action Pane Web Part](action-pane-web-part.md). Consider using an AxActionPane component in a User Control when you do not want to rely on having an Action Pane web part on the page where the User Control will be used.

To reference the AxActionPane in ASP.NET code for Enterprise Portal in Microsoft Dynamics AX 2012, you must include the following reference in the markup for the User Control:

    <%@ Register Assembly="Microsoft.Dynamics.Framework.Portal.SharePoint, Version=6.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
        Namespace="Microsoft.Dynamics.Framework.Portal.SharePoint.UI.WebControls" TagPrefix="dynamics" %>

To reference the AxActionPane in ASP.NET code for Enterprise Portal in Microsoft Dynamics AX 2012 R2, you must include the following reference in the markup for the User Control:

    <%@ Register Assembly="Microsoft.Dynamics.Framework.Portal.SharePoint, Version=6.2.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
        Namespace="Microsoft.Dynamics.Framework.Portal.SharePoint.UI.WebControls" TagPrefix="dynamics" %>

If you are using Enterprise Portal with SharePoint 2013, your EP Web Application Project must be set to target the .NET 4 framework to use this component.

After you have added the reference to the assembly that contains the control, you can add the control to the markup. The following ASP.NET code example shows the AxActionPane that was added to a User Control:

    <dynamics:AxActionPaneControl ID="ActionPane1" runat="server" 
        DataMember="FCMWorkOrders_Current" DataSourceID="WorkOrderListDataSource" WebMenuName="WorkOrdersActionPane"></dynamics:AxActionPaneControl>

## Properties

The AxActionPane component has the following properties:

### Subsection Heading

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
<td><p>Specifies whether the action pane is enabled.</p></td>
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
<td><p>The SkinId of the control skin that provides the skin of the control.</p></td>
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
<td><p>The table or view from the data set that is being used for the action pane.</p></td>
</tr>
<tr class="odd">
<td><p>DataSourceID</p></td>
<td><p>Specifies the AxDataSource component that will be used by the action pane to access data.</p></td>
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
<td><p>Web Menu Name</p></td>
<td><p>Specifies the Web Menu item in the AOT that defines the items displayed in the action pane.</p></td>
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
<td><p>Specifies whether the controls in the validation group specified by the <strong>ValidationGroup</strong> property will be validated when an action pane item is clicked.</p></td>
</tr>
<tr class="odd">
<td><p>EnableMenuItemHelpText</p></td>
<td><p>Not applicable for the action pane control.</p></td>
</tr>
<tr class="even">
<td><p>ValidationGroup</p></td>
<td><p>The name of the validation group for which the validation controls will be validated when an action pane item is clicked. Each validation control has a <strong>ValidationGroup</strong> property that specifies which validation group it is part of.</p></td>
</tr>
</tbody>
</table>


## Events

The AxActionPane component has the events listed in the following table.

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
<td><p>Occurs after an item in the action pane has been clicked and the action has been performed.</p></td>
</tr>
<tr class="even">
<td><p>ActionMenuItemClicking</p></td>
<td><p>Occurs after an item in the action pane has been clicked, but before the action has been performed.</p></td>
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
<td><p>Occurs before the items in the action pane are displayed, allowing the properties to be set.</p></td>
</tr>
<tr class="even">
<td><p>Unload</p></td>
<td><p>Occurs when the server control is unloaded from memory.</p></td>
</tr>
</tbody>
</table>


## Defining Action Pane Content with Code

In most cases, you define the content displayed by an action pane by using Web Menu and Web Menu Item resources in the AOT. If you need the action pane content to be more dynamic, you can define the action pane content with code you add to the User Control that displays the action pane. You do this by implementing a method that returns an IWebMenuGenerator object for the User Control. This method defines the contents of the action pane. The process to define action pane content with code is the same as the process used to define toolbar content with code. For an example of how to use the IWebMenuGenerator to define content through code, see [AxToolbar](axtoolbar.md).

