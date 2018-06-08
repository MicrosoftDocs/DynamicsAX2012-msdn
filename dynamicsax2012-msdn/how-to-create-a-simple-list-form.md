---
title: 'How to: Create a Simple List Form'
TOCTitle: 'How to: Create a Simple List Form'
ms:assetid: f2fd8824-30fb-4e3d-add0-fca0e4e9fe52
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh538488(v=AX.60)
ms:contentKeyID: 39508921
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Simple List Form 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how you use that AOT and a form template to create a simple list form. You use a simple list form to view, update, create, and delete the following types of data:

  - Records that show data from a reference table.

  - Records that have six or less fields.

  - Records that do not have a parent and child relationship between any of the fields that appears on the form.

If your record type has more than six fields, consider using a simple list and details form. For information about how to create a simple list and details form, see [How to: Create a Simple List and Details Form](how-to-create-a-simple-list-and-details-form.md). For more information about simple list and simple list and details forms, see [Simple List Forms Overview](simple-list-forms-overview.md). To create a simple list form, follow these steps.

### To create the simple list form

1.  In the AOT, right-click **Forms**, click **New Form from template**, and then click **SimpleList**. The template creates a new form.

2.  Right-click the form and then click **Properties**. In the property sheet, click **Name**, and then type a name that uniquely identifies the form.

3.  Expand the form, expand **Designs**, and then click **Design**. In the property sheet, find the **Style** property and verify that the value is set to **SimpleList**.

4.  Click the **Caption** property and then select a label that represents the name that you want to appear in the title bar of the form.
    

    > [!NOTE]
    > <P>The form title should be plural. Many times you can use the same label that is specified by the <STRONG>Label</STRONG> property of the table in the form data source.</P>



### To add the data source

1.  Press CTRL+D to open a second AOT window.

2.  Expand **Data Dictionary**, expand **Tables**, and then find the table you want to use with the form.

3.  Drag the table onto the **Data Sources** node of the form that you created in the previous procedure.

4.  In the AOT window that shows the form, click the **Design** node. In the property sheet, click **Datasource** and select the same table you will use as the data source for the grid control. Click the **TitleDatasource** property and verify that the property value is empty.

5.  Expand the **Design** node. You should see controls for the action pane strip, the page title group, the custom filter group, and the grid container group. Click the **ActionPane** control. In the property sheet, click **DataSource** and select the table that you specified in the previous step.

### To add fields to the grid

1.  In the AOT window that shows the form, find the **Design** node, expand the **GridContainer** group, and then click the **Grid** control.

2.  In the properties sheet for the grid control, click the **DataSource** property and then click the table you want to use as the data source for the grid. Select the table that includes the fields you want to appear in the grid.

3.  Verify that the form does not support the selection of multiple records. First, click the **MultiSelect** property and verify that the property value is set to **No**. Click the **ShowRowLabels** property and verify that the property value is set to **No**.

4.  To add fields to the grid, right-click the **Data Sources** node of the form and then click **Open New Window**. The form data source appears in a separate window.

5.  In the window that shows the form data source, find and expand the node for the table that contains the fields that you want to appear in the grid, and then expand **Fields**.

6.  Click the field or field group that you want to appear in the form and drag it onto the grid control. Repeat this step for each field or field group that you want to appear in the form.
    

    > [!TIP]
    > <P>If you want to use the form to create records, you must add all the required fields for that type of record to the grid.</P>



7.  Right-click the form and then click **Save**.

To view the simple list, right-click the form and then click **Open**. You should see the form that you created. To close the form, click the **Close** button in the status bar.

If the simple list form displays dependent data (the form opens in the context of another record), you should add a title group to the form. For information about how to add a title group, see [How to: Add a Page Title Group to a Simple List Form](how-to-add-a-page-title-group-to-a-simple-list-form.md).

## See also

[How to: Customize the Action Pane Strip](how-to-customize-the-action-pane-strip.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

