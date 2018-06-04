---
title: Security Code Permission Properties
TOCTitle: Security Code Permission Properties
ms:assetid: dfafb422-f192-442b-8bb6-08f52a1e1fc9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg731864(v=AX.60)
ms:contentKeyID: 35132753
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Security Code Permission Properties 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A code permission is a group of permissions that are associated with a menu item or a service operation. When a security role has access to a menu item, the role also has access to other AOT items that are mentioned within the code permission for the menu item. The degree of access is controlled by the particular permissions that are defined under the code permission node.

## Securable Objects

Code permissions are used to give access to securable objects. The following list shows the hierarchy of code permission nodes in the AOT:

  - Security
    
      - Code Permissions
        
          - YourCodePermission
            
              - Tables
            
              - Server Methods
            
              - Associated Objects
                
                  - Forms
                
                  - Web Controls
                
                  - Reports

Code permissions can also override the access levels to securable objects under the **Associated Objects** node.

## Code Permission Properties

This section describes the properties for the AOT node at **Security** \> **Code Permissions** \> YourCodePermission.

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
<td><p>Name of the code permission. The code permission allows users to execute the class method that is specified in <strong>Method</strong> property.</p></td>
</tr>
<tr class="even">
<td><p>Class</p></td>
<td><p>Optional</p></td>
<td><p>Class that is associated with this code permission.</p></td>
</tr>
<tr class="odd">
<td><p>Method</p></td>
<td><p>Optional</p></td>
<td><p>Method that is associated with this code permission.</p></td>
</tr>
</tbody>
</table>


## Table Properties

This section describes the properties for the AOT node at **Security** \> **Code Permissions** \> YourCodePermission \> **Tables** \> YourTable.

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

This section describes the properties for the AOT node at **Security** \> **Code Permissions** \> YourCodePermission \> **Server Methods** \> YourServerMethod.

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
<td><p>The secure server method that is tagged with the <strong>SysEntryPointAttribute</strong> attribute.</p></td>
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

This section describes the properties for the AOT node at **Security** \> **Code Permissions** \> YourCodePermission \> **Associated Objects** \> **Forms** \> YourForm.

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
<tr class="even">
<td><p>AccessLevel</p></td>
<td><p>Yes</p></td>
<td><p>Permission value. This field can contain one of the following values:</p>
<ul>
<li><p>Read</p></li>
<li><p>Update</p></li>
<li><p>Create</p></li>
<li><p>Correct</p></li>
<li><p>Delete</p></li>
<li><p>NoAccess</p></li>
</ul>
<p>The permission values for the <strong>EffectiveAccess</strong> property represent a hierarchy. <strong>Read</strong> is the weakest permission, and <strong>Delete</strong> is the strongest. <strong>Delete</strong> permission includes every other permission. <strong>Create</strong> permission includes <strong>Update</strong> and <strong>Read</strong>.</p>
<p>You can set the permission value to <strong>NoAccess</strong> to prevent all access to the form.</p></td>
</tr>
<tr class="odd">
<td><p>ManagedBy</p></td>
<td><p>Optional</p></td>
<td><p>This property is for use by automation tools.</p></td>
</tr>
</tbody>
</table>


## Web Control Properties

This section describes the properties for the AOT node at **Security** \> **Code Permissions** \> YourCodePermission \> **Associated Objects** \> **Web Controls** \> YourWebControl.

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
<td><p>WebControl</p></td>
<td><p>Yes</p></td>
<td><p>Name of the web control.</p></td>
</tr>
<tr class="even">
<td><p>AccessLevel</p></td>
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
<p>You can set the permission value to <strong>NoAccess</strong> to prevent all access to the web control.</p></td>
</tr>
<tr class="odd">
<td><p>ManagedBy</p></td>
<td><p>Optional</p></td>
<td><p>This property is for use by automation tools.</p></td>
</tr>
</tbody>
</table>


## Report Properties

This section describes the properties for the AOT node at **Security** \> **Code Permissions** \> YourCodePermission \> **Associated Objects** \> **Reports** \> YourReport.

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
<td><p>Name of the report design.</p></td>
</tr>
<tr class="even">
<td><p>Report</p></td>
<td><p>Yes</p></td>
<td><p>Full name of the report.</p></td>
</tr>
<tr class="odd">
<td><p>ManagedBy</p></td>
<td><p>Optional</p></td>
<td><p>This property is for use by automation tools.</p></td>
</tr>
</tbody>
</table>


## See also

[Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md)

[Role-Based Security System](role-based-security-system.md)

[Walkthrough: Creating a Code Permission under AOT Security](walkthrough-creating-a-code-permission-under-aot-security.md)

[Walkthrough: Design Permissions for a Form that is Started from a Menu Item](walkthrough-design-permissions-for-a-form-that-is-started-from-a-menu-item.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

