---
title: Extended Data Types (EDTs)
TOCTitle: Extended Data Types (EDTs)
ms:assetid: ed713410-76c7-4b4e-9a27-a5ce9764743e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa884607(v=AX.60)
ms:contentKeyID: 35253243
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Extended Data Types (EDTs) [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Extended data types (EDTs) are user-defined types, based on the primitive data types boolean, integer, real, string, and date, and the composite type container. You can also base EDTs on other EDTs.

This feature is not implemented as a language construct. EDTs are defined in the Application Object Tree (AOT).

An EDT is a primitive data type or container with a supplementary name and some additional properties. For example, you could create a new EDT called Name and base it on a string. Thereafter you can use the new EDT in variable and field declarations in the development environment.

## Benefits of EDTs

The benefits of EDTs are as follows:

  - Code is easier to read because variables have a meaningful data type. For example, Name instead of string.

  - The properties you set for an EDT are used by all instances of that type, which reduces work and promotes consistency. For example, account numbers (AccountNum data type) have the same properties throughout the system.

  - You can create hierarchies of EDTs, inheriting the properties that are appropriate from the parent and changing the other properties. For example, the ItemCode data type is used as the basis for the MarkupItemCode and PriceDiscItemCode data types.

## Declaration of EDT Variables

In the AOT, the **Data Dictionary** \> **Extended Data Types** node is used to create EDTs. The range of an EDT is identical to that of the base type it is based on. When you declare a variable in X++, use the syntax shown in the following table.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Extended declaration</p></td>
<td><p>=</p></td>
<td><p>Extendedtype Variable { , Variable } ;</p></td>
</tr>
<tr class="even">
<td><p>Variable</p></td>
<td><p>=</p></td>
<td><p>Identifier [ option ]</p></td>
</tr>
<tr class="odd">
<td><p>Option</p></td>
<td><p>=</p></td>
<td><p><a href="arrays.md">arrayoptions</a> | initialization</p></td>
</tr>
</tbody>
</table>


where Extendedtype is the name of the extended data type in the AOT.

    // A UserGroupID (integer) variable is declared and initialized to 1.
    UserGroupID groupID = 1;
    
    // An Amount (real) variable is declared.
    Amount currency;

## Automatic Conversion

EDTs are standard data types, but with a specific name and additional properties. EDTs undergo the same value and type conversions as do the standard data types they are based on.

## See also

[Extended Data Types in the Database](extended-data-types-in-the-database.md)

[Data Types in X++](data-types-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

