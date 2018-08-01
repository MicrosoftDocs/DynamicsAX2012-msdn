---
title: Security Duty Properties
TOCTitle: Security Duty Properties
ms:assetid: bfc712a2-83b8-4488-b368-6dbb9189d32e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg731862(v=AX.60)
ms:contentKeyID: 35132747
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Security Duty Properties [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, security permissions are combined into privileges, and privileges are combined into duties. Duties are defined as a group of related privileges that provide a user with access to a specific business function. In the application object tree (AOT), these privileges are organized into the nodes of a duty.

## Best Practices

This section describes the best practice rules for duties.

  - All duties should be assigned to a role.

  - All duties should be part of a process cycle.

  - Because a duty represents a specific business function the name of the duty should rarely or never change. For example, your company pays bills. The details of how you pay bills may change but the essential function of paying bills will not change. Instead of creating a new duty you should change the privilege subnodes of the duty.

  - The name of a process cycle should rarely or never change.

## AOT Duty Hierarchy

The following list shows the hierarchy of duty nodes in the AOT:

  - Security
    
      - Duties
        
          - YourDuty
            
              - Privileges

## Duty Properties

This section describes the properties for the AOT node at **Security** \> **Duties** \> YourDuty.

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
<td><p>Name of the duty.</p></td>
</tr>
<tr class="even">
<td><p>Label</p></td>
<td><p>Yes</p></td>
<td><p>Text that appears on the user interface for the duty.</p></td>
</tr>
<tr class="odd">
<td><p>Description</p></td>
<td><p>Yes</p></td>
<td><p>Description of the duty.</p></td>
</tr>
<tr class="even">
<td><p>Enabled</p></td>
<td><p>Yes</p></td>
<td><p>The enable value. The value can be one of the following:</p>
<ul>
<li><p><strong>Yes</strong>. Enable the duty.</p></li>
<li><p><strong>No</strong>. Disable the duty.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Privilege Properties

This section describes the properties for the AOT node at **Security** \> **Duties** \> YourDuty \> **Privileges** \> YourPrivilege.

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


## See also

[Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md)

[Role-Based Security System](role-based-security-system.md)

[Role-Based Security Concepts Overview](role-based-security-concepts-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

