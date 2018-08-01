---
title: Security Permissions Properties for an Info Part
TOCTitle: Security Permissions Properties for an Info Part
ms:assetid: e68ec434-5869-4ae6-aa28-dbf6c46a57e3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg848022(v=AX.60)
ms:contentKeyID: 35253220
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Security Permissions Properties for an Info Part [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic lists and describes the many permission related properties that exist on subnodes under the **Permissions** node under the **Parts** \> **Info Parts** node in the AOT.

In Microsoft Dynamics AX an info part is a specialized type of control that you use to define a **FactBox**. For more information, see [Parts](parts.md).

## Info Parts Permissions Node in the AOT

The following list shows the position of the **Permissions** node under the **Parts** node in the AOT:

  - Parts
    
      - Info Parts
        
          - YourInfoPart
            
              - Permissions
                
                  - Tables
                
                  - Server Methods

## Table Properties

This section describes the properties for the AOT node at **Parts** \> **Info Parts** \> YourInfoPart \> **Permissions** \> **Tables** \> YourTable.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Required</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Table</p></td>
<td><p>Yes</p></td>
<td><p>The name of the table.</p></td>
</tr>
<tr class="even">
<td><p>EffectiveAccess</p></td>
<td><p>Yes</p></td>
<td><p>The permission value. The value can be one of the following:</p>
<ul>
<li><p>Read</p></li>
<li><p>Update</p></li>
<li><p>Create</p></li>
<li><p>Correct</p></li>
<li><p>Delete</p></li>
<li><p>NoAccess</p></li>
</ul>
<p>The permission values for the <strong>EffectiveAccess</strong> property represent a hierarchy. <strong>Read</strong> is the weakest permission, and <strong>Delete</strong> is the strongest. <strong>Delete</strong> permission includes every other permission. <strong>Create</strong> permission includes <strong>Update</strong> and <strong>Read</strong>.</p>
<p>You can set the permission value to <strong>NoAccess</strong> to prevent all access to the table.</p></td>
</tr>
<tr class="odd">
<td><p>SystemManaged</p></td>
<td><p>Yes</p></td>
<td><p>Indicates whether this permission was added through automatic inference. The value can be one of the following:</p>
<ul>
<li><p><strong>Yes</strong>. This permission was added through automatic inference.</p></li>
<li><p><strong>No</strong>. This permission was created manually.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ManagedBy</p></td>
<td><p>Optional</p></td>
<td><p>This property is reserved for use by automation tools.</p></td>
</tr>
</tbody>
</table>


## Server Method Properties

This section describes the properties for the AOT node at **Parts** \> **Info Parts** \> YourInfoPart \> **Permissions** \> **Server Methods** \> YourServerMethod.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Required</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Class</p></td>
<td><p>Yes</p></td>
<td><p>The name of the server class.</p></td>
</tr>
<tr class="even">
<td><p>Method</p></td>
<td><p>Yes</p></td>
<td><p>The name of the secure server method tagged with the <strong>SysEntryPointAttribute</strong> attribute.</p></td>
</tr>
<tr class="odd">
<td><p>EffectiveAccess</p></td>
<td><p>Yes</p></td>
<td><p>The permission value. The value can be one of the following:</p>
<ul>
<li><p><strong>Invoke</strong>. The server method can be called.</p></li>
<li><p><strong>NoAccess</strong>. The server method cannot be called.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>SystemManaged</p></td>
<td><p>Yes</p></td>
<td><p>Indicates whether this permission was added through automatic inference. The value can be one of the following:</p>
<ul>
<li><p><strong>Yes</strong>. This permission was added through automatic inference.</p></li>
<li><p><strong>No</strong>. This permission was created manually.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>ManagedBy</p></td>
<td><p>Optional</p></td>
<td><p>This property is reserved for use by automation tools.</p></td>
</tr>
</tbody>
</table>


## See also

[Security Permissions for Securable Objects in the AOT](security-permissions-for-securable-objects-in-the-aot.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

