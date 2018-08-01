---
title: AxEnhancedPreview
TOCTitle: AxEnhancedPreview
ms:assetid: afe2cc05-f13d-45ec-ad34-af351167eb6b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh812512(v=AX.60)
ms:contentKeyID: 44090298
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# AxEnhancedPreview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The AxEnhancedPreview is used to display a small preview window when the pointer hovers over a control or group of controls. You must manually add this component to the markup for the User Control. The following ASP.NET code example shows the AxEnhancedPreview that was added to a User Control:

    <dynamics:AxEnhancedPreview ID="EnhancedPreview1" runat="server" Enabled="true" 
        Url="http://www.contoso.com" Height="200" Width="400">
        <asp:TextBox ID="TextBox1" runat="server" Width="117px"></asp:TextBox>
        <asp:TextBox ID="TextBox2" runat="server" Width="117px"></asp:TextBox>
        <asp:Button ID="Button1" runat="server" onclick="Button1_Click" 
            Text="Web" />
    </dynamics:AxEnhancedPreview>

When the pointer hovers over any of the three components that are enclosed in the preview definition, the preview is displayed.

## Properties

The AxEnhancedPreview component has the following properties:

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
<td><p>The keyboard shortcut used by the control. Not used for Enterprise Portal.</p></td>
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
<td><p>Specifies whether the control is enabled.</p></td>
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
<td><p>The programmatic name of the control.</p></td>
</tr>
<tr class="even">
<td><p>Height</p></td>
<td><p>The height of the preview.</p></td>
</tr>
<tr class="odd">
<td><p>ShowBullet</p></td>
<td><p>Indicates whether a set of bullet characters is displayed next to the control as the preview is prepared for display.</p></td>
</tr>
<tr class="even">
<td><p>URL</p></td>
<td><p>The complete URL of the content to display in the preview.</p></td>
</tr>
<tr class="odd">
<td><p>Width</p></td>
<td><p>The width of the preview.</p></td>
</tr>
</tbody>
</table>

