---
title: 'Best Practice Performance Optimizations: Database Design and Operations'
TOCTitle: 'Performance Optimizations: Database Design and Operations'
ms:assetid: ad874ff2-d5f6-414c-b892-1685e7739e15
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa854605(v=AX.60)
ms:contentKeyID: 35249723
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practice Performance Optimizations: Database Design and Operations 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes design techniques that can improve database performance.

## Caching

Set the table cache level to cache as many records as possible for the table.

Use the record view cache when the same set of records is going to be repeatedly selected.

You can also use your own local caching, in a simple buffer variable, in a record-sorted list or in a temporary table.

## Index Design

Index design is very important. Correct index definitions are crucial to a well-performing application. Ensure that there are adequate indexes and that there is the correct number of fields in each index.

It can be useful to add or remove some indexes on the individual installations, depending on the amount and contents of their records.

Using clustered indexes to organize your tables can lead to large gains in performance, but do so carefully. For more information, see [Clustered Indexes](clustered-indexes.md).

## Select Statements

  - Use joins instead of multiple nested while selects.

  - Use field lists where applicable.

  - Use select/aggregate functions where applicable.

  - Use delete\_from (instead of while select ... .delete()).

  - Select from the cache where possible.

## Transactions

  - Make transactions as short and small as possible, to avoid deadlocks and large rollback logs.

  - Never wait for a user interaction inside a transaction.

  - If several operations must be performed before data returns to a consistent state, perform all the operations in one transaction.

  - Avoid deadlocks. Explicitly select records to be updated in a specific order within the table (preferably the order of the key), each time, throughout the application. Select records for update from different tables in the same order, each time, throughout the application.

## Avoid Lengthy Locks on Commonly Used Records

  - Use Optimistic Concurrency Control (OCC).

  - Update locks on central, commonly used (updated) records that represent bottlenecks in the application.

  - Try to avoid updating commonly used records inside transactions.

  - Structure the design so that you can use inserts instead of updates. Inserts do not lock objects.

  - Place the select statement for updates as close to the ttsCommit statement as possible, to reduce the amount of time records are locked.

## Do Not Write/Update if the Record Has Not Been Changed

The system routinely optimizes database updates by updating a record only if it has actually been changed. If you can do that optimization yourself, it can spare some database operations.

## Use Joins in Forms

Use joins in forms, instead of using display methods that contain selects.

Using display methods with selects on grids on forms can be slow on thin AOS clients, especially if they are not cached. A call has to be made from the client to the AOS and from there to the database server. These calls are multiplied by the number of visible lines in the grid.

If possible, rewrite the form to use a join statement between the data sources. There will be only one call to the database when approximately 20 rows are shown in the grid. It is also possible to filter, find, and sort on the joined fields.

## Use the Internal Cache of the Form

Whenever records are selected from the database and shown in a form, they are cached internally in the form. You can access and use the cached information rather than re-selecting the records.

### ![Aa854605.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa854605.collapse_all(en-us,AX.60).gif")Example

A form shows data from up to four tables that are related to the table on the first tab page, each on a grid on a separate tab page. The related tab pages are hidden if there is no data to show.

Tab pages can be hidden by selecting a record in the database with the same range as that shown on the tab page. If no records are retrieved, the tab page is hidden (.visible(false)). This results in two selects for the same data per tab page.

The hiding of the tab pages can be optimized to only one select per tab page by checking if there is any data in the related internal cache, and then hiding the tab page if there is no data. The actual check is performed by asking if the buffer related to the data source on the tab page is true (with some records to show) or false.

## See also

[Best Practices: Performance Optimizations](best-practices-performance-optimizations.md)

[Best Practice Performance Optimizations: General Programming](best-practice-performance-optimizations-general-programming.md)

[Best Practice Performance Optimizations: AOS Tuning](best-practice-performance-optimizations-aos-tuning.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

