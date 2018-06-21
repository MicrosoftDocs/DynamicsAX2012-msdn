---
title: Data Operations in X++ on Base and Derived Tables
TOCTitle: Data Operations in X++ on Base and Derived Tables
ms:assetid: 3dd97552-62a3-46a6-b61f-9e8f7e9127ef
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg845084(v=AX.60)
ms:contentKeyID: 35242938
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Data Operations in X++ on Base and Derived Tables [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, when you insert a row into a derived table, the system automatically inserts the required base table row. When you delete a row from a base table, the system automatically deletes dependent rows from the derived table. If a problem prevents any one of these inserts or deletes from succeeding, the system rolls back the entire transaction, so that the data remains unchanged.

## Background for this Walkthrough

The following topics provide background for this topic:

  - [Walkthrough: Creating Base and Derived Tables](walkthrough-creating-base-and-derived-tables.md)

  - [Data Selection and Manipulation](data-selection-and-manipulation.md)

## Structure of the Demonstration Tables

The code examples in this walkthrough refer to the following two tables, TabPet and TabPetDog.

### ![Gg845084.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845084.collapse_all(en-us,AX.60).gif")TabPet Base Table

The following table shows the fields of the TabPet base table.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Field name</p></th>
<th><p>Data type</p></th>
<th><p>Mandatory</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>InstanceRelationTypeId</p></td>
<td><p>int64</p></td>
<td><p><strong>No</strong></p></td>
<td><p>The system requires that you add a mandatory int64 field to each base table. You can name the field anything, but you must assign the field to the <strong>InstanceRelationType</strong> property on the base table.</p></td>
</tr>
<tr class="even">
<td><p>PetBirthDate</p></td>
<td><p>date</p></td>
<td><p><strong>Yes</strong></p></td>
<td><p>Inserts into the derived table can specify a value for this field in the base table. Specifying a value prevents the system from leaving the field value empty when it automatically inserts a row into this base table.</p></td>
</tr>
</tbody>
</table>


### ![Gg845084.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845084.collapse_all(en-us,AX.60).gif")TabPetDog Derived Table

The following table shows the fields of the TabPetDog derived table.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Field name</p></th>
<th><p>Data type</p></th>
<th><p>Mandatory</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NumberOfTeeth</p></td>
<td><p>int</p></td>
<td><p><strong>Yes</strong></p></td>
<td><p>No special fields are required on the derived table.</p></td>
</tr>
</tbody>
</table>


## Insert Cascade from Derived to Base

This section describes a code example that contains insert statements for the derived table. These statements do not mention the base table, but the system automatically inserts the necessary base row into the base table. Each row in the derived table is dependent on a corresponding row in the base table.

The code example also shows a select statement that reads from the base table. Some of the data that was inserted by using a buffer variable for the derived table can be read from the base table.

### ![Gg845084.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845084.collapse_all(en-us,AX.60).gif")Call Patterns in the Code Example

The following table shows the major statements that are made in the code example.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++ statement</p></th>
<th><p>Comment</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>delete_from tPet;</p></td>
<td><p>Deletes all the rows from the base table in one operation. This delete cascades to delete all the rows in the derived table TabPetDog.</p></td>
</tr>
<tr class="even">
<td><p>tDog.PetBirthDate = 20\07\1988;</p></td>
<td><p>In the AOT, the field PetBirthDate is defined on the TabPet table, not on the TabPetDog table. The field is inherited by the TabPetDog table, even though physically it exists on only the TabPet table in the underlying database.</p></td>
</tr>
<tr class="odd">
<td><p>tDog.insert();</p></td>
<td><p>This insert method adds a row to the base table and to the derived table that is referenced by the tDog variable.</p></td>
</tr>
<tr class="even">
<td><p>while select * from tPet</p>
<p>  { anyt = tPet.getFieldValue(&quot;PetBirthDate&quot;); }</p></td>
<td><p>These statements show that the PetBirthDate field can be read from the base table. The AOT shows this field is defined on the TabPet base table.</p></td>
</tr>
<tr class="odd">
<td><p>while select * from tDog</p>
<p>  { anyt = tDog.getFieldValue(&quot;PetBirthDate&quot;); }</p></td>
<td><p>These statements show that the PetBirthDate field can be read from the TabPetDog derived table. The AOT shows this field is defined on the TabPet base table.</p></td>
</tr>
</tbody>
</table>


The following code example shows that an insert into the derived table automatically also inserts into the base table. The system rejects the entire transaction if either insert fails.

    static void InsertCascadeMandatoryIssueJob3I(Args _args)
    {
        TabPet tPet;
        TabPetDog tDog;
        anytype anyt;
        date dPetBirthDate;
        str sPetBirthDate, sNumberOfTeeth;
        int nNumberOfTeeth;
    
     // Local function.
     str Date2StrEasyLocal(date _date)
     {
            return ( date2Str
                (_date,
                321, // YMD
                DateDay::Digits2,
                DateSeparator::Hyphen,
                DateMonth::Digits2,
                DateSeparator::Hyphen,
                DateYear::Digits4) );
     }
    
        // Ensure both tables start empty.
        //This delete cascades to delete all rows from tDog also.
        delete_from tPet;
    
        // Inserts into the derived table,
        // which cascade to the base table.
        tDog.PetBirthDate = 20\07\1988;
        tDog.NumberOfTeeth = 42;
        tDog.insert();
    
        tDog.PetBirthDate = 29\02\2008;
        tDog.NumberOfTeeth = 39;
        tDog.insert();
    
        info("--- List base table rows after the inserts.");
        while select * from tPet
        {
            anyt = tPet.getFieldValue("PetBirthDate");
            dPetBirthDate = any2Date(anyt);
            sPetBirthDate = Date2StrEasyLocal(dPetBirthDate);
    
            info("After insert, base table variable has: " + sPetBirthDate);
        }
        info("--- List derived table rows after the inserts.");
        while select * from tDog
        {
            anyt = tDog.getFieldValue("PetBirthDate");
            dPetBirthDate = any2Date(anyt);
            sPetBirthDate = Date2StrEasyLocal(dPetBirthDate);
    
            anyt = tDog.getFieldValue("NumberOfTeeth");
            nNumberOfTeeth = any2Int(anyt);
            sNumberOfTeeth = int2Str(nNumberOfTeeth);
    
            info("After insert, the derived table variable has: "
                + sPetBirthDate + " , " + sNumberOfTeeth);
        }
    }

The following output to the **Infolog** is generated by the previous program.

Message (06:22:14 pm)

\--- List base table rows after the inserts.

After insert, base table variable has: 1988-07-20

After insert, base table variable has: 2008-02-29

\--- List derived table rows after the inserts.

After insert, the derived table variable has: 1988-07-20 , 42

After insert, the derived table variable has: 2008-02-29 , 39

## Data in the Demonstration Tables

This section describes the data that is inserted into the base and derived tables by the previous code example. The values for InstanceRelationTypeId and RecId can vary between test runs, but they match among the tables in any particular run.

### ![Gg845084.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845084.collapse_all(en-us,AX.60).gif")Rows in the Base Table

The following table shows the rows that are inserted into the TabPet base table. The value in the InstanceRelationTypeId field is the system ID of the derived table.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>InstanceRelationTypeId</p></th>
<th><p>PetBirthDate</p></th>
<th><p>RecId</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>50011</p></td>
<td><p>1988-07-20</p></td>
<td><p>111222332</p></td>
</tr>
<tr class="even">
<td><p>50011</p></td>
<td><p>2008-02-29</p></td>
<td><p>111222333</p></td>
</tr>
</tbody>
</table>


### ![Gg845084.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845084.collapse_all(en-us,AX.60).gif")Rows in the Derived Table

The following table shows the rows that are inserted into the TabPetDog derived table.

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
<td><p>111222332</p></td>
</tr>
<tr class="even">
<td><p>39</p></td>
<td><p>111222333</p></td>
</tr>
</tbody>
</table>


## Delete Cascade in Both Directions

This section describes the next code example, which continues where the previous example stops. This next example demonstrates the following cascading deletes:

  - Base to derived – an X++ SQL delete\_from statement that deletes all base table rows would cascade to delete all rows in all derived tables.

  - Derived to base – an X++ SQL delete\_from statement on the derived table can cascade to delete rows from the base table. If many tables derive directly from the same base table, the delete of all rows from one derived table would not affect base rows that are associated with other derived tables.
    

    > [!NOTE]
    > <P>This is different than the delete cascade behavior that occurs when you delete from a foreign key table. The delete of rows that contain a foreign key does not cascade to delete any rows from the primary key table.</P>



<!-- end list -->

    static void DeleteCascadeJob3D(Args _args)
    {
        TabPet tPet;
        TabPetDog tDog;
    
        // Delete_from statements, with exactly one row identified
        // in each Where clause.
    
        info("--- Delete from base, cascades to delete to derived.");
        delete_from tPet where tPet.PetBirthDate == 29\02\2008;
    
        info("--- Delete from derived, cascades delete to base.");
        delete_from tDog where tDog.NumberOfTeeth == 42;
    
        // Verify the tables are empty.
    
        info("--- List base table rows after the delete (should be none).");
        while select * from tPet
        {
            error("Error, the base table should be empty.");
        }
        info("--- List derived table rows after the delete (should be none).");
        while select * from tDog
        {
            error("Error, the derived table should be empty.");
        }
    }

The following output to the **Infolog** is generated by the previous program.

Message (09:55:54 am)

\--- Delete from derived, cascades delete from to base.

\--- Delete from base, cascades to delete from derived.

\--- List base table rows after the delete (should be none).

\--- List derived table rows after the delete (should be none).

## See also

[Table Inheritance Overview](table-inheritance-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

