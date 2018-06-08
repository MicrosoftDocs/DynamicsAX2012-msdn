---
title: Select Statements on Fields
TOCTitle: Select Statements on Fields
ms:assetid: 9a2a3ae2-2cc8-4381-9375-1e25f3270a19
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa845654(v=AX.60)
ms:contentKeyID: 35248100
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Select Statements on Fields 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

It is possible to use a select statement in a lookup on a field. Following a select statement that fetches a record in a table, you can write .fieldName to reference a field in the table. These select statements must be used in expressions.

There is a difference between a normal select statement and a field select statement:

  - The field select statement operates directly on a table.

  - The normal select statement operates on a table buffer variable.

## Example

    void selectFieldExamples ()
    {
        ;
        // Prints the NameRef field from the selected customer
        print (select CustTable order by AccountStatement).AccountStatement;
             pause;
     
        // Uses the balance field from the customer with AccountNum 3000
        if ((select custTable where CustTable.AccountNum == '3000').CreditMax < 50000)
          print "This customer has a credit maximum less than $50,000.";
          pause;
    }

## See also

[Select Statements](select-statements.md)

[while select Statements](while-select-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

