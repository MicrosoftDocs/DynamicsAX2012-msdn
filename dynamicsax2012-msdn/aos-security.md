---
title: AOS Security
TOCTitle: AOS Security
ms:assetid: 252fdd86-ab9e-4041-872f-5b04a96f82af
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc551159(v=AX.60)
ms:contentKeyID: 35241656
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# AOS Security [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Application Object Server (AOS) can protect the Microsoft SQL Server database from security threats because clients connect to the database only through the AOS. There are several security advantages when you use the AOS. This topic describes AOS security advantages and best practices for the AOS.

## AOS Security Advantages

The following table describes security advantages when you use the AOS.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Advantage</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>No direct access to the SQL Server database.</p></td>
<td><p>The client configuration does not store the information that would enable it to connect to the database.</p></td>
</tr>
<tr class="even">
<td><p>Built-in data encryption based on common standards.</p></td>
<td><p>For instance, Microsoft Dynamics AX encrypts the data in communications between the AOS and client tiers.</p></td>
</tr>
<tr class="odd">
<td><p>Flexible authentication.</p></td>
<td><p>Authentication to log in to the AOS requires user registration in Microsoft Dynamics AX plus registration in a supportive external system that provides authentication. The list of authentication systems that Microsoft Dynamics AX can interact with includes Active Directory Services and the Claims system of SharePoint. The ability of Microsoft Dynamics AX to interact with a variety of supportive external authentication systems is called flexible authentication.</p></td>
</tr>
<tr class="even">
<td><p>Authorization.</p></td>
<td><p>The AOS has authority to read every Microsoft Dynamics AX table that is in the associated SQL Server database system. A table permissions framework prevents unauthorized Microsoft Dynamics AX users from accessing any table which has its <strong>AOSAuthorization</strong> property set to a restrictive value. Access to system tables is also restricted.</p>
<p>The AOS also enforces authorization according to the role-based security system.</p></td>
</tr>
</tbody>
</table>


## AOS Connection to SQL Server

When you install the AOS, the setup program asks for a domain account. The AOS must have a domain account that has sufficient user rights and permissions.

The AOS account must be a user in the database and must be assigned to the following database roles:

  - db\_ddladmin

  - db\_datareader

  - db\_datawriter

In addition, the AOS user must have the following user rights and permissions to execute stored procedures in the database:

  - createserversessions

  - createusersessions

## See also

[How to: Secure an API on the AOS](how-to-secure-an-api-on-the-aos.md)

[Application Object Server security and protection](https://msdn.microsoft.com/en-us/library/hh202118\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

