---
title: Use the Table Browser to View, Add, Modify, or Delete Records
TOCTitle: Use the Table Browser to View, Add, Modify, or Delete Records
ms:assetid: 89402b55-02ea-40bc-ad0e-0774b1655426
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb314838(v=AX.60)
ms:contentKeyID: 35246304
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Use the Table Browser to View, Add, Modify, or Delete Records [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

After you have created a forms interface and entered data in a table, you can use the table browser to view and edit data.

## Open the Table Browser

1.  Locate the table that you want to view in the Application Object Tree (AOT).

2.  Right-click the table and then click **Add-Ins** \> **Table browser**. Alternatively, you can right-click the table and select **Open**.
    
    The table browser displays data from all fields in the table.
    

    > [!NOTE]
    > <P>The table browser does not support the display of fields of type container. This means that even when you want to see all fields, container fields are excluded. In addition, any field that has its Visible property set to No will not display in the table browser.</P>



Click the **Autoreport** radio button to limit the fields to those defined in the table's **AutoReport** field group. Click the **All Fields** radio button to toggle back to displaying all fields. Any table and field validation that is defined is enforced when you edit in the table browser.

You can add, modify, and delete records in the table browser but only when **All Fields** is selected. To add a row in the table browser, click CTRL+N and enter data in the new row. To delete a row, click ALT+F9.

You can invoke the table browser anywhere a table is used as a data source: in a form, in a report, or in a query.

Property settings on a table or a field may prevent you from editing or deleting in the table browser. If you cannot edit or delete data, check the table property setting for MaxAccessMode and the field property setting for AllowEdit. The MaxAccessMode property defines the maximum level of access available on the table. For more information about table properties, see [Table Properties](https://msdn.microsoft.com/en-us/library/aa871620\(v=ax.60\)). For more information about field properties, see [Table Field Properties](https://msdn.microsoft.com/en-us/library/aa577032\(v=ax.60\)).

You can also use the table browser to view the contents of system tables. System tables are located in the **System Documentation\\Tables** node in the AOT.

## Run SQL Statements

The table browser can be used to run SQL statements. Enter the SQL statement in the text box below the grid and then click the **Execute** button to run the SQL against the data source. This feature is useful for testing SQL statements used in your code. For example, when browsing the CustTable table, the following statement displays only the customers who are in customer group 40.

select \* from custTable where custTable.custGroup==’40’

## See also

[Table Browser Form](https://msdn.microsoft.com/en-us/library/aa584230\(v=ax.60\))

[Table Properties](https://msdn.microsoft.com/en-us/library/aa871620\(v=ax.60\))

[Table Field Properties](https://msdn.microsoft.com/en-us/library/aa577032\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

