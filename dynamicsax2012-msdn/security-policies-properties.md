---
title: Security Policies Properties
TOCTitle: Security Policies Properties
ms:assetid: 0d917cf8-ce88-4c7e-8e41-f678d0fa29bd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg731857(v=AX.60)
ms:contentKeyID: 35132724
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Security Policies Properties 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Developers and system administrators can create security policies to deny access to subset of data records in tables.

## Constrained Tables of a Policy

You can add tables and views under the **Constrained Tables** node of a security policy in the AOT. These tables and views relate to the data source table of the query that is named in the **Query** property of the policy. The following list shows the hierarchy of security policy nodes in the AOT:

  - Security
    
      - Policies
        
          - YourPolicy
            
              - Constrained Tables
                
                  - YourConstrainedTable
                    
                      - YourConstrainedSubTable
                
                  - YourConstrainedView

Each **Constrained Tables** node can contain any number of constrained tables and views. And each constrained table can contain any number of constrained sub-tables.

## Security Policy Properties

The following table describes the properties for the AOT node at **Security** \> **Policies** \> YourPolicy.

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
<td><p>The name of the security policy.</p></td>
</tr>
<tr class="even">
<td><p>Label</p></td>
<td><p>Yes</p></td>
<td><p>The text that appears on the user interface for the security policy.</p></td>
</tr>
<tr class="odd">
<td><p>PrimaryTable</p></td>
<td><p>Yes</p></td>
<td><p>The table that is specified in the data source for the security policy query.</p></td>
</tr>
<tr class="even">
<td><p>Query</p></td>
<td><p>Yes</p></td>
<td><p>The query which is used by the policy to filter data from the constrained tables that are specified in the policy.</p></td>
</tr>
<tr class="odd">
<td><p>UseNotExistJoin</p></td>
<td><p>Yes</p></td>
<td><p>Indicates whether the security query must be applied as a not exists join or as an exists join.</p></td>
</tr>
<tr class="even">
<td><p>PolicyGroup</p></td>
<td><p>No</p></td>
<td><p>The <strong>PolicyGroup</strong> property is set by a drop-down list that contains the security policy group names that the system administrator has created.</p>
<p>The system administrator or developer can create security policy groups. This property can be used by administrators and developers to quickly identify groups of related security policies. The system does not use this property during run time.</p></td>
</tr>
<tr class="odd">
<td><p>ConstrainedTable</p></td>
<td><p>Yes</p></td>
<td><p>Controls whether the security policy restricts the data values in records that are returned from the primary table. The value can be one of the following:</p>
<ul>
<li><p><strong>Yes</strong> – The security policy is enforced on the primary table.</p></li>
<li><p><strong>No</strong> – The security policy is not enforced on the primary table.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Enabled</p></td>
<td><p>Yes</p></td>
<td><p>Controls whether the policy is enforced by the system during run time. The value can be one of the following:</p>
<ul>
<li><p><strong>Yes</strong> – Enable the security policy.</p></li>
<li><p><strong>No</strong> – Disable the security policy.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Operation</p></td>
<td><p>Yes</p></td>
<td><p>Controls which data operations the policy is enforced for. The value can be one of the following:</p>
<ul>
<li><p>Select</p></li>
<li><p>Insert</p></li>
<li><p>Update</p></li>
<li><p>Delete</p></li>
<li><p>Insert, Update and Delete</p></li>
<li><p>All operations</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ContextType</p></td>
<td><p>Yes</p></td>
<td><p>Controls the context type of the security policy. The value can be one of the following:</p>
<ul>
<li><p><strong>ContextString</strong> – Indicates that you have to specify a value for the <strong>ContextString</strong> property. The security policy uses a specific application context for the policy.</p></li>
<li><p><strong>RoleName</strong> – Indicates that the security policy is only applied to the application user assigned to the value of <strong>RoleName</strong>.</p></li>
<li><p><strong>RoleProperty</strong> – This value is used in combination with the <strong>ContextString</strong> property to specify multiple roles context.</p>
<p>For more information, see <a href="https://msdn.microsoft.com/en-us/library/gg958698(v=ax.60)">XDSServices.setXDSContext Method</a>.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>ContextString</p></td>
<td><p>Yes</p></td>
<td><p>This property works in combination with <strong>ContextType</strong> property. It can specify an application or multiple roles context.</p></td>
</tr>
</tbody>
</table>


## See also

[Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

