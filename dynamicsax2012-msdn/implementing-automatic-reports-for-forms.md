---
title: Implementing Automatic Reports for Forms
TOCTitle: Implementing Automatic Reports for Forms
ms:assetid: 86ee1f62-8325-4bcb-a884-a5ae521355c8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa678005(v=AX.60)
ms:contentKeyID: 35246210
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Implementing Automatic Reports for Forms [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX can be configured to generate a report from the contents of any form that the user currently has open. Such automatic reports are based on the fields placed in the **AutoReport** field group.

1.  Locate the table used as a data source for the form in the Application Object Tree (AOT).

2.  Drag fields from the **Fields** list to the **AutoReport** field group on the table.

If a form has more than one data source, only the fields from the first table are displayed in the report.

The report is displayed when a user selects **File** \> **Print** on an open form. Users can change the default output, range, and sorting before they print the report.

## Best Practices for AutoReport Field Group

You must place at least two fields in the **AutoReport** field group for each table, ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon") except for parameter tables.

The fields placed in the **AutoReport** field group should be those that the user expects to print when they first click **Print** on the **File** menu. The fields used for the TitleField1 and TitleField2 properties are often used for this field group.

## See also

[How to: Create a Field Group](how-to-create-a-field-group.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

