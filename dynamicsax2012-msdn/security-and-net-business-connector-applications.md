---
title: Security and .NET Business Connector Applications
TOCTitle: Security and .NET Business Connector Applications
ms:assetid: d5140289-10e6-4b6b-b9c4-6a1df463e9bd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb986589(v=AX.60)
ms:contentKeyID: 35252026
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Security and .NET Business Connector Applications [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX .NET Business Connector uses authentication and security privileges to implement security.

## Authentication

.NET Business Connector uses Microsoft Windows authentication. Authentication is the process by which the system validates user logon information. A user name and password are compared with an authorized list. If the system detects a match, access is granted to the extent specified in the permission list for that user. A Microsoft Dynamics AX user is allowed to use .NET Business Connector if they satisfy one of the following criteria:

  - User is assigned to the System administrator role

  - User is assigned to the Business Connector role

  - User is assigned to a role with the privilege of doing a .NET Business Connector operation

For information on how to assign a user to a role, see [Assign users to security roles](https://msdn.microsoft.com/en-us/library/gg751367\(v=ax.60\)). For more information, see [Authentication](http://go.microsoft.com/fwlink/?linkid=104941).

## Security Privileges

Security privileges are permissions on specific application elements. You can assign privileges to roles and users are then assigned to the role. The following security privileges in Microsoft Dynamics AX enable a user to perform operations through the .NET Business Connector. These are located under **AOT** \> **Security** \> **Privileges**.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Privilege</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SysCom</p></td>
<td><p>Allows the Logon operation.</p></td>
</tr>
<tr class="even">
<td><p>SysComExecution</p></td>
<td><p>Allows an X++ query to be run.</p></td>
</tr>
<tr class="odd">
<td><p>SysComISS</p></td>
<td><p>Allows the Logon operation using .NET Business Connector through a Web process, for example Internet Information Services (IIS).</p></td>
</tr>
<tr class="even">
<td><p>SysComDataCreate</p></td>
<td><p>Allows new rows to be created.</p></td>
</tr>
<tr class="odd">
<td><p>SysComDataRead</p></td>
<td><p>Allows access to data rows.</p></td>
</tr>
<tr class="even">
<td><p>SysComDataUpdate</p></td>
<td><p>Allows existing rows to be updated.</p></td>
</tr>
<tr class="odd">
<td><p>SysComDataDelete</p></td>
<td><p>Allows existing rows to be deleted.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>If the user is assigned to the SysBusinessConnectorRole role, all .NET Business connector operations are allowed and the security privileges are ignored. The security privileges are checked only if user is not assigned to the role SysBusinessConnectorRole.</P>



## See also

[.NET Business Connector Overview](net-business-connector-overview.md)

[How to: Debug X++ Code Running in .NET Business Connector](how-to-debug-x-code-running-in-net-business-connector.md)

Security overview

[Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

