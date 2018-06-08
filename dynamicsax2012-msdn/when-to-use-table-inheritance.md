---
title: When to Use Table Inheritance
TOCTitle: When to Use Table Inheritance
ms:assetid: 116a7e9b-9c3c-4a67-9d80-7f9b63dd2ee8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg843731(v=AX.60)
ms:contentKeyID: 35240560
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# When to Use Table Inheritance 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you consider the use of inheritance between two tables, one table is the proposed base table, and the other is the proposed derived table. You should consider the use of inheritance between two tables when all the following conditions are true:

  - There is no thought that there might be a 1-to-many or many-to-many relationship between the two tables, if they were considered in isolation from all other tables.

  - The row in the proposed base table, and the corresponding row in the derived table, both refer to the same item in the real world. The two rows refer to different attributes about the item.

  - Each row in the proposed base table has exactly one corresponding row in the derived table. If one row is ever deleted from either table, the corresponding row must also be deleted.

  - The base table probably has at least two tables that derive from it. The two derived tables have fields for different kinds of attributes for different kinds of things. The two derived tables refer to different variations of the general items that are tracked together in the base table.

  - No item that is represented in a base table would ever be represented in more than one of its derived tables.
    

    > [!NOTE]
    > <P>In Microsoft Dynamics AX the system prevents any individual row in a base table from being associated to more than one derived table (at any one level in the inheritance hierarchy). This is an implementation choice that was made by the Microsoft Dynamics AX product team.</P>



  - The derived table is not meant for performance tuning of the physical database, such as placing an image column in its own table.
    

    > [!NOTE]
    > <P>In cases where a table is not involved in any inheritance relationship, there might be a small performance penalty if you set its <STRONG>SupportsInheritance</STRONG> property to <STRONG>Yes</STRONG>.</P>



## Example Data to Illustrate Table Inheritance

This section uses example data to illustrate an effective use of table inheritance.

### ![Gg843731.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843731.collapse_all(en-us,AX.60).gif")Same Field Names are a Clue

A pet store has several pets for sale, including dogs and birds. The store uses Microsoft Dynamics AX to track its pet inventory. The store owner envisions a database that has tables named TabPetDog and TabPetBird. The store owner creates a list of all the fields to track for each dog, and for each bird. The following table displays the two lists.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Pet dog properties</p></th>
<th><p>Pet bird properties</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>BirthDate</p>
<p>Name</p>
<p>NumberOfTeeth</p></td>
<td><p>BirthDate</p>
<p>Name</p>
<p>BeakColor</p></td>
</tr>
</tbody>
</table>


The store owner notices that the lists for dogs and birds start with the same two properties, BirthDate and Name. This overlap is a clue that there might be a third table that is less specific than TabPetDog and TabPetBird. The store owner realizes he needs to add the TabPet table. The two overlapping fields should be moved to TabPet.

The store owner settles on a design that has one base table named TabPet, and two derived tables that are named TabPetDog and TabPetBird that each extend TabPet.

### ![Gg843731.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843731.collapse_all(en-us,AX.60).gif")Test Data for Three Tables

This section shows test data for the three tables TabPet, TabPetDog, and TabPetBird.

The RecId system field has been added to each table as the primary key. Also, the system field InstanceRelationTypeId has been added to the base table, and its values refer to derived tables. Its value 50011 refers to TabPetDog, and 50012 refers to TabPetBird.

#### ![Gg843731.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843731.collapse_all(en-us,AX.60).gif")TabPet Test Data

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>PetBirthDate</p></th>
<th><p>PetName</p></th>
<th><p>InstanceRelationTypeId</p></th>
<th><p>RecId</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1988-07-20</p></td>
<td><p>Spot</p></td>
<td><p>50011</p></td>
<td><p>1234567890</p></td>
</tr>
<tr class="even">
<td><p>2008-02-29</p></td>
<td><p>Tweety</p></td>
<td><p>50012</p></td>
<td><p>1234567891</p></td>
</tr>
<tr class="odd">
<td><p>2005-03-21</p></td>
<td><p>Polly</p></td>
<td><p>50012</p></td>
<td><p>1234567892</p></td>
</tr>
<tr class="even">
<td><p>2005-04-22</p></td>
<td><p>Lassie</p></td>
<td><p>50011</p></td>
<td><p>1234567893</p></td>
</tr>
<tr class="odd">
<td><p>2004-05-23</p></td>
<td><p>Rex</p></td>
<td><p>50011</p></td>
<td><p>1234567894</p></td>
</tr>
</tbody>
</table>


Each value in the TabPet.RecId column must match a RecId value in one of the tables that derives from TabPet.

#### ![Gg843731.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843731.collapse_all(en-us,AX.60).gif")TabPetDog Test Data

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>NumberOfTeeth</p></th>
<th><p>RecId</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>42</p></td>
<td><p>1234567890</p></td>
</tr>
<tr class="even">
<td><p>41</p></td>
<td><p>1234567893</p></td>
</tr>
<tr class="odd">
<td><p>38</p></td>
<td><p>1234567894</p></td>
</tr>
</tbody>
</table>


#### ![Gg843731.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843731.collapse_all(en-us,AX.60).gif")TabPetBird Test Data

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>BeakColor</p></th>
<th><p>RecId</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>gray</p></td>
<td><p>1234567891</p></td>
</tr>
<tr class="even">
<td><p>red</p></td>
<td><p>1234567892</p></td>
</tr>
</tbody>
</table>


## See also

[Table Inheritance Overview](table-inheritance-overview.md)

[Walkthrough: Creating Base and Derived Tables](walkthrough-creating-base-and-derived-tables.md)

[How to: Use the UnitOfWork Class to Manage Database Transactions](how-to-use-the-unitofwork-class-to-manage-database-transactions.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

