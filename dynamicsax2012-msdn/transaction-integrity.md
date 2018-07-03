---
title: Transaction Integrity
TOCTitle: Transaction Integrity
ms:assetid: 2d5127c0-9c85-4d81-b419-1fc7e0664c05
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa622564(v=AX.60)
ms:contentKeyID: 35241932
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Transaction Integrity 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX has two internal checking features to help ensure the integrity of transactions made by X++ programmers.

If the integrity of transactions is not ensured, it may lead to data corruption, or, at best, poor scalability with reference to concurrent users on the system.

## forUpdate Checking

This check ensures that no record can be updated or deleted if the record has not first been selected for update. A record can be selected for update, either by using the forUpdate keyword in the select statement, or by using the selectForUpdate method on tables.

## ttsLevel Checking

This check ensures that no record can be updated or deleted except from within the same transaction scope as it was selected for update. Integrity is ensured by using the following statements:

  - ttsBegin: marks the beginning of a transaction. This ensures data integrity, and guarantees that all updates performed until the transaction ends (by ttsCommit or ttsAbort) are consistent (all or none).

  - ttsCommit: marks the successful end of a transaction. This ends and commits a transaction. MorphX guarantees that a committed transaction will be performed according to intentions.

  - ttsAbort: allows you to explicitly discard all changes in the current transaction. As a result, the database is rolled back to the initial state—nothing will have been changed. Typically, you will use this if you have detected that the user wants to break the current job. Using ttsAbort ensures that the database is consistent.


> [!NOTE]
> <P>It is usually better to use <A href="exception-handling-with-try-and-catch-keywords.md">exception handling</A> instead of ttsAbort. The throw statement automatically aborts the current transaction.</P>



Statements between ttsBegin and ttsCommit may include one or more transaction blocks as shown in the following example.
```X++  
    ttsBegin;
        // Some statements.
    ttsBegin;
        // More statements.
    ttsCommit;
    ttsCommit;
```
In such cases, nothing is actually committed until the successful exit from the final ttsCommit.

## Examples

### ![Aa622564.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa622564.collapse_all(en-us,AX.60).gif")Example use of ttsBegin and ttsCommit
```X++  
    Custtable custTable;
    ;
    ttsBegin;
     
    select forUpdate custTable where custTable.AccountNum == '4000';
    custTable.NameAlias = custTable.Name;
    custTable.update();
     
    ttsCommit;
```
### ![Aa622564.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa622564.collapse_all(en-us,AX.60).gif")Examples of Code Rejected by the two Transaction Integrity Checks
```X++  
    ttsBegin;
     
    select myTable; // Rejected by the forUpdate check.
    mytable.myField = 'xyz';
    myTable.update();
     
    ttsCommit;
     
    ttsBegin;
     
    select forUpdate * from myTable;
    myTable.myField = 'xyz';
    ttsCommit;
    ...
    ttsBegin;
    myTable.update(); // Rejected by the ttsLevel check.
     
    ttsCommit;
```
The first failure is because the forupdate keyword is missing.

The second failure is because the update is in another transaction scope rather than the one that the record was selected in ttsCommit for update.

## See also

[How to: Use the UnitOfWork Class to Manage Database Transactions](how-to-use-the-unitofwork-class-to-manage-database-transactions.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

