---
title: Composite Data Types
TOCTitle: Composite Data Types
ms:assetid: e9c5429c-348e-4b2b-a336-61f4ba5f2438
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa882886(v=AX.60)
ms:contentKeyID: 35253230
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Composite Data Types [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The composite data types in X++ are listed in the following table. For more information about each data type, click its link.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++ composite data types</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="arrays.md">Arrays</a></p></td>
<td><p>An array is a list of items with the same data type and the same name—only the index differs.</p></td>
</tr>
<tr class="even">
<td><p><a href="containers.md">Containers</a></p></td>
<td><p>A container is a dynamic list of items containing primitive data types and/or some composite data types.</p></td>
</tr>
<tr class="odd">
<td><p><a href="classes-as-data-types.md">Classes as Data Types</a></p></td>
<td><p>A class is a type definition that describes both variables and methods for instances (objects) of the class.</p></td>
</tr>
<tr class="even">
<td><p><a href="event-handler-nodes-in-the-aot.md">Delegates as data types</a></p></td>
<td><p>A delegate collects methods that subscribe to the delegate. The delegate specifies the parameter signature that all its subscriber methods must share. When the delegate is called, the delegate calls each of its subscribers.</p></td>
</tr>
<tr class="odd">
<td><p><a href="tables-as-data-types.md">Tables as Data Types</a></p></td>
<td><p>All tables defined in the database can be handled as class definitions.</p></td>
</tr>
</tbody>
</table>


The [Collection classes](collection-classes-in-microsoft-dynamics-ax.md) allow you to create arrays, lists, sets, maps, and structs that can hold any data type, including objects.

## Default Values on Composite Types

The default values for variables of composite data types are shown in the following table.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Data type</p></th>
<th><p>Default</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Array</p></td>
<td><p>as data type</p></td>
<td><p>The default value on an array is that all items have their normal default value.</p></td>
</tr>
<tr class="even">
<td><p>Container</p></td>
<td><p>empty</p></td>
<td><p>The default value of a container is empty. The container does not contain any values.</p></td>
</tr>
<tr class="odd">
<td><p>Class</p></td>
<td><p>null</p></td>
<td><p>A class is only a definition for objects, and all objects are null when they are declared.</p></td>
</tr>
<tr class="even">
<td><p>Delegate</p></td>
<td><p>not applicable</p></td>
<td><p>No delegate can have a default value. However, each delegate starts with zero methods subscribed to it.</p></td>
</tr>
<tr class="odd">
<td><p>Table</p></td>
<td><p>empty</p></td>
<td><p>A table variable can be seen as an instance (an object) of the table (class) definition. For every field in a table variable, the default value is empty.</p></td>
</tr>
</tbody>
</table>


## See also

[Extended Data Types (EDTs)](extended-data-types-edts.md)

[Primitive Data Types](primitive-data-types.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

