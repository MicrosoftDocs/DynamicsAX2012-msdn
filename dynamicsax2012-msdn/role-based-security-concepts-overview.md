---
title: Role-Based Security Concepts Overview
TOCTitle: Role-Based Security Concepts Overview
ms:assetid: cababef1-5b4f-4d40-b7e5-242e723da4f7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg880983(v=AX.60)
ms:contentKeyID: 35251374
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Role-Based Security Concepts Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX role-based security system restricts system access to authorized users. You can create security roles to represent various job functions. A defined set of application access privileges is assigned to specific roles. Users can be assigned to one or more security roles and through those role assignments acquire the permissions to perform particular system functions.

You can use privileges to group together securable objects, such as entry points and permissions for tables, forms and server methods. You can further combine privileges into duties and duties into process cycles. A duty is a set of application access privileges that are required for a user to carry out their responsibilities. A process cycle is a collection of duties that represent a higher level business process.

The following table summarizes role-based security system concept definitions.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Concept</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Security role</p></td>
<td><ul>
<li><p>Security roles represent a behavior pattern that a person in the organization can play.</p></li>
<li><p>A security role includes a defined set of application access privileges.</p></li>
<li><p>A security role can be defined as a group of duties for a job function.</p></li>
<li><p>System administrators can limit the data that users can access by applying data security policies. Administrators can also control the level of access that users in the role have to current, past, or future records.</p></li>
<li><p>Users are assigned to one or more security roles. Each user must be assigned to at least one security role to have access to Microsoft Dynamics AX.</p></li>
<li><p>Examples of security roles: Shipping Clerk, Accounts Receivable Clerk, System Administrator.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Role hierarchy</p></td>
<td><ul>
<li><p>Security roles can be organized into a hierarchy by defining roles as combinations of other roles. For example, the accounting manager role could be defined as a combination of the manager role and the accountant role.</p></li>
<li><p>A role hierarchy is a many to many relation that allows defining a security role as being derived from another security role.</p></li>
<li><p>Instead of having to define each security role independently, a role hierarchy allows security roles to inherit the permissions from other security roles and reuse them.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Duty</p></td>
<td><ul>
<li><p>A duty is a responsibility to perform one or more tasks or services for a job. Duties correspond to parts of a business process.</p></li>
<li><p>A duty can be defined as a group of related privileges allowing a specific business function.</p></li>
<li><p>In the security model, a duty is a set of application access privileges that are required for a user to carry out their responsibilities.</p></li>
<li><p>Duties are designed with a specific business objective in mind.</p></li>
<li><p>A duty can be assigned to more than one role.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Process</p></td>
<td><ul>
<li><p>A functional work structure that an organization is responsible for designing, controlling, and improving.</p></li>
<li><p>A process consists of a coordinated set of activities in which one or more participants consume, produce, and use economic resources to achieve one or more organizational goals.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Process cycle</p></td>
<td><ul>
<li><p>Process cycles organize duties and access privileges according to high level processes. For example, revenue cycle.</p></li>
<li><p>A process cycle can be defined as a group of duties for a job function.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Privilege</p></td>
<td><ul>
<li><p>A privilege specifies the access that is required to accomplish a job, problem, or assignment.</p></li>
<li><p>A privilege contains permissions to individual application objects, such as user interface elements and tables.</p></li>
<li><p>Privileges group together related securable objects. For example, menu items and controls.</p></li>
<li><p>Privileges can be assigned directly to roles. However, for easier maintenance, we recommend only assigning duties to roles.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Entry point</p></td>
<td><ul>
<li><p>An entry point is the object that triggers a user action to start a particular function, such as a form or a service.</p></li>
<li><p>In Microsoft Dynamics AX, there are three different types of entry points - menu items, Web content items and service operations.</p></li>
</ul>
> [!caution]  
> <P>In the licensing model for Microsoft Dynamics AX, entry points are referred to as menu items.</P>
</td>
</tr>
<tr class="even">
<td><p>Permission</p></td>
<td><ul>
<li><p>Permission refers to the securable objects and associated access levels that are required to perform the function associated with an entry point. This could include any tables, fields, forms or server side methods that are accessible through the entry point.</p></li>
<li><p>Security permissions are used to control access to individual application elements: menus, menu items, action and command buttons, reports, service operations, Web URL menu items, Web controls, and fields in the Windows client and Enterprise Portal.</p></li>
<li><p>Permissions group securable objects and permissions that are required for them. For example, form and report permissions.</p></li>
<li><p>In Microsoft Dynamics AX, individual security permissions are combined into privileges, and privileges are combined into duties.</p></li>
</ul>
> [!caution]  
> <P>Be aware that modifying permissions may impact licensing requirements. For more information about how licensing relates to security, see the <a href="http://go.microsoft.com/fwlink/?linkid=228370">Security roles and licensing white paper</a> for Microsoft Dynamics AX 2012.</P>
</td>
</tr>
<tr class="odd">
<td><p>Permission set</p></td>
<td><p>A permission set refers to the objects and associated permissions that are required to perform the function associated with an entry point. This could include any tables, fields, forms or server side methods that are accessible through the entry point.</p></td>
</tr>
</tbody>
</table>


## See also

[Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

