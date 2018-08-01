---
title: 'Best Practices: Performance Optimizations'
TOCTitle: 'Best Practices: Performance Optimizations'
ms:assetid: 123660f6-f2bc-4a2f-b5f3-18879307d851
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa597597(v=AX.60)
ms:contentKeyID: 35240572
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices: Performance Optimizations [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This section has some hints on how an application can be optimized for better performance. This topic also contains a list of the best practice checks for performance. For more information, see the following topics:

  - [Database design and operations](best-practice-performance-optimizations-database-design-and-operations.md)

  - [AOS tuning](best-practice-performance-optimizations-aos-tuning.md)

  - [General programming](best-practice-performance-optimizations-general-programming.md)

## Design for Performance

Design your application for performance and functionality. Use a good data model, and use the paradigms of MorphX (copy what has already been done). The features of MorphX are built for optimized performance.

Keep in mind the following issues when you create your design.

Network setup:

  - The network that connects the client to Application Object Server (AOS) is slow. It is more efficient to make a small number of calls that transfer a large amount of data than it is to make a large number of calls that transfer a small amount of data.

  - The network that connects AOS to a database server is fast, but it is quicker to keep calls in the AOS than to call over the network.

  - Database servers are usually high-end and fast, but a single database server serves everyone, and represents the traditional performance bottleneck in the application.

Execution of X++ code:

  - All X++ statements are fast, but they run faster as CIL than they do in interpretive mode. If your X++ code runs on the AOS, then it can run as CIL.

  - Creation of objects is more time-consuming, but still fast.

  - Database-related statements depend on the database design and load. Usually, selects are faster than inserts, inserts are faster than deletes, and deletes are faster than updates.

  - Calls between tiers (client/server) are slow.

  - Method calls are expensive. Try to reduce the number of calls. For example, do not call the same method several times if you can store a value from the method and instead use that value.

When you design, implement, and test for performance, use a database with a realistic number of records (millions) in the various tables in the database, a realistic number of concurrent users (hundreds), and a realistic configuration of network, clients, and servers.

## Best Practice Checks

Microsoft Dynamics AX conducts specific best practice checks for performance. For information about how to set the options for best practice checks, see [Best practice parameters](best-practice-parameters.md).

The following table lists the best practice error and warning messages and how to fix the errors.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Message</p></th>
<th><p>Message type</p></th>
<th><p>How to fix the error or warning</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Table is missing Clustered Index</p></td>
<td><p>Warning</p></td>
<td><p>Using clustered indexes to organize your tables can lead to large gains in performance, but do so carefully. For more information, see <a href="clustered-indexes.md">Clustered Indexes</a>.</p></td>
</tr>
<tr class="even">
<td><p>Table is missing Primary Index</p></td>
<td><p>Warning</p></td>
<td><p>There are advantages and disadvantages for using indexes. For more information, see <a href="best-practices-for-indexes.md">Best Practices for Indexes</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Extended Data Type is set to be right justified, should be set to left justified</p></td>
<td><p>Warning</p></td>
<td><p>Set the extended data type to be left-justified. For more information about extended data type best practices, see <a href="best-practices-for-extended-data-types.md">Best Practices for Extended Data Types</a>.</p></td>
</tr>
<tr class="even">
<td><p>RunBase classes should be able to run on 'Called From' (Ensure pack and unpack are implemented correctly to allow promptPrim to marshal the class across tiers)</p></td>
<td><p>Warning</p></td>
<td><p>The RunBase class is a framework for classes that need a dialog for user interaction and that need the dialog values to be saved per user. For more information, see <a href="https://msdn.microsoft.com/en-us/library/gg822570(v=ax.60)">RunBase Class</a>.</p></td>
</tr>
</tbody>
</table>


## In This Section

Additional best practice errors relating to tables are described in the following topics.

  - [Best Practice Performance Optimizations: AOS Tuning](best-practice-performance-optimizations-aos-tuning.md)  

  - [Best Practice Performance Optimizations: Database Design and Operations](best-practice-performance-optimizations-database-design-and-operations.md)  

  - [Best Practice Performance Optimizations: General Programming](best-practice-performance-optimizations-general-programming.md)  

  - [Best Practice Performance Optimizations: Swapping Arrays to Disk](best-practice-performance-optimizations-swapping-arrays-to-disk.md)  

## See also

[Designing a Microsoft Dynamics AX Application](designing-a-microsoft-dynamics-ax-application.md)

[Best Practice Overview](best-practice-overview.md)

[Best Practices for Microsoft Dynamics AX Development](best-practices-for-microsoft-dynamics-ax-development.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

