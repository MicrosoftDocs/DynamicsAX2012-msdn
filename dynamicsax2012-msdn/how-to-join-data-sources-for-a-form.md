---
title: 'How to: Join Data Sources for a Form'
TOCTitle: 'How to: Join Data Sources for a Form'
ms:assetid: 63a9b53b-d01e-4137-8c0c-a053313fa888
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa608858(v=AX.60)
ms:contentKeyID: 35244626
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Join Data Sources for a Form 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to create a join relationship between two tables in the **Data Sources** node of a form. The following steps describe how to add and join the tables.

### To Join Data Sources as a Single Data Source

1.  In the AOT, expand the form, and then expand the **Data Sources** node.

2.  Press CTRL-D to open a second AOT, expand **Data Dictionary**, and then expand **Tables**. The AOT lists the tables you can use as a form data source.

3.  To add tables to the form data source, drag two tables and drop each table on the **Data Sources** node of the form in the first AOT. The tables are added as data sources to the form.

4.  Identify the table you will use as the primary data source. The other table will be the secondary data source.

5.  Click the secondary data source, and set the JoinSource property to the name of the primary data source.

6.  Set the LinkType property of the secondary data source to InnerJoin, OuterJoin, ExistJoin, or NotExistJoin.

7.  Create the form design, and add controls that display fields from the joined data sources. Typically, you use a grid control to display the data from joined data sources.

8.  You might have to add code that updates data in shared fields. This step depends upon the design of your form and might not be required for all forms with joined data sources.
    
    For example, you create a join between two tables using Table1.Field1 and Table2.Field2. Since the fields are identical, only Table1.Field1 appears in the form. However, a change to Table1.Field1 on the form does not automatically update the value of Table2.Field2. To update Table2.Field2, add code to the modified method of Table1.Field1 that updates the value of Table2.Field2.

## See also

[Form Data Source Properties](form-data-source-properties.md)

[Using the display Method Modifier](using-the-display-method-modifier.md)

[Using the edit Method Modifier](using-the-edit-method-modifier.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

