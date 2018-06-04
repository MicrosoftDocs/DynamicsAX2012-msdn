---
title: Role-based Security in the AOT for Developers
TOCTitle: Role-based Security in the AOT for Developers
ms:assetid: e3d0cfab-a7f0-43a9-9ff4-540a3d887e93
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg847971(v=AX.60)
ms:contentKeyID: 35253166
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Role-based Security in the AOT for Developers 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX AOT allows the developer to manage role-based security. Under **AOT** \> **Security** the developer manages permissions, privileges, duties, roles, and policies.

The system administrator assigns privileges, duties, and policies to roles. Users who are assigned to these roles are affected by these privileges and policies.

## Views are a Loose Model of Security

An SQL view has a list of columns in its select clause, and has row filters in its where clause:

  - The column list gives the view the ability to return data from those columns. If it were possible to list no columns, the view would return no data.

  - The row filters define the criteria that each returned row must meet. If no row filters are defined, all rows are eligible to be returned.

The column and row mechanisms of an SQL view are a loose model of how the Microsoft Dynamics AX security model works. Under **AOT** \> **Security** there is a **Privileges** node and a **Policies** node:

  - **Privileges** – are analogous to the column mechanism in an SQL view. On a form, you cannot see data from any field from any table unless a privilege containing the field is assigned to a role that you belong to. If your roles are assigned no privileges, you cannot see any fields on any form.

  - **Policies** – are analogous to the row mechanism in an SQL view. On a form, you can see data from any row from any table unless a policy about rows from those tables is assigned to your roles. If your roles are assigned no policies, you can see any rows or records on any form.

## Privileges are Sets of Permissions

A privilege is a set of permissions. Permissions to read and write data originate under the **Permissions** node of several AOT elements including the following:

  - **Forms** \> MyForm

  - **Parts** \> **Info Parts** \> MyInfoPart

  - **Reports** \> MyReport

  - **Web** \> **Web Files** \> **Web Controls** \> MyWebControl

  - **Services** \> MyService \> **Operations** \> MyOperation

## Policies Originate from Queries

The most common type of security policy originates from a query in the AOT.

On its **Ranges** node, a query specifies the criteria each row or record must satisfy to be returned. Further criteria are specified on its **Relations** node. These specifications help define the security policy that refers to this query.

On its **Fields** node, a query specifies which fields should be returned from which tables. However, the field specifications have no effect on the security policy that refers to this query.

## See also

[Automatic Inference of Permissions in AOT Security](automatic-inference-of-permissions-in-aot-security.md)

[Security Policies in the AOT for Data Records](security-policies-in-the-aot-for-data-records.md)

[Security for Microsoft Dynamics AX](security-for-microsoft-dynamics-ax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

