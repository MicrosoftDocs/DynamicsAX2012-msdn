---
title: insert Table Method
TOCTitle: insert Table Method
ms:assetid: b22e949d-667e-4e28-b134-6e16ba3344d7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa856945(v=AX.60)
ms:contentKeyID: 35249741
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# insert Table Method [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The xRecord .insert method generates values for RecId and system fields, and then inserts the contents of the buffer into the database.

The method operated as follows:

  - Only the specified columns of those rows selected by the query are inserted into the named table.

  - The columns of the table being copied from and those of the table being copied to must be type compatible.

  - If the columns of both tables match in type and order, the column-list may be omitted from the insert clause.

The insert method updates one record at a time. To insert multiple records at a time, use [array inserts](optimizing-record-inserts.md), [insert\_recordset](insert-recordset.md), or [RecordSortedList.insertDatabase](https://msdn.microsoft.com/en-us/library/gg923768\(v=ax.60\)).

To override the behavior of the insert method, use the [doInsert](doinsert-table-method.md) method.

## Example 1

The following code example inserts a new record into the CustTable table, with the AccountNum set to 5000 and the Name set to MyCompany (other fields in the record will be blank).
```X++  
    CustTable custTable;
    ;
    ttsBegin;
      
    select forUpdate custTable;
    custTable.AccountNum = '5000';
    
    custTable.insert();
      
    ttsCommit;
```
## Example 2: Transaction and Duplicate Key

The following example shows how you can catch a DuplicateKeyException in the context of an explicit transaction. The exception is thrown when a call to xRecord .insert fails because of a duplication of an existing unique value. In the catch block, your code can take corrective action, or it can log the error for later analysis. Then your code can continue without losing all the pending work of the transaction.


> [!NOTE]
> <P>You cannot catch a duplicate key exception caused by a set based operation such as insert_recordset.</P>



This example depends on two tables TableNumberA and TableNumberB. Each has one mandatory **Integer** field, named NumberAKey and NumberBKey respectively. Each of these key fields has a unique indexed defined on it. The TableNumberA table must have at least one record in it.

``` 
static void JobDuplicKeyException44Job(Args _args)
    {
    TableNumberA tabNumA; // Has one record, key = 11.
    TableNumberB tabNumB;
    int iCountTries = 0, iNumberAdjust = 0, iNewKey, ii;
    container ctNotes;

    // Empty the B table.

    delete_from tabNumB;

    // Insert a copy of one record.

    insert_recordset tabNumB (NumberBKey)

    select firstOnly NumberAKey from tabNumA order by NumberAKey asc;
        
    ttsBegin;

    try
        {
        iCountTries++;
        ctNotes += strFmt("---- Inside the try block, try count is %1. ----", iCountTries);

        while select * from tabNumA order by NumberAKey asc
            {   
            tabNumB .clear();
            iNewKey = tabNumA .NumberAKey + iNumberAdjust;
            tabNumB .NumberBKey = iNewKey;
            ctNotes += strFmT ("-- %1 is the key to be tried. --" ,iNewKey);
            tabNumB .insert();
            ctNotes += "-- .insert() successful. --";
            break; // Keeps demo simple.
            }
        ttsCommit;
        }

    catch (Exception ::DuplicateKeyException, tabNumB) // Table is optional.
        {
        ctNotes += "---- Inside the catch block. ----";
        ctNotes += infolog .text();

        if (iCountTries <= 1)
            {
            ctNotes += "-- Will issue retry. --";
            iNumberAdjust = 1;
            retry; // Erases Infolog.
            }
        else
            {
            ctNotes += "-- Aborting the transaction. --";
            ttsAbort;
            }
        }

    for (ii=1; ii <= conLen(ctNotes); ii++)
        {
        info(conPeek(ctNotes ,ii));
        }
    }
    
```

/\*\*\*\*\*\*\*\*\*\*\* Actual output

Message (10:53:13 am)

\---- Inside the try block, try count is 1. ----

\-- 11 is the key to be tried. --

\---- Inside the catch block. ----

Cannot create a record in TableNumberB (TableNumberB).

The record already exists.

\-- Will issue retry. --

\---- Inside the try block, try count is 2. ----

\-- 12 is the key to be tried. --

\-- .insert() successful. --

\*\*\*\*\*\*\*\*\*\*\*/

## See also

[Updating, Deleting, and Inserting Data](updating-deleting-and-inserting-data.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

