---
title: Troubleshooting Forms
TOCTitle: Troubleshooting Forms
ms:assetid: f00d1566-956f-4490-86c2-bd3fa6a81b09
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa885747(v=AX.60)
ms:contentKeyID: 35253301
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Troubleshooting Forms [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

What do you need help with?

My form is blank.

The property sheet for my form control is shaded.

My ComboBox control does not display all options.

## Blank Forms

A form may appear to be blank for any of the following reasons:

  - One or more of the fields on the underlying table may have had the **Visible** property set to **No**.

  - The form might not be bound to an underlying table. Check the **Data Sources** node of the form to verify that an actual table is specified.

  - The form might be bound to an underlying data source that does not have any data. Check the underlying data source to make sure that it includes one or more records.

  - The **DataSource** property of the grid control is empty. If you do not specify a data source for the grid, the grid will not show any field values.

## Control Properties Shaded

The property sheet for a form control in a group control is shaded if the **AutoDataGroup** property for the group has been set to **Yes**. To view or change the **AutoDataGroup** value, you must use the autoDataGroup method for the group control. The default value for the **AutoDataGroup** property is **No**.

## ComboBox Control Values are Missing

You might find that a ComboBox control associated with a database field of type enum is missing values. The missing value occurs when you have the following conditions:

  - You set the **Mandatory** property of the field to **Yes**.

  - You use that field as the data source for the ComboBox control

As a result, you cannot see the first value (value 0) of the enum. The first enum value is invalid.

To enable the first enum value, you must set the **Mandatory** property of the field to **No**.

## See also

[Form Control Properties](form-control-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

