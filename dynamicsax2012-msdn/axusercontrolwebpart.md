---
title: AxUserControlWebPart
TOCTitle: AxUserControlWebPart
ms:assetid: f4bddd5e-7252-4817-b4ee-111037572299
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc654080(v=AX.60)
ms:contentKeyID: 28119518
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# AxUserControlWebPart 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The AxUserControlWebPart component displays a User Control in an ASP.NET page. It is used when you create pages for the ASP.NET test environment. It is automatically included on the Default.aspx page that is part of a Microsoft Dynamics AX Web Application project. To add more AxUserControlWebPart components to an .ASP.NET page, you would add code such as this to the markup:

    <dynamics:AxUserControlWebPart ID="AxUserControlWebPart1" runat="server" 
              ManagedContentItem="WorkOrderDetails" />

## Microsoft Dynamics AX Properties

The following properties specific to Microsoft Dynamics AX are available for this web part.

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
<td><p>Default Title</p></td>
<td><p>Specifies the default title for the web part.</p></td>
</tr>
<tr class="even">
<td><p>Managed Web Content Item</p></td>
<td><p>The name of the Web Control (an item in the <strong>Web</strong> &gt; <strong>Web Content</strong> &gt; <strong>Managed</strong> node of the AOT) that will be displayed in the web part.</p></td>
</tr>
<tr class="odd">
<td><p>WebPart Role</p></td>
<td><p>Specifies whether the User Control web part is a provider or consumer in web part communication for the page.</p></td>
</tr>
<tr class="even">
<td><p>Update Mode</p></td>
<td><p>When connected to another web part, specifies when the content of the web part will be updated. The value can be <strong>Conditional</strong> or <strong>Always</strong>. If it is set to <strong>Conditional</strong>, the content of the web part is updated only when the context changes. When set to <strong>Always</strong>, the web part will be updated even when the context has not changed.</p></td>
</tr>
</tbody>
</table>


## See also

[How to: Test User Controls in Visual Studio](how-to-test-user-controls-in-visual-studio.md)

