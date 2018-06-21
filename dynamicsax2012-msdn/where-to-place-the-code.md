---
title: Where to Place the Code
TOCTitle: Where to Place the Code
ms:assetid: a1576a4d-7408-40df-8a3e-ed82472b1d65
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa849024(v=AX.60)
ms:contentKeyID: 35248304
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Where to Place the Code [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Correct code placement is essential for good application performance (especially in the client/server environment) and to make the application easy to customize, reuse, navigate, and maintain.

## 3-tier Design

Optimize your programs to utilize the 3-tier architecture that is supported by Microsoft Dynamics AX.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Tier</p></th>
<th><p>Objects and code belonging to the tier</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Client</p></td>
<td><p>Presentation layer. This is where forms are stored. Place client-specific classes and methods here.</p></td>
</tr>
<tr class="even">
<td><p>Object server</p></td>
<td><p>The location of business application logic. Transaction-oriented database update jobs should be placed to run here, close to the database.</p></td>
</tr>
<tr class="odd">
<td><p>Database server</p></td>
<td><p>Utilize the power of the database server by using aggregate functions, joins, and other calculating features of the database management system.</p></td>
</tr>
</tbody>
</table>


## Classes

Put code in the classes that are:

  - Related to many tables, such as update jobs
    
    –or–

  - Not related to tables, for example, various supporting activities

Create class instance methods:

  - When working on the instance variables of the class (objects of)
    
    –or–

  - When overriding is potentially useful

Create class static methods when:

  - Access to the class instance members is not needed

  - Overriding is not necessary

  - The functionality of the method is related to the class it is defined on

  - The method might be able to execute on a different tier than the method's

## Tables

Put code that is strictly related to a table as methods on that table.

Create table instance methods for handling one record at a time. Create table static methods when handling none, some, or all records.

Split code to be executed on separate tiers into separate methods.


> [!NOTE]
> <P>Do not create instance methods when no instance is needed.</P>
> <P>Code in static methods can technically be created anywhere—on any table or class—because it has no physical binding to the instance. Create it either on the table or on the class where it logically belongs.</P>



## The Global Class

Place methods in the Global class if they cannot be placed more logically on another class (or table).

Methods on Global should have the same character as the [system functions](https://msdn.microsoft.com/en-us/library/aa856741\(v=ax.60\)). They should be general-purpose, tool-extending, and application-neutral.

Do not use the Global:: prefix when calling Global methods—methods on this class do not need a variable declaration.

## Forms and Reports

Do not put any code in forms or reports except for calls to the classes and table methods that handle complex layout and business logic.

Do not to place edit and display methods on forms and reports if they can be placed on a table.

If code cannot be avoided in the form:

  - Place the code at the data source/data source field level and not at the control level.

  - Call classes from buttons on forms by using menu items (for example, by not using code).

## Maps

Use maps for a limited number of connected fields. For example, for the Address fields, code should be placed on AddressMap.

## Views

Views are limited select statements used on read-only tables. Do not place much code on views, unless, for example, you have a display method on the parent table.

## See also

[Designing a Microsoft Dynamics AX Application](designing-a-microsoft-dynamics-ax-application.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

