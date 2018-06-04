---
title: Conditional Table Relations
TOCTitle: Conditional Table Relations
ms:assetid: ed24f372-1847-4361-ad7c-d356f98693a0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb190115(v=AX.60)
ms:contentKeyID: 35253238
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Conditional Table Relations 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Define conditional table relations to filter the records in either the primary or the related table. Following are the conditional table relations that can be specified when you define the fields in a table relation:

  - Field fixed

  - Related field fixed

You create a conditional relation by right-clicking the  
 **AOT** \> **Data Dictionary** \> **Tables** \> YourTable \> **Relations** \> YourRelation   
node. Then click either **Field fixed** for **Related field fixed**.

The following table shows the characteristics of the two conditional table relations.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Relation Type</p></th>
<th><p>Format</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Field fixed</p></td>
<td><p>Field fixed</p>
<p>(Table.Field == &lt;EnumValue&gt;)</p></td>
<td><p>Restricts the records selected in the primary table. Only records that meet the condition are selected.</p>
<p>The condition is <strong>AND</strong>ed with your relation.</p></td>
</tr>
<tr class="even">
<td><p>Related field fixed</p></td>
<td><p>Related field fixed</p>
<p>(&lt;EnumValue&gt; == Table.Field)</p></td>
<td><p>Restricts the records selected in the related table. Only records that meet the condition are selected.</p>
<p>The condition is <strong>AND</strong>ed with your relation.</p></td>
</tr>
</tbody>
</table>


## Example of Field Fixed Conditional Relation

Fabrikam, Inc. receives clothing orders by telephone. When a customer places an order, the sales associate determines if the customer wants to buy clothes from the men’s, women’s, or children’s collection.

The Orders table has a CollectionTypeID column that stores which collection the order is related to. The possible CollectionTypeID values are defined by the CollectionType enum, which contains the Man, Woman, and Child values. There are conditional relations between the Orders table and each of the three collection tables (MensCollection, WomensCollection, and ChildrensCollection). One of the conditional relations is used according to which collection type the sales associate selects.

Using conditional relations makes it possible to look up information in three different tables from the same field in the Orders table. The table that Microsoft Dynamics AX uses is determined by the CollectionType enum value in the CollectionTypeID column in the Orders table.

## Example of Related Field Fixed Conditional Relation

Fabrikam, Inc.'s men's collection includes stylish, business, and leisure clothing. There's a ClothingCategoryID column in the MensCollection table, which is populated by the ClothingCategory enum. The ClothingCategoryID column is also in the Orders table.

When the sales associate enters a category into the ClothingCategoryID column in the Orders table, it displays a look-up list of the available items. The number of items in the look-up list (from the MensCollection table) is limited based on the value in the ClothingCategoryID column. This makes it easier to find the appropriate item because the items in two of the three men’s collection categories don't appear in the look-up list.

## See also

[Defining Table Relations](defining-table-relations.md)

[How to: Add a Relation to a Table](how-to-add-a-relation-to-a-table.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

