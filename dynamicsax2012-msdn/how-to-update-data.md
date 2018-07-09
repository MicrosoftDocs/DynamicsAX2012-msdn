---
title: 'How to: Update Data'
TOCTitle: 'How to: Update Data'
ms:assetid: 91f7409a-7aff-430a-bac9-152f4a07f372
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa661155(v=AX.60)
ms:contentKeyID: 35247437
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Update Data 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the while select statement to modify data. For more information, see [while select Statements](while-select-statements.md).

All select statements use a table variable. This variable must be declared before a select statement can be executed. For more information, see [Tables as Data Types](tables-as-data-types.md).

In the following example, a customer record is updated when the condition specified by the where clause is met.

The ttsBegin and ttsCommit keywords are used to help ensure the integrity of the data transaction. For more information, see [Transaction Integrity](transaction-integrity.md).


> [!WARNING]
> <P>Microsoft Dynamics AX does not allow you to pass unbounded string parameters in where clauses. You create a bounded string by declaring a character limit after you specify the data type. In the example below, you declare the customer account number parameter as str 30 AccountNum.</P>


```X++  
    static void UpdateCustomerCreditMax(str 30 AccountNum, real newMaximum)
    {
        CustTable custTable;
    
    
        ttsBegin;
     
        while select forUpdate custTable        
                where custTable.AccountNum == AccountNum
                  
        {
            custTable.CreditMax = newMaximum;
            custTable.update();
            
        }
      
        
        ttsCommit;
    }
```
## See also

[Optimizing Record Inserts](optimizing-record-inserts.md)

[Select Statement Syntax](select-statement-syntax.md)

[Database for Microsoft Dynamics AX](database-for-microsoft-dynamics-ax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

