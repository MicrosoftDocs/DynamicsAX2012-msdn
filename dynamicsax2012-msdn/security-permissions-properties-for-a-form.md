---
title: Security Permissions Properties for a Form
TOCTitle: Security Permissions Properties for a Form
ms:assetid: c2423d18-5d3a-4b49-84c2-c830dde86649
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg879980(v=AX.60)
ms:contentKeyID: 35250111
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Security Permissions Properties for a Form [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic lists and describes the permission related properties that exist on subnodes under the **Permissions** node under the node for each form in the AOT. These property values interact with other properties that are set under the **AOT** \> **Security** node. These values also interact with permission related properties under other high-level nodes such as **AOT** \> **Menu Items**.

For an example of interaction between security settings, consider a menu item. Suppose you create YourMenuItem at **AOT** \> **Menu Items** \> **Display**. There you assign values to security properties, such as the **ReadPermissions** and **UpdatePermissions** properties. Then you can assign the menu item as a node under **AOT** \> **Security** \> **Privilege** \> ImportantPrivilege \> **Entry Points**. The assignment of the menu item adds the security settings of the menu item to ImportantPrivilege.

On the **Entry Point** \> YourMenuItem node, you can use the **AccessLevel** property to choose which set of permissions to receive from the menu item into the privilege.

## Permission Group Nodes under Forms in the AOT

The following list shows the position of the **Permissions** node under the **Forms** node in the AOT:

  - Forms
    
      - YourForm
        
          - Permissions
            
              - Read
                
                  - Controls
                
                  - Tables
                
                  - Server Methods
                
                  - Associated Forms
            
              - Update
            
              - Create
            
              - Correct (disabled by default)
            
              - Delete

The nodes at the level of **Read** through **Delete** contain many individual permissions. The **Read** and **Delete** nodes can be referred to as permission group nodes.

All of the permission group nodes contains the same subnodes that are shown under the **Read** node.

## NeededPermission Property of a Control

This section describes the **NeededPermission** property for the AOT node at **Forms** \> YourForm \> **Designs** \> **Design** \> YourControl. The value can be one of the following:

  - None

  - Read

  - Update

  - Create

  - Correct

  - Delete

  - Manual

The values for the **NeededPermission** property represent a hierarchy. **Read** is the weakest permission, and **Delete** is the strongest. **Read** is included by **Update**, and **Update** is included by **Create**. Therefore **Read** is also included by **Create** permission.

To see a particular control on a form, the user must have a permission to the control that is at least as strong as the permission the control requires. For example, suppose a control has its **NeededPermission** property set to **Update**. A user who has only **Read** permission does not see the control on the form. But the control is visible to another user who has **Update** or **Delete** permission to the control.

Through [automatic inference](automatic-inference-of-permissions-in-aot-security.md) the system inserts a subnode representing the control, under the appropriate permission group nodes in the AOT. This occurs when you specify a value for the **NeededPermission** property of the control.

### ![Gg879980.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg879980.collapse_all(en-us,AX.60).gif")Special Values for NeededPermission

The following table describes the special values that can be assigned to the **NeededPermission** property of a control.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>NeededPermission value</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Manual</strong></p></td>
<td><p>When you specify <strong>Manual</strong> for the <strong>NeededPermission</strong> property, the automatic inference system does not add a node representing the control as a subnode under the permission group nodes in the AOT. You can insert the control subnode manually under the permission group nodes.</p></td>
</tr>
<tr class="even">
<td><p><strong>None</strong></p></td>
<td><p>When you specify <strong>Manual</strong> for the <strong>NeededPermission</strong> property, the automatic inference system does not add a node representing the control as a subnode under the permission group nodes in the AOT. You can set the <strong>NeededPermission</strong> value to <strong>None</strong> to enable access to the control without any restrictions.</p>
<p>Suppose a control was manually added to a permission group. Later you set the <strong>NeededPermission</strong> property of the control to <strong>None</strong>. In this scenario the node representing the control is not automatically removed from the permission group. When you compile the form an error message similar to the following is generated:</p>
<p>NeededPermission property on control ControlName is set to none.</p></td>
</tr>
</tbody>
</table>


## Control Properties

This section describes the properties for the AOT node at **Forms** \> YourForm \> **Permissions** \> **Read** \> **Controls** \> YourControl. The descriptions of the properties for the **Read** node apply to **Update**, **Create**, and **Delete** nodes.

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
<td><p>Control</p></td>
<td><p>Yes</p></td>
<td><p>The name of the control.</p></td>
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
<p>You can set the permission value to <strong>NoAccess</strong> to prevent all access to the control provided that no other entry point, privilege, or role grants access to the control.</p></td>
</tr>
<tr class="odd">
<td><p>SystemManaged</p></td>
<td><p>Yes</p></td>
<td><p>Indicates whether this permission was added through automatic inference. The value can be one of the following:</p>
<ul>
<li><p><strong>Yes</strong>. This permission was added through automatic inference.</p></li>
<li><p><strong>No</strong>. This permission was created manually or overridden.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ManagedBy</p></td>
<td><p>Optional</p></td>
<td><p>This property is for use by automation tools.</p></td>
</tr>
</tbody>
</table>


## Table Properties

This section describes the properties for the AOT node at **Forms** \> YourForm \> **Permissions** \> **Read** \> **Tables** \> YourTable. The descriptions of the properties for the **Read** node apply to **Update**, **Create**, and **Delete** permission group nodes.

Suppose you create a data source node for a table under your form node. The system uses automatic inference to add a node representing the table under the appropriate permission group nodes. When you remove your data source, the system removes the table subnode from the permission nodes.

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
<td><p>ManagedBy</p></td>
<td><p>Optional</p></td>
<td><p>This property is for use by automation tools.</p></td>
</tr>
</tbody>
</table>


## Server Method Properties

This section describes the properties for the AOT node at **Forms** \> YourForm \> **Permissions** \> **Read** \> **Server Methods** \> YourServerMethod. The descriptions of the properties for the **Read** node apply to **Update**, **Create**, and **Delete** nodes.

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
<td><p>The name of the secure server method that is tagged with the <strong>SysEntryPointAttribute</strong> attribute.</p></td>
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
<td><p>This property is for use by automation tools.</p></td>
</tr>
</tbody>
</table>


## Associated Form Properties

This section describes the properties for the AOT node at **Forms** \> YourForm \> **Permissions** \> **Read** \> **Associated Forms** \> YourAssociatedForm. The descriptions of the properties for the **Read** node apply to **Update**, **Create**, and **Delete** nodes.

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
<tr class="even">
<td><p>AccessLevel</p></td>
<td><p>Yes</p></td>
<td><p>The permission value. This field can contain one of the following values:</p>
<ul>
<li><p>Read</p></li>
<li><p>Update</p></li>
<li><p>Create</p></li>
<li><p>Correct</p></li>
<li><p>Delete</p></li>
<li><p>NoAccess</p></li>
</ul>
<p>The permission values for the <strong>EffectiveAccess</strong> property represent a hierarchy. <strong>Read</strong> is the weakest permission, and <strong>Delete</strong> is the strongest. <strong>Delete</strong> permission includes every other permission. <strong>Create</strong> permission includes <strong>Update</strong> and <strong>Read</strong>. You can set the permission value to <strong>NoAccess</strong> to prevent all access to the form.</p></td>
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
<td><p>This property is for use by automation tools.</p></td>
</tr>
</tbody>
</table>


## See also

[Security Permissions for Securable Objects in the AOT](security-permissions-for-securable-objects-in-the-aot.md)

[How to: Use Associated Forms Permissions](how-to-use-associated-forms-permissions.md)

[Automatic Inference of Permissions in AOT Security](automatic-inference-of-permissions-in-aot-security.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

