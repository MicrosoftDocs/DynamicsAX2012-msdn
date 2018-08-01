---
title: Security Privilege Properties
TOCTitle: Security Privilege Properties
ms:assetid: 1bc3ce9c-2c23-48d4-9dcf-8848ba2ce4ab
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg731858(v=AX.60)
ms:contentKeyID: 35132727
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Security Privilege Properties [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A privilege is a group of permissions. The nodes that are underneath each privilege node identify the securable objects that a user can access. And those nodes set the level of access for each object.

## Best Practices

This section describes the best practice rules for privileges.

  - You can use privileges to specify the access that is required to accomplish a job.

  - You can use privileges to group together the permissions for related securable objects. For example, menu items and their controls are closely related.

  - You can assign privileges directly to security roles. However, security settings are easier to maintain if you assign duties or process cycles instead of privileges.

## Securable Objects

Privileges are used to give access to securable objects. The following list shows the hierarchy under the **Security** \> **Privilages** node in the AOT:

  - Security
    
      - **Privileges**
        
          - YourPrivilege
            
              - Entry Points
            
              - Permissions
                
                  - Tables
                
                  - Server Methods
                
                  - Forms

Privileges can also override the access levels to securable objects as they are defined elsewhere in the AOT. For example, a privilege can override a permission found under **AOT** \> **Forms** \> YourForm \> **Permissions** \> **Update** \> **Tables** \> YourTable, in the **EffectiveAccess** property.

## Privilege Properties

This section describes the properties for the AOT node at **Security** \> **Privileges** \> YourPrivilege.

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
<td><p>Name of the privilege.</p></td>
</tr>
<tr class="even">
<td><p>Label</p></td>
<td><p>Yes</p></td>
<td><p>Text that appears on the user interface for the privilege.</p></td>
</tr>
<tr class="odd">
<td><p>Description</p></td>
<td><p>Yes</p></td>
<td><p>Description of the privilege.</p></td>
</tr>
<tr class="even">
<td><p>Enabled</p></td>
<td><p>Yes</p></td>
<td><p>The enable value. The value can be one of the following:</p>
<ul>
<li><p><strong>Yes</strong>. Enable the privilege.</p></li>
<li><p><strong>No</strong>. Disable the privilege.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Entry Point Properties

This section describes the properties for the AOT node at **Security** \> **Privileges** \> YourPrivilege \> **Entry Points** \> YourEntryPoint.

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
<td><p>Name of the entry point.</p></td>
</tr>
<tr class="even">
<td><p>ObjectType</p></td>
<td><p>Yes</p></td>
<td><p>Object type of the entry point. The value can be one of the following:</p>
<ul>
<li><p>MenuItemDisplay</p></li>
<li><p>MenuItemOutput</p></li>
<li><p>MenuItemAction</p></li>
<li><p>ServiceOperation</p></li>
<li><p>WebActionItem</p></li>
<li><p>WebURLItem</p></li>
<li><p>WebManagedContent</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>ObjectName</p></td>
<td><p>Yes</p></td>
<td><p>Object name of the entry point.</p></td>
</tr>
<tr class="even">
<td><p>ObjectChildName</p></td>
<td><p>Optional</p></td>
<td><p>Represents the service method name.</p>

> [!note]  
> <P>Specify the value of this property only if the <strong>ObjectType</strong> property is set to <strong>ServiceOperation</strong>.</P>

</td>
</tr>
<tr class="odd">
<td><p>AccessLevel</p></td>
<td><p>Yes</p></td>
<td><p>Permission value for all object types except <strong>ServiceOperation</strong>. The value can be one of the following:</p>
<ul>
<li><p>Read</p></li>
<li><p>Update</p></li>
<li><p>Create</p></li>
<li><p>Correct</p></li>
<li><p>Delete</p></li>
<li><p>NoAccess</p></li>
</ul>
<p>The permission values for the <strong>AccessLevel</strong> property represent a hierarchy. <strong>Read</strong> is the weakest permission, and <strong>Delete</strong> is the strongest. <strong>Delete</strong> permission includes every other permission. <strong>Create</strong> permission includes <strong>Update</strong> and <strong>Read</strong>. You can set the permission value to <strong>NoAccess</strong> to prevent all access to the entry point.</p>
<p>The <strong>Correct</strong> permission applies only when a time state table is involved. This permission authorizes you to issue update records in a time state table.</p>
<p>If instead the object type is <strong>ServiceOperation</strong>, the value can be one of the following:</p>
<ul>
<li><p><strong>Invoke</strong>. The server method can be called.</p></li>
<li><p><strong>NoAccess</strong>. The server method cannot be called.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Table Properties

This section describes the properties for the AOT node at **Security** \> **Privileges** \> YourPrivilege \> **Permissions** \> **Tables** \> YourTable.

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
<td><p>Name of the table.</p></td>
</tr>
<tr class="even">
<td><p>EffectiveAccess</p></td>
<td><p>Yes</p></td>
<td><p>Permission value. The value can be one of the following:</p>
<ul>
<li><p>Read</p></li>
<li><p>Update</p></li>
<li><p>Create</p></li>
<li><p>Correct</p></li>
<li><p>Delete</p></li>
<li><p>NoAccess</p></li>
</ul>
<p>The permission values for the <strong>EffectiveAccess</strong> property represent a hierarchy. <strong>Read</strong> is the weakest permission, and <strong>Delete</strong> is the strongest. <strong>Delete</strong> permission includes every other permission. <strong>Create</strong> permission includes <strong>Update</strong> and <strong>Read</strong>.</p>
<p>The <strong>Correct</strong> permission applies only when a time state table is involved. This permission authorizes you to update records in a time state table.</p>
<p>You can set the permission value to <strong>NoAccess</strong> to prevent all access to the table.</p></td>
</tr>
<tr class="odd">
<td><p>ManagedBy</p></td>
<td><p>Optional</p></td>
<td><p>This property is for use by automation tools.</p></td>
</tr>
</tbody>
</table>


## Server Method Properties

This section describes the properties for the AOT node at **Security** \> **Privileges** \> YourPrivilege \> **Permissions** \> **Server Methods** \> YourServerMethod.

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
<td><p>Name of the server class.</p></td>
</tr>
<tr class="even">
<td><p>Method</p></td>
<td><p>Yes</p></td>
<td><p>Name of the secure server method that is tagged with the <strong>SysEntryPointAttribute</strong> attribute.</p></td>
</tr>
<tr class="odd">
<td><p>EffectiveAccess</p></td>
<td><p>Yes</p></td>
<td><p>Permission value. The value can be one of the following:</p>
<ul>
<li><p><strong>Invoke</strong>. The server method can be called.</p></li>
<li><p><strong>NoAccess</strong>. The server method cannot be called.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ManagedBy</p></td>
<td><p>Optional</p></td>
<td><p>This property is for use by automation tools.</p></td>
</tr>
</tbody>
</table>


## Form Properties

This section describes the properties for the AOT node at **Security** \> **Privileges** \> YourPrivilege \> **Permissions** \> **Forms** \> YourForm.

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
<td><p>Name of the form.</p></td>
</tr>
</tbody>
</table>


## See also

[Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md)

[Role-Based Security System](role-based-security-system.md)

[Security Node in the AOT](https://msdn.microsoft.com/en-us/library/gg731863\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

