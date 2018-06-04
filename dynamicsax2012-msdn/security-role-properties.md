---
title: Security Role Properties
TOCTitle: Security Role Properties
ms:assetid: b09428c4-2f5e-4b63-bcff-1ab43bced2b9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg731861(v=AX.60)
ms:contentKeyID: 35132741
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Security Role Properties 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, roles represent a collection of permissions, which can be granted to users. The nodes that are nested underneath each role node identify various securable objects that a user can access. And the nested nodes specify the level of access.

## Role Node in the AOT

Roles are used to give access to securable objects. The following list shows the hierarchy of role nodes in the AOT:

  - Security
    
      - Roles
        
          - YourRole
            
              - Duties
            
              - Privileges
            
              - Permissions
                
                  - Tables
                
                  - Forms
                
                  - Server Methods
            
              - Sub Roles

Roles are typically associated with security duties, and sometimes, security privileges. Access levels to securable objects within a role are derived from the duties, privileges, or both. Roles can also override the access levels to securable objects under the **Permissions** node.

## Role Properties

This section describes the properties for the AOT node at **Security** \> **Roles** \> YourRole.

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
<td><p>Name</p></td>
<td><p>Yes</p></td>
<td><p>The name of the role.</p></td>
</tr>
<tr class="even">
<td><p>Label</p></td>
<td><p>Yes</p></td>
<td><p>The text that appears on the user interface for the role.</p></td>
</tr>
<tr class="odd">
<td><p>Description</p></td>
<td><p>Yes</p></td>
<td><p>The description of the role.</p></td>
</tr>
<tr class="even">
<td><p>Enabled</p></td>
<td><p>Yes</p></td>
<td><p>The enable value. This field can contain one of these values:</p>
<ul>
<li><p>Yes. Enable the role.</p></li>
<li><p>No. Disable the role.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>PastDataAccess</p></td>
<td><p>Yes</p></td>
<td><p>Specifies the past data access for the tables with date effective fields. The value can be one of the following:</p>
<ul>
<li><p>Read</p></li>
<li><p>Update</p></li>
<li><p>Create</p></li>
<li><p>Correct</p></li>
<li><p>Delete</p></li>
<li><p>NoAccess</p></li>
</ul>
<p>The permission values for the <strong>PastDataAccess</strong> property represent a hierarchy. <strong>Read</strong> is the weakest permission, and <strong>Delete</strong> is the strongest. <strong>Delete</strong> permission includes every other permission. <strong>Create</strong> permission includes <strong>Update</strong> and <strong>Read</strong>. You can set the permission value to <strong>NoAccess</strong> to prevent all access to the table.</p></td>
</tr>
<tr class="even">
<td><p>CurrentDataAccess</p></td>
<td><p>Yes</p></td>
<td><p>Specifies the current data access for the tables with date effective fields.</p></td>
</tr>
<tr class="odd">
<td><p>FutureDataAccess</p></td>
<td><p>Yes</p></td>
<td><p>Specifies the future data access for the tables with date effective fields.</p></td>
</tr>
<tr class="even">
<td><p>ContextString</p></td>
<td><p>Optional</p></td>
<td><p>A user-defined string that can be used by security policies.</p></td>
</tr>
</tbody>
</table>


## Duty Properties

This section describes the properties for the AOT node at **Security** \> **Roles** \> **Duties** \> YourDuty.

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
<td><p>Name</p></td>
<td><p>Yes</p></td>
<td><p>The name of the duty.</p></td>
</tr>
<tr class="even">
<td><p>Enabled</p></td>
<td><p>Yes</p></td>
<td><p>The enable value. The value can be one of the following:</p>
<ul>
<li><p><strong>Yes</strong>. Enables the duty.</p></li>
<li><p><strong>No</strong>. Disables the duty.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Privilege Properties

This section describes the properties for the AOT node at **Security** \> **Roles** \> **Privileges** \> YourPrivilege.

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
<td><p>Name</p></td>
<td><p>Yes</p></td>
<td><p>The name of the privilege.</p></td>
</tr>
<tr class="even">
<td><p>Enabled</p></td>
<td><p>Yes</p></td>
<td><p>The enable value. The value can be one of the following:</p>
<ul>
<li><p><strong>Yes</strong>. Enables the privilege.</p></li>
<li><p><strong>No</strong>. Disables the privilege.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Table Properties

This section describes the properties for the AOT node at **Security** \> **Roles** \> **Permissions** \> **Tables** \> YourTable.

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
<p>The permission values for the <strong>EffectiveAccess</strong> property represent a hierarchy. <strong>Read</strong> is the weakest permission, and <strong>Delete</strong> is the strongest. <strong>Delete</strong> permission includes every other permission. <strong>Create</strong> permission includes <strong>Update</strong> and <strong>Read</strong>. You can set the permission value to <strong>NoAccess</strong> to prevent all access to the table.</p></td>
</tr>
<tr class="odd">
<td><p>ManagedBy</p></td>
<td><p>Optional</p></td>
<td><p>This property is reserved for use by automation tools.</p></td>
</tr>
</tbody>
</table>


## Form Properties

This section describes the properties for the AOT node at **Security** \> **Roles** \> **Permissions** \> **Form** \> YourForm.

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
<td><p>Form</p></td>
<td><p>Yes</p></td>
<td><p>The name of the form.</p></td>
</tr>
</tbody>
</table>


## Server Method Properties

This section describes the properties for the AOT node at **Security** \> **Roles** \> **Permissions** \> **Server Methods** \> YourServerMethod.

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
<td><p>ManagedBy</p></td>
<td><p>Optional</p></td>
<td><p>This property is reserved for use by automation tools.</p></td>
</tr>
</tbody>
</table>


## Sub Role Properties

This section describes the properties for the AOT node at **Security** \> **Roles** \> **Sub Roles** \> YourSubRole.

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
<td><p>Name</p></td>
<td><p>Yes</p></td>
<td><p>The name of the subrole.</p></td>
</tr>
<tr class="even">
<td><p>Enabled</p></td>
<td><p>Yes</p></td>
<td><p>The enable value. The value can be one of the following:</p>
<ol>
<li><p><strong>Yes</strong>. Enables the subrole.</p></li>
<li><p><strong>No</strong>. Disables the subrole.</p></li>
</ol></td>
</tr>
</tbody>
</table>


## See also

[Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md)

[Role-Based Security System](role-based-security-system.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

