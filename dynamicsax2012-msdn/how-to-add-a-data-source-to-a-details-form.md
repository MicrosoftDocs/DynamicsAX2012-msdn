---
title: 'How to: Add a Data Source to a Details Form'
TOCTitle: 'How to: Add a Data Source to a Details Form'
ms:assetid: ddc1c8ae-5b87-4b55-a121-d08d0ac5e803
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh528510(v=AX.60)
ms:contentKeyID: 37835257
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a Data Source to a Details Form [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to add a data source and a title data source to a details form. Before you add a data source you must first create the details form. For information about how to use a template to create a details form, see [How to: Create a Details Form](how-to-create-a-details-form.md).

The following steps show you how to add tables to the form data source and how to populate the data source properties of the form. You set the title data source to show two field values from the current record in the form title.

### To add tables to the form data source

1.  In the AOT, find the form to which you are adding a data source and expand the form node.

2.  Press Ctrl+D to open a second AOT window. Expand **Data Dictionary**, expand **Tables**, and then find the table you want to add as a form data source. Drag the table to the **Data Sources** node of the form.
    
    For example, the **Customers** form uses CustTable as the primary data source table.

3.  If you are creating a details form with lines, find and drag the table that contains the line information to the **Data Sources** node of the form. Click the **JoinSource** property and then click the name of the table that represents the primary data source for the form. Click the **LinkType** property and set the property to **Delayed**. For more information about how to configure the data source, see [How to: Join Parent/Child Data Sources for a Form](how-to-join-parent-child-data-sources-for-a-form.md).
    
    For example, the **Sales order** form uses SalesTable as the primary data source for the form. To supply information about the lines for each sales order, the **Sales order** form uses the SalesLine table. Notice how the **JoinSource** property of the **SalesLine** table in the form data source is set to **SalesTable**. This builds on the table relation that exists between the SalesTable and SalesLine tables.

4.  You can add related tables to the form data source. For more information about form data sources, see [Form Data Sources](form-data-sources.md).
    
    For example, the **Data Source** node of the **CustTable** form includes several tables that supply information about people and addresses associated with the customer record that appears in the **Customers** form. The **JoinSource** property of the tables that contain the related information all specify **CustTable**. In addition, there are table relations that define the relationship between **CustTable** and each related table.

### To specify the primary data source

1.  In the AOT that shows the form, expand **Designs**, right-click **Design**, and then click **Properties**.

2.  In the property sheet, click the **DataSource** property and then select the table you want to use as the primary data source for the form.
    
    For example, the **DataSource** property of the **Customers** form specifies **CustTable** as the primary data source for the form.

### To specify the title data source

1.  In the property sheet, click the **TitleDataSource** property and then select the table that contains the field values that you want to appear in the title bar of the form.
    
    For example, the **TitleDataSource** property of the **Customers** form specifies **CustTable**. As a result, the **Customers** form shows values in the form title for the fields specified by the **TitleField1** and **TitleField2** properties from **CustTable**.

2.  Right-click the form and then click **Save**.

After you add the data source you can add fields to the details form. For information about how to show field values on the form, see [How to: Add Fields to a Details Form](how-to-add-fields-to-a-details-form.md).

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

