---
title: Cardinality in Valid Time State Table Relationships
TOCTitle: Cardinality in Valid Time State Table Relationships
ms:assetid: f20ad434-9412-44a1-95d1-01bc27e3719d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg864901(v=AX.60)
ms:contentKeyID: 35253406
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Cardinality in Valid Time State Table Relationships 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Valid time state tables are used to track the effective dates for the relationship between two entities. You can design the indexes on your valid time state table to control the cardinality of the relationship.

## Cardinalities of Relationships

The following table lists the three cardinalities of relationships that can exist between two entities at one moment in time. The cardinalities are described with the example of employees that have been assigned to projects. For valid time state tables, the cardinalities are in terms of any single moment in time.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Name</p></th>
<th><p>Symbol</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>many-to-many</p></td>
<td><p>M:M</p></td>
<td><p>At one moment in time, any one project can have many employees assigned to it (or have no employees). Also, any one employee can be assigned to many projects (or be assigned to no projects).</p></td>
</tr>
<tr class="even">
<td><p>one-to-many</p></td>
<td><p>1:M</p></td>
<td><p>At one moment in time, any one project can have many employees assigned to it (or no employees). But any one employee can be assigned to at most one project (or be assigned to no project).</p></td>
</tr>
<tr class="odd">
<td><p>one-to-one</p></td>
<td><p>1:1</p></td>
<td><p>At one moment in time, any one project can have at most one employee assigned to it (or no employees). Also, any one employee can be assigned to at most one project (or be assigned to no project).</p></td>
</tr>
</tbody>
</table>


A valid time state table that enforces a 1:1 cardinality can have multiple rows for a given pairing of a particular employee to a particular project. However, each such row would have to refer to a different date range.

## Many-to-Many

This section displays an example of M:M data. Then it describes the alternate key index that provides a M:M relationship in a valid time state table.

### ![Gg864901.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg864901.collapse_all(en-us,AX.60).gif")M:M Data

The following table shows example pairings of employees and projects in a M:M relationship. Notice that there are days when each employee is on two projects.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Employee ID</p></th>
<th><p>Project ID</p></th>
<th><p>ValidFrom</p></th>
<th><p>ValidTo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>em11</p></td>
<td><p>pr99</p></td>
<td><p>2001-01-22</p></td>
<td><p>2002-02-22</p></td>
</tr>
<tr class="even">
<td><p>em11</p></td>
<td><p>pr888</p></td>
<td><p>2001-07-23</p></td>
<td><p>2004-04-23</p></td>
</tr>
<tr class="odd">
<td><p>em11</p></td>
<td><p>pr99</p></td>
<td><p>2003-03-24</p></td>
<td><p>2004-04-24</p></td>
</tr>
<tr class="even">
<td><p>em222</p></td>
<td><p>pr99</p></td>
<td><p>2001-01-11</p></td>
<td><p>2003-03-11</p></td>
</tr>
<tr class="odd">
<td><p>em222</p></td>
<td><p>pr888</p></td>
<td><p>2002-02-13</p></td>
<td><p>2004-04-13</p></td>
</tr>
</tbody>
</table>


### ![Gg864901.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg864901.collapse_all(en-us,AX.60).gif")M:M Index

The following list displays the fields that would belong in a unique index for this M:M relationship:

  - EmployeeID

  - ProjectID

  - ValidFrom

  - ValidTo


> [!NOTE]
> <P>The ValidFrom and ValidTo fields must be included in the index when a valid time state table is involved.</P>



## One-to-Many

This section displays an example of 1:M data. Then it describes the alternate key index that provides a 1:M relationship in a valid time state table.

### ![Gg864901.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg864901.collapse_all(en-us,AX.60).gif")1:M Data

The following table shows example pairings of projects and employees in a 1:M relationship. On any one date, each project can have many employees assigned to it, but each employee can be assigned to at most one project. The data shows that in August 2001 the pr99 project had two employees working on it, while each employee was working on only that one project. Later both employees were reassigned to the pr888 project.

When a relationship between an employee and a project has no known end date, the ValidTo field is set to the maximum date. For more information, see [maxDate Function](https://msdn.microsoft.com/en-us/library/aa631979\(v=ax.60\)), or see the [DateTimeUtil::maxValue Method](https://msdn.microsoft.com/en-us/library/gg837450\(v=ax.60\)).

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Employee ID</p></th>
<th><p>Project ID</p></th>
<th><p>ValidFrom</p></th>
<th><p>ValidTo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>em11</p></td>
<td><p>pr99</p></td>
<td><p>2001-01-15</p></td>
<td><p>2002-01-15</p></td>
</tr>
<tr class="even">
<td><p>em11</p></td>
<td><p>pr888</p></td>
<td><p>2002-01-16</p></td>
<td><p>2154-12-31</p></td>
</tr>
<tr class="odd">
<td><p>em222</p></td>
<td><p>pr99</p></td>
<td><p>2001-07-15</p></td>
<td><p>2002-01-15</p></td>
</tr>
<tr class="even">
<td><p>em222</p></td>
<td><p>pr888</p></td>
<td><p>2002-01-16</p></td>
<td><p>2154-12-31</p></td>
</tr>
</tbody>
</table>


### ![Gg864901.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg864901.collapse_all(en-us,AX.60).gif")1:M Index

The following list displays the fields that would belong in a unique index for this 1:M relationship:

  - EmployeeID

  - ValidFrom

  - ValidTo

## One-to-One

This section displays an example of 1:1 data. Then it describes the alternate key index that provides a 1:1 relationship in a valid time state table.

### ![Gg864901.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg864901.collapse_all(en-us,AX.60).gif")1:1 Data

The following table shows example pairings of employees and projects in a 1:1 relationship. Any one project can have at most one employee assigned to it, and any one employee can be assigned to at most one project. Notice that em11 and pr888 are paired more than one time, because each pairing applies to a different date range.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Employee ID</p></th>
<th><p>Project ID</p></th>
<th><p>ValidFrom</p></th>
<th><p>ValidTo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>em11</p></td>
<td><p>pr888</p></td>
<td><p>2008-01-01</p></td>
<td><p>2008-12-31</p></td>
</tr>
<tr class="even">
<td><p>em11</p></td>
<td><p>pr99</p></td>
<td><p>2009-01-01</p></td>
<td><p>2009-12-31</p></td>
</tr>
<tr class="odd">
<td><p>em11</p></td>
<td><p>pr888</p></td>
<td><p>2010-01-01</p></td>
<td><p>2010-12-31</p></td>
</tr>
<tr class="even">
<td><p>em222</p></td>
<td><p>pr99</p></td>
<td><p>2010-01-01</p></td>
<td><p>2010-12-31</p></td>
</tr>
<tr class="odd">
<td><p>em222</p></td>
<td><p>pr888</p></td>
<td><p>2009-01-01</p></td>
<td><p>2009-12-31</p></td>
</tr>
</tbody>
</table>


### ![Gg864901.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg864901.collapse_all(en-us,AX.60).gif")1:1 Index

Two alternate key indexes are needed to enforce a 1:1 relationship. Each index enforces a different 1:M relationship. Their combined effect is to enforce a 1:1 relationship.

One of the indexes has the following fields:

  - EmployeeID

  - ValidFrom

  - ValidTo

The second index has the following fields:

  - ProjectID

  - ValidFrom

  - ValidTo

For more information about alternate key indexes on valid time state tables, see [Walkthrough: Creating a Valid Time State Table](walkthrough-creating-a-valid-time-state-table.md).

## See also

[Valid Time State Tables and Date Effective Data](valid-time-state-tables-and-date-effective-data.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

