---
title: Enums
TOCTitle: Enums
ms:assetid: e738f221-a042-4f21-a45d-f65c643ca099
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa881702(v=AX.60)
ms:contentKeyID: 35253222
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Enums [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

X++ does not support constants but has an enumerable type (enum), which is a list of literals. You need to create an enum in the Application Object Tree (AOT) before you can use it.

Enum values are represented internally as integers. The first literal has number 0, the next has number 1, the next has number 2, and so on. You can use enums as integers in expressions.

There are hundreds of enumerable types that are built into the standard application. For example, the enum NoYes has two associated literals, where No has the value 0, and Yes has the value 1.


> [!TIP]
> <P>To get a list of all enums when you are using the X++ code editor, press F11.</P>



## Creating an Enum

To create an enum

1.  Expand the **Data Dictionary** node in the AOT.

2.  Right click the **Base Enums** node and select **New Base Enum**.

3.  Rename the enum.

4.  The literals in the enum are called elements. Right-click the enum and select **New Element**.

5.  Rename the element.

6.  Add as many additional elements as you need.

By default, elements take values in the order in which they are created. The first element has the value 0, the second element has the value 1, and so on. However, you can explicitly assign a particular integer value to an element by using the EnumValue property.

## Range and Precision

You can create as many enums as you want, and you can declare up to 251 (0 to 250) literals in a single enum type.

## Declaring Enums

You must create an enum type in the AOT before you can declare it.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Enum declaration</p></td>
<td><p>=</p></td>
<td><p>enumname Variable { , Variable } ;</p></td>
</tr>
<tr class="even">
<td><p>Variable</p></td>
<td><p>=</p></td>
<td><p>identifier [ option ]</p></td>
</tr>
<tr class="odd">
<td><p>Option</p></td>
<td><p>=</p></td>
<td><p><a href="arrays.md">Arrayoptions</a> | initialization</p></td>
</tr>
</tbody>
</table>


    //A NoYes enum
    NoYes done;
     
    //An array of Criteria enums 
    Criteria crit[100];

## Referencing Enums in X++

To reference an enum, use the name of the enum, followed by the name of the literal, separated by two colons:

EnumName::literal

For example, to use the literal No in the NoYes enum, write NoYes::No.

## Automatic Conversion

Enums are automatically converted into Booleans, integers, and reals.

## Overview of Enums

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Keyword</p></td>
<td><p>None—the keyword is the name of the enum</p></td>
</tr>
<tr class="even">
<td><p>Size of data type</p></td>
<td><p>Byte</p></td>
</tr>
<tr class="odd">
<td><p>Scope of data type</p></td>
<td><p>User-defined</p></td>
</tr>
<tr class="even">
<td><p>Default value</p></td>
<td><p>0 (first literal)</p></td>
</tr>
<tr class="odd">
<td><p>Implicit conversions</p></td>
<td><p>Automatically converted to Boolean, int, and real</p></td>
</tr>
<tr class="even">
<td><p>Explicit conversions</p></td>
<td><p>enum2str, str2enum</p></td>
</tr>
</tbody>
</table>


## See also

[Data Types in X++](data-types-in-x.md)

[Variables](variables.md)

[enum2Str Function](https://msdn.microsoft.com/en-us/library/aa845422\(v=ax.60\))

[str2Enum Function](https://msdn.microsoft.com/en-us/library/aa655065\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

