---
title: Security Process Cycles Properties
TOCTitle: Security Process Cycles Properties
ms:assetid: ea42c53f-ba46-4082-a150-8590f31ee420
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg731865(v=AX.60)
ms:contentKeyID: 35132755
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Security Process Cycles Properties 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A process cycle is a group of duties. A process cycle represents a high-level job function. The details of how a given job function is executed might change over the years, but the concept and name of that job function probably remains unchanged.

## Best Practices

This section describes the best practice rules for process cycles.

  - Each duty should be part of a process cycle.

  - Use a process cycle to organize a group of duties for a job function.

## AOT Process Cycles Hierarchy

The following list shows the hierarchy of process cycles nodes in the AOT:

  - Security
    
      - Process Cycles
        
          - YourProcessCycle
            
              - Duties

## Process Cycles Properties

This section describes the properties for the AOT node at **Security** \> **Process Cycles** \> YourProcessCycle.

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
<td><p>Name of the process cycle.</p></td>
</tr>
<tr class="even">
<td><p>Label</p></td>
<td><p>Yes</p></td>
<td><p>Text that appears on the user interface for the process cycle.</p></td>
</tr>
<tr class="odd">
<td><p>Description</p></td>
<td><p>Yes</p></td>
<td><p>Description of the process cycle.</p></td>
</tr>
<tr class="even">
<td><p>Enabled</p></td>
<td><p>Yes</p></td>
<td><p>The enable value. The value can be one of the following:</p>
<ul>
<li><p><strong>Yes</strong>. Enable the process cycle.</p></li>
<li><p><strong>No</strong>. Disable the process cycle.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Duty Properties

This section describes the properties for the AOT node at **Security** \> **Process Cycles** \> YourProcessCycle \> **Duties** \> YourDuty.

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


## See also

[Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md)

[Role-Based Security System](role-based-security-system.md)

[Role-Based Security Concepts Overview](role-based-security-concepts-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

