---
title: Security Policies in the AOT for Data Records
TOCTitle: Security Policies in the AOT for Data Records
ms:assetid: ab4cce5a-8abe-4b45-89c2-65901642454a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg847361(v=AX.60)
ms:contentKeyID: 35249614
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Security Policies in the AOT for Data Records [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes the relationships between the Application Object Tree (AOT) elements that work together to create and apply security policies. Security policies determine the allowable table record accesses for users that are associated to the same security roles that the policies are associated to.

Security policies are based on AOT queries. Queries filter table records by the joining of data sources, and by range specifications that data values must satisfy.


> [!NOTE]
> <P>In contrast to security <EM>policies</EM> which secure table rows or records, security <EM>permissions</EM> secure table columns or fields.</P>



## Creating a Query for your Policy

All security policies are based on an AOT query. The query defines the table records that the policy allows access to. This topic uses the **VendProfileAccountPolicy** query as an example.

The **VendProfileAccountPolicy** query has two ranges defined. The ranged named **ExternalEntityType** allows access only to table records that have the entity type value of Vendor.

![The VendProfileAccountPolicy query in the AOT.](images/Gg847361.VendProfileAccountPolicy-AOT-q41(en-us,AX.60).png "The VendProfileAccountPolicy query in the AOT.")

**The VendProfileAccountPolicy query**

## Create a Security Policy in the AOT

You create a security policy under **AOT** \> **Security** \> **Policies**.

Next you set the following properties on your new policy:

1.  Set the **PrimaryTable** property. This affects the drop-down list for the **Query** property.

2.  Set the **Query** property. In the current example the query is named **VendProfileAccountPolicy**.

3.  Set the **ConstrainedTable** property.

4.  Set the **ContextType** property.

5.  Set the **ContextString** property, if appropriate for the **ContextType** value.

There are other important properties to set also. For more information about these properties, see [Security Policies Properties](security-policies-properties.md).

![The security policy VendProfileAccount in the AOT.](images/Gg847361.VendProfileAccountPolicy-AOT-spq41(en-us,AX.60).png "The security policy VendProfileAccount in the AOT.")

**The VendProfileAccount policy**

### ![Gg847361.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg847361.collapse_all(en-us,AX.60).gif")Add Constrained Tables under the Policy

The query might have several data sources. Typically they are tables that are related by foreign key relations. You increase the number of tables that the policy secures by adding nodes under the **ConstrainedTables** node of the security policy. You increase the number of tables that are secured by the policy by adding nodes under the **ConstrainedTables** node for the security policy. The nodes represent a set of tables that are connected by foreign keys relations. Some constrained tables should have foreign key relations with a table in the query. And those tables would have foreign key relations with some remaining tables, and so on. All the constrained tables are linked by foreign keys. Security applies to apply the whole set of constrained tables.

## Interaction between Multiple Security Policies

The behavior of the system depends on the number of policies that apply, as explained in the following list:

  - When no security policy applies – There are no restrictions on which records can be accessed.

  - When one security policy applies – The records that are included by the policy are the only records that can be accessed.

  - When two or more security policies apply – The intersection (not the union) of the records that are included by each policy are the only records that can be accessed. This means that a record must satisfy all the applicable security policies before access to the record is allowed.

## See also

[Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md)

[Security Policies Properties](security-policies-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

