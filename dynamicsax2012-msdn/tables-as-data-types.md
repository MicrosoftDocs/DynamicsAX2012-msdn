---
title: Tables as Data Types
TOCTitle: Tables as Data Types
ms:assetid: a22ce2df-7cbe-4ed2-91cd-3f97b3d84bf1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa849396(v=AX.60)
ms:contentKeyID: 35248326
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Tables as Data Types 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

All tables, which are created in MorphX by using the Application Object Tree (AOT), can be treated like class definitions (at least in all practical aspects) in the X++ programming language.

You can address fields and create methods on tables. The methods can be invoked on instances of the table.

To manipulate (read, update, insert, and delete) records in tables, you must declare at least one table variable, which can hold the record in focus.

Here are a few important differences between tables and objects:

  - You cannot allocate space for table variables—it is done implicitly.

  - Fields in table variables are public—you can reference them anywhere.

  - Fields in table variables can be referenced with expressions.

## Scope of Table Variables

Table variables are declared on the basis of the data dictionary in MorphX; that is, on the basis of the tables, which are declared in the AOT. In most respects, table variables can be considered objects. Contrary to objects, they are not allocated explicitly. Only a variable declaration is required.

All tables are compatible with the Common table in the same way that all objects are compatible with the Object class. Table variables, which are declared as common buffers, can be used to hold data from any table. You cannot access tables without table variables.

## Declaration of Table Variables

The principles for declaring table variables and objects are the same except for the allocation of space.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Table variable declaration</p></td>
<td><p>= ( tablename | common ) Variable { , Variable } ;</p></td>
</tr>
</tbody>
</table>


public void myMethod()

{

    // Declares and allocates space for one CustTable record

    CustTable custTable;

}


> [!NOTE]
> <P>It is a best practice to use the name of the table as the name of the variable, but with an initial lowercase letter.</P>



## Referencing Table Variables

The syntax for referencing fields in a table variable is:

RefTableVariable = Tablevariable.\[ ( expression ) | fieldname \]

The most widely used field reference is Tablevariable.Fieldname, for example custTable.AccountNo.

public void printAccountNo();

{

    CustTable custTable;

    ;

    print custTable.AccountNo;

}

The syntax, however, also allows various possibilities for referencing fields in records, for example by using the TableName.(FieldId) syntax. The following example prints the contents of the fields in the current record in the Customer table.
```X++  
    public void printCust()
    {
        int i, n, k;
        CustTable custTable;
        DictTable dictTable;
        ;
     
        dictTable = new DictTable(custTable.TableId);
        n = dictTable.fieldCnt();
     
        print "Number of fields in table: ", n;
        for(i=1; i<=n; i++)
        {
            k = dictTable.fieldCnt2Id(i);
            print "The ", dictTable.fieldName(k), 
                " field with Id=",k, " contains '", 
                custTable.(k), "'";
            pause;
        }
    }
```

> [!NOTE]
> <P>The previous example uses the fieldCnt and fieldCnt2Id methods. The fieldCnt method counts the number of fields in a table, while fieldCnt2Id returns the ID for a field number. For example, you can use the fieldCnt2Id method to find out that field number 6 in a table has the ID 54. It is necessary to perform this conversion because it is not guaranteed that the IDs of the fields in a table are consecutive.</P>



## Automatic Conversion

There is no automatic conversion, but table variables that are declared as Common can hold data from any table.

## See also

[Classes as Data Types](classes-as-data-types.md)

[Composite Data Types](composite-data-types.md)

[Extended Data Types (EDTs)](extended-data-types-edts.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

