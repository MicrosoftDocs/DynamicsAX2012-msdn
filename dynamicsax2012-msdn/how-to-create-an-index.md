---
title: 'How to: Create an Index'
TOCTitle: 'How to: Create an Index'
ms:assetid: 5c412c46-724b-4498-ab42-51725f15c71a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa607289(v=AX.60)
ms:contentKeyID: 35244401
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create an Index 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A table index is a database object that you can create in the Application Object Tree (AOT) to optimize access to table records.


> [!NOTE]
> <P>It is recommended that you define only as many indexes as you need for optimum database performance.</P>



To specify an index in a select statement, use the index keyword. For more information, see [Select Statement Syntax](select-statement-syntax.md).

To manage changes to AOT objects, a version control system is available. For more information, see [Version Control System](version-control-system.md).

## Create an Index

1.  In the AOT, locate the table that you want to add an index to, right-click the **Indexes** node, and then click **New Index**.

2.  Right-click the new index, and then click **New Field**.

3.  Right-click the field you added in step 3, click **Properties**, and then select a field from the **DataField** property list.
    
    Repeat steps 2 - 3 to add more fields to the index.
    
    The order of the fields determines the sorting order of the records. If a sorting conflict occurs, the data is sorted on the next field.
    

    > [!NOTE]
    > <P>Any field of type String is transformed into lowercase.</P>



4.  Right-click the new index, and then click **Properties**.

5.  Specify whether the index is unique or non-unique by doing one of the following:
    
      - To specify that the index is a non-unique index, confirm that the **AllowDuplicates** property is set to **Yes**. It is recommended that you create non-unique indexes for optimum database performance.
        

        > [!NOTE]
        > <P>If you include a <STRONG>RecId</STRONG> field in an index, the index will be unique. When you include this field and set the property to <STRONG>Yes</STRONG>, the Microsoft Dynamics AX compiler displays a warning.</P>

    
      - To specify that the index is unique, set the **AllowDuplicates** property to **No**. When the index is unique, you cannot insert records with duplicate key values. A warning is issued to the user if he attempts to insert records with duplicate values.

6.  To disable the index, set the **Enabled** property to **No**. When you disable an index, it is deleted from the database.
    
    You can also delete an index by right-clicking the index, and then clicking **Delete**.

7.  Modify additional properties as needed.

## See also

[How to: Create Tables](how-to-create-tables.md)

[Table Index Properties](https://msdn.microsoft.com/en-us/library/aa881522\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

