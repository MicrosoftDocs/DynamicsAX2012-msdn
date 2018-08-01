---
title: 'Best Practices: Table Fields'
TOCTitle: Table Fields
ms:assetid: 6ae8af24-0554-4038-892b-5d3f288ead70
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa609787(v=AX.60)
ms:contentKeyID: 35244793
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices: Table Fields [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX conducts a best practice check for table fields. For information about how to set the options for best practice checks, see [Best practice parameters](best-practice-parameters.md). For information about field properties and field groups, see [Best Practices for Table Field Properties](best-practices-for-table-field-properties.md) and [Best Practices for Field Groups](best-practices-for-field-groups.md).

## Best Practice Checks

The following table lists the best practice error messages and how to fix the errors.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Message</p></th>
<th><p>Message type</p></th>
<th><p>How to fix the error or warning</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Check that when an InventDimId field is added to a table, code for handing this field is also added to the Multisite Activation Wizard.</p></td>
<td><p>Error</p></td>
<td><p>You have added an InventDimId field to a table and you must also add code for handling this field to the Multisite Activation Wizard. This is necessary so that during activation, the site dimension is properly populated wherever inventory dimensions are used. You must add the InventDimId field to InventSiteActivateDimFieldsCheck.updateableFields or InventSiteActivateDimFieldsCheck.notUpdatableFields. Adding it to one of these would affect whether it is considered during multisite activation or not.</p>
<p>This error message is being sent through InventSiteActivateDimFieldsCheck.ValidateField that receives as a parameter the specific field being evaluated, you can use a breakpoint to determine which field is causing the error.</p>
<p>The Multisite Activation Wizard activates the multisite functionality for a Microsoft Dynamics AX company. Data references by all InventDimId fields are updated with site information. Adding an InventDimId field without updating the Multisite Activation Wizard makes it impossible to activate multisite functionality.</p></td>
</tr>
</tbody>
</table>


## Table IDs and Record IDs

Do not directly use the system data types recId or tableId. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon") Instead, use the following extended data types:

  - RefRecId for fields that refer to record IDs

  - RefTableId for fields that refer to table ID

  - Extended data types derived from RefRecId and RefTableId

If a table field uses RefRecID or a data type that is derived from it, a relationship must be defined for that field on either the extended data type or the table. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon").  A relationship is not required, but is recommended, if the field is in a temporary table. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

## Memo and Container Fields

Review the use of memo and container fields in application tables. Memo and container fields have the following characteristics:

  - Add time to the application fetch

  - Add time to the database fetch

  - Inhibit array fetching

  - Cannot be used in where expressions

Consider using text fields with a specific number of characters instead of memo fields. For example, use the Addressing extended data type for addressing fields. Use the ItemFreeTxt extended data type for item descriptions on order lines, and so on.

When selecting tables where the memo or container fields are not needed, consider using a field list, which excludes the unneeded memo or container fields.


> [!NOTE]
> <P>Use field lists carefully. Ensure that they are not used where additional information might be needed.</P>



If the memo or container field is rarely used (compared with the other fields in the table), you could move them away from the table. Place them in a separate table that is then selected (joined) only when the memo and container fields are actually needed. This helps avoid potential field list problems.

## In This Section

[Best Practices for Table Field Properties](best-practices-for-table-field-properties.md)

[Best Practices for Field Groups](best-practices-for-field-groups.md)

[Extended Field IDs](extended-field-ids.md)

## See also

[Best Practices for Table Field Properties](best-practices-for-table-field-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

