---
title: Best Practices for Field Groups
TOCTitle: Field Groups
ms:assetid: 22f03c3b-1720-4a4d-a367-b723db5cdbba
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa620479(v=AX.60)
ms:contentKeyID: 35241584
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Field Groups 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Any field that appears in the user interface must belong to a field group. You must always use field groups to design your forms.

Standardized group names are as follows:

  - Identification

  - Administration

  - Address

  - ModuleName (for example 'Ledger')

  - Setup

  - Dimension

  - Misc

The Dimension field must always be the only field in a group named 'Dimension.' ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

## Properties

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Rules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Mandatory</p></td>
</tr>
<tr class="even">
<td><p>Label</p></td>
<td><p>Mandatory <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
</tbody>
</table>


## AutoReport

You must place at least two fields in the **AutoReport** field group for each table, ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon") except for parameter tables.

The fields placed there should be the ones that the user expects to print when they first click **Print** on the **File** menu. The fields used for the TitleField1 and TitleField2 properties are often candidates for this field group.

## AutoLookup

If you do not put anything into the **AutoLookup** field group, the AutoLookup form will contain the fields used in the TitleField1 and TitleField2 properties, plus the field in the first unique index.

## See also

[How to: Create a Field Group](how-to-create-a-field-group.md)

[How to: Create Tables](how-to-create-tables.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

