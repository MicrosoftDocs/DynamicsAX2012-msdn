---
title: 'How to: Join Parent/Child Data Sources for a Form'
TOCTitle: 'How to: Join Parent/Child Data Sources for a Form'
ms:assetid: 82f8f47c-731c-4ca3-9408-a90e49da9abc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg862510(v=AX.60)
ms:contentKeyID: 35246153
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Join Parent/Child Data Sources for a Form 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use form data sources to join tables that create a parent/child relationship between data records. Typically, the records from the data sources are visually separated on the form. For example, you use a grid to list order records and a second grid that us lists the order lines associated with each order. The following steps show how to add and join the tables.

### To Join Data Sources that Create Parent/Child Links

1.  In the AOT, expand the form, and then expand the **Data Sources** node.

2.  Press CTRL-D to open a second AOT, expand **Data Dictionary**, and then expand **Tables**. The AOT lists the tables you can use as a form data source.

3.  To add tables to the form data source, drag two tables and drop each table on the **Data Sources** node of the form in the first AOT. The tables are added as data sources to the form.

4.  Identify the table you will use as the parent data source. The other table will be the child data source.

5.  Set the JoinSource property on the child data source to the name of the parent data source.

6.  Set the LinkType property of the child data source to Active, Passive, or Delayed.
    
    The LinkType property specifies how to update the child data source in response to a change in the parent data source.

7.  Create the form design, and then add fields from each data source to the form. Typically, you add two grid controls. One grid displays fields from the parent data source. The second grid displays fields from the child data source.

## See also

[Form Data Source Properties](form-data-source-properties.md)

[Using the display Method Modifier](using-the-display-method-modifier.md)

[Using the edit Method Modifier](using-the-edit-method-modifier.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

