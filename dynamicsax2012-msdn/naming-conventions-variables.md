---
title: 'Naming Conventions: Variables'
TOCTitle: Variables
ms:assetid: fd46ce44-8c38-453c-b347-590827bbab58
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa892904(v=AX.60)
ms:contentKeyID: 35254208
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Naming Conventions: Variables 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Variables of general types (primitive and composite data types) should be named logically.

Variables of specialized types (extended data types) should have the same name as the type (which should have a logical name) but starting with a lower case character.

If you have more than one variable of the same specialized type, use logical names that contain the name of the type as a prefix.

Avoid one-character variable names, except for temporary 'looping' variables, like i and j, or coordinate variables like x and y.

Examples:

InvoiceJour invoiceJour;

InvoiceLine invoiceLine;

CustTable custTable;

CustTrans custTrans;

MarkupTrans markupTrans;

int i;

The prefix of the variable can be removed if the name of the variable is still understandable.

## See also

[Data Types in X++](data-types-in-x.md)

[Extended Data Types (EDTs)](extended-data-types-edts.md)

[Naming Conventions](naming-conventions.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

