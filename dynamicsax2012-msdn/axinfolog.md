---
title: AxInfoLog
TOCTitle: AxInfoLog
ms:assetid: de046eaf-3767-4b42-8a82-0d80bcb1e4e7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc639851(v=AX.60)
ms:contentKeyID: 28119505
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# AxInfoLog [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The AxInfoLog component displays important information for the user, such as status and error information for actions that are performed on a page. It is used when you create pages for the ASP.NET test environment. It is automatically included on the Default.aspx page that is part of a Microsoft Dynamics AX Web Application project.

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
<td><p>WebPart Role</p></td>
<td><p>Specifies whether the web part is a provider or consumer in web part communication for the page. Not used for Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>Update Mode</p></td>
<td><p>When connected to another web part, specifies when the content of the web part will be updated. The value can be <strong>Conditional</strong> or <strong>Always</strong>. If it is set to <strong>Conditional</strong>, the content of the web part is updated only when the context changes. When set to <strong>Always</strong>, the web part will be updated even when the context has not changed. Not used for Enterprise Portal.</p></td>
</tr>
</tbody>
</table>


## See also

[How to: Test User Controls in Visual Studio](how-to-test-user-controls-in-visual-studio.md)

