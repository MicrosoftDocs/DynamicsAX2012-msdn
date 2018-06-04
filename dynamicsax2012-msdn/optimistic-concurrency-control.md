---
title: Optimistic Concurrency Control
TOCTitle: Optimistic Concurrency Control
ms:assetid: 7c9d49dd-34cd-4d1f-bb07-16ee179d3517
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb190073(v=AX.60)
ms:contentKeyID: 35246090
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Optimistic Concurrency Control 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Optimistic Concurrency Control (OCC) helps increase database performance. Pessimistic Concurrency Control locks records as soon as they are fetched from the database for an update. However, Optimistic Concurrency only locks records from the time when the actual update is performed.

Pessimistic concurrency was the only option available in Microsoft Axapta 3.0 (now a part of Microsoft Dynamics). You can now choose which concurrency model to use—optimistic or pessimistic.

Following are the advantages of using OCC:

  - Fewer resources are used to hold the locks during the update process.

  - Records are locked for a shorter length of time.

  - Records remain available for other processes to update if they have been selected from the database but haven't yet been updated.

The disadvantage of using OCC is that the update can fail if another process updates the same record. If the update fails, it must be retried. This can lead to a reduction in database performance.

## Update Conflicts

OCC makes it possible for other processes to update a record even after it has been fetched. You can catch update conflicts by catching the UpdateConflict and UpdateConflictNotRecovered exceptions. For more information, see [Exception Handling with try and catch Keywords](exception-handling-with-try-and-catch-keywords.md).

Update conflicts are detected by the kernel. It checks the value of the recVersion system field on the table at the time the record is selected for update. This value is matched to the value of the field when the record is subsequently updated. The default value of recVersion is 1. This is changed to a random value when a record is updated.

## Set the Concurrency Model

The concurrency model is set on all tables in the standard application. The majority of tables use optimistic concurrency. You can change these settings, specify settings for your own tables, and specify the concurrency model at a statement level or at a global level.

To set the concurrency model for a table, set the OccEnabled table property.


> [!NOTE]
> <P>The DictTable.occEnabled method returns the concurrency model setting for a table.</P>



To set the concurrency model for a statement, replace the forUpdate keyword in your select statement with optimisticLock or pessimisticLock. This overrules (or enforces) the setting on the table. For example:

select pessimisticLock custTable   
     where custTable.AccountNum \> '1000'

If you use the forUpdate keyword, the concurrency model used will be that which was set on the table.

You can also control the concurrency model by using the xRecord.concurrencyModel method or the QueryBuildDataSource.concurrencyModel method. These methods take the ConcurrencyModel enumeration as a parameter.

### ![Bb190073.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb190073.collapse_all(en-us,AX.60).gif")Decide which Concurrency Model to Use

Enforce optimistic concurrency in situations where the optimistic model would improve concurrency and throughput when compared with the pessimistic model. For example, where more records are locked than are actually updated. Use OCC if a table is never updated or deleted from code but updated only by a client through a form.

Use pessimistic concurrency under the following conditions:

  - Serialization logic exists that requires an update lock on a record in the database. The serializing select statement should include the pessimisticLock keyword. The logic fails if the OccEnabled property is changed on the table.

  - Update conflicts are likely (otherwise, extra time is used on retries).

If only a few business scenarios require a different concurrency model rather than the one already set on the table, handle the scenarios individually by applying a line of statement-level concurrency code.

### ![Bb190073.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb190073.collapse_all(en-us,AX.60).gif")Set a Concurrency Model Globally

Override all table-level concurrency settings at run time. This affects all business logic except for situations where the optimisticLock or pessimisticLock keywords have been used.

Global changes are made on the **Concurrency model configuration** form, which is accessible from **Administration** \> **Setup** \> **Database** \> **Concurrency model configuration**.


> [!WARNING]
> <P>Overriding the table-level concurrency settings can significantly affect database performance. Before you disable the table-level settings, test the effects in a non-production environment.</P>



## Concurrency Models in Forms

When data is updated or deleted by a client by using forms, the OccEnabled property on the tables is ignored. OCC is always used.

## See also

[Table Properties](https://msdn.microsoft.com/en-us/library/aa871620\(v=ax.60\))

[ConcurrencyModel Enumeration](https://msdn.microsoft.com/en-us/library/gg882089\(v=ax.60\))

[Data Integrity](data-integrity.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

