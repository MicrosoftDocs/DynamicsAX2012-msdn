---
title: Role-Based Security System
TOCTitle: Role-Based Security System
ms:assetid: e1307779-6515-46d1-b512-1b1542b24449
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg864884(v=AX.60)
ms:contentKeyID: 35253085
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Role-Based Security System [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Microsoft Dynamics AX security system implements a role-based security model. The primary security specifications are privileges for table fields, and policies for table records. From the perspective of the developer using the AOT, a role is an aggregation of security specifications. The security specifications are designed to support a group of job activities performed by users with a known set of job responsibilities.

The Microsoft Dynamics AX system administrator assigns roles to the users. The users through those role assignments acquire the permissions to perform specific system operations. You should choose role names that describe the job activities performed by users of the system. For more information about role-based security, see [Role-based security in Microsoft Dynamics AX](https://msdn.microsoft.com/en-us/library/gg731787\(v=ax.60\)).

## Strengths of the Role-based Security Model

The strengths of the Microsoft Dynamics AX role-based security system include the following features.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Feature</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Easy administration</p></td>
<td><p>System administrators do not need to know the individual tables needed by users. Developers know which tables to bundle into sets called privileges or duties. The system administrator needs to know only which privileges make sense for each given role. Easier security administration leads to significantly lower total cost of ownership.</p></td>
</tr>
<tr class="even">
<td><p>Conveniently reusable</p></td>
<td><p>The privileges and policies are designed to be easily reused as users and roles change. You can apply a single set of roles across all companies and organizations.</p></td>
</tr>
<tr class="odd">
<td><p>Automatic inference</p></td>
<td><p>The automatic inference feature makes it easy for developers to bundle form permissions into privileges.</p></td>
</tr>
<tr class="even">
<td><p>Regulatory compliance</p></td>
<td><p>The role-based model makes it easy to audit the security structure of the application. You can better comply with regulatory requirements such as those from Sarbanes-Oxley (SOX), International Financial Reporting Standards (IFRS), and the United States Food and Drug Administration (FDA).</p>
<p>You can set up a segregation of duties rules to make sure a user does not have access to conflicting duties. For example, you can set up a rule specifying one person should not be granted access to both create and release a purchase order. In another example, you can set up a rule specifying one person cannot both acknowledge the receipt of goods and pay the vendor.</p>
<p></p></td>
</tr>
</tbody>
</table>


## See also

[Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

