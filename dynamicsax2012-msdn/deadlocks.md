---
title: Deadlocks
TOCTitle: Deadlocks
ms:assetid: fd1474bd-c58a-47fd-95bb-e602102327dd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa892828(v=AX.60)
ms:contentKeyID: 35254204
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Deadlocks [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A deadlock occurs when two or more database tasks permanently block each other by maintaining a lock on a resource that the other tasks are attempting to lock. An example of this is when each task has obtained a lock on data that the other task needs to complete it work.

## Example

  - Transaction 1 has a lock on the CustTable and wants a lock on the VendTable but is blocked by Transaction 2.

  - Transaction 2 has a lock on the VendTable and wants a lock on the CustTable but is blocked by Transaction 1.

Transaction 1 is waiting for Transaction 2 to complete but it has a lock on the resources that Transaction 2 needs to complete and Transaction 2 is waiting for Transaction 1 to complete but it has a lock on the resources that Transaction 1 needs to complete creating a circular dependency.

Each database engine monitors for deadlocked transactions and follows its own rules for handling deadlocks. Typically the database engine resolves the deadlock by selecting one of the transactions as a deadlock victim, terminating that transaction based on certain rules and returning an error. This allows the successful transaction to complete.

## Minimize Deadlocks

Use the following coding best practices to minimize the occurrence of deadlocks:

  - Access server objects in the same order each time. If two separate database tasks always request access to the CustTable first and then the VendTable, a task may be temporarily blocked but is less likely to be deadlocked. Requesting access to the CustTable and then the VendTable in one task and requesting access to the VendTable and then the CustTable in another is likely to lead to a deadlock.

  - Ensure that the database design is normalized.

  - Reduce lock time by grabbing locks at the latest possible time and releasing locks as early as possible.

  - Don't allow user input during a transaction. Collect all user input before a database transaction begins to avoid blocking other transactions indefinitely. If you must get user input during a transaction, implement a time out facility in your code so that the blocking transaction is either rolled back or committed.

  - Keep transactions as short as possible.

Deadlocks cannot always be avoided so be sure to put database transaction code within a try/catch block. You can then test for a deadlock exception and retry the operation. For more information about handling deadlock exceptions, see [X++ standards: try/catch Statements](x-standards-try-catch-statements.md)

## See also

[X++ standards: try/catch Statements](x-standards-try-catch-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

