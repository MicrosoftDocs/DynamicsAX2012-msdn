---
title: 'How to: Create a Simple List and Details Form'
TOCTitle: 'How to: Create a Simple List and Details Form'
ms:assetid: 80b41cc3-65f2-459e-8f0d-708d877b5d47
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh538483(v=AX.60)
ms:contentKeyID: 39508916
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Simple List and Details Form [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to use the AOT and a template to create a simple list and details form. You use a simple list and details form to view, update, create, and delete the following types of records:

  - Records that show data from a reference table.

  - Records that have more than six fields.

  - Records that have a parent and child relationship between fields that appears on the form.

If the record type you want to appear in the form has fewer than six columns, consider using a simple list form. For information about how to create a simple list form, see [How to: Create a Simple List Form](how-to-create-a-simple-list-form.md). For more information about simple list and simple list and details forms, see [Simple List Forms Overview](simple-list-forms-overview.md). To create a simple list and details form, follow these steps.

### To create the simple list and details form

1.  In the AOT, right-click **Forms**, click **New Form from template**, and then click **SimpleListDetails**. The template creates a new form.

2.  Right-click the form and then click **Properties**. In the property sheet, click **Name**, and then type a name that uniquely identifies the form.

3.  Expand the form, expand **Designs**, and then click **Design**. In the properties sheet, find the **Style** property and verify that the value is set to **SimpleListDetails**.

4.  Click the **Caption** property and then select the label that represents the name that you want to appear in the title bar of the form.
    

    > [!NOTE]
    > <P>The form title should be plural. You often can use the same label that is specified by the <STRONG>Label</STRONG> property of the table that you use as the form data source.</P>



### To add the data source

1.  Press CTRL+D to open a second AOT window.

2.  Expand **Data Dictionary**, expand **Tables**, and then find the table you want to use with the form.

3.  Drag the table onto the **Data Sources** node of the form that you created in the previous steps.

4.  In the AOT window that shows the form, click the **Design** node. In the properties sheet, click **Datasource** and then select the table you will use as the data source for the grid control. Click the **TitleDatasource** property and verify that the property value is empty.

5.  Expand the **Design** node. You should see controls for the action pane strip, the page title group, the custom filter group, and the body group. Click the **ActionPane** control. In the properties sheet, click **DataSource** and then select the table that you specified in the previous step.
    

    > [!WARNING]
    > <P>If the form was not created based on a template, or the form has changed template values, the names and sequence specified in this and the remaining steps might be different.</P>



### To add fields to the grid

1.  Expand the **Design** node, expand the **Body** group, and then expand the **GridContainer** group. You should see the **Grid** control.

2.  Click the grid. In the properties sheet for the grid control, click the **DataSource** property and then click the table you want to use as the data source for the grid. Select the table that includes the fields you want to appear in the grid.

3.  Verify that the grid does not support the selection of multiple records. First, click the **MultiSelect** property and verify that the property value is set to **No**. Click the **ShowRowLabels** property and verify that the property value is set to **No**.

4.  Right-click the **Data Sources** node of the form to add a field to the grid, and then click **Open New Window**. The form data source appears in a separate window.

5.  In the window that shows the form data sources, expand the node for the table that you specified in the earlier step, and then expand **Fields**.

6.  Drag the field or field group that you want to appear in the form onto the grid control. You should not add more than four fields to the grid.

### To add the splitter between the grid and details

1.  Expand the **Design** node, expand the **Body** group, and then click the **VSplitter** group.

2.  In the property sheet, click the **Style** property and verify the value is set to **SplitterVerticalContainer**.
    

    > [!NOTE]
    > <P>The template adds SysFormSplitter_X verticalSplitter; to the ClassDeclaration method of the form. The template adds verticalSplitter = new SysFormSplitter_X(VSplitter, GridContainer, element, 300); to the init method of the form. These statements let users use the splitter control.</P>



### To add fields to the details header group

1.  Expand the **Design** node, expand the **Body** group, and then expand the **DetailsContainer** group. You should see a group control named **DetailsHeader**.
    

    > [!NOTE]
    > <P>The details header is an optional section for a simple list and details form. If the details tab shows the fields that appear in the grid and you do not have FastTabs, you do not need the details header group. If the <STRONG>DetailsHeader</STRONG> group is empty, the details header does not appear on the form.</P>



2.  In the window that shows the form data sources, expand the node for the table that you chose as the form data source, and then expand **Fields**.

3.  Drag each field that you want to appear in the details header group. You should add fields that identify the record. Typically, you use the same fields that appear in the grid.

### To add fields to the details tab

1.  Expand the **Design** node, expand the **Body** group, expand the **DetailsContainer** group, and then click **DetailsTab**. In the property sheet for the tab control, click the **Style** property, and then select one of the following values.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property value</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>FastTabs</strong></p></td>
    <td><p>Select this value when you will add more fields than can appear on a single tab page.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Tabs</strong></p></td>
    <td><p>Select this value when all the fields can appear on a single tab page.</p></td>
    </tr>
    </tbody>
    </table>


2.  Expand **DetailsTab** and then click the tab page control named **TabPage**.

3.  In the property sheet, click the **Caption** property and specify the label you want to appear as the title for the tab.

4.  In the window that shows the form data sources, expand the node for the table that you chose as the form data source, and then expand **Fields**.

5.  Drag a field group or each field that you want to appear onto the tab page control.

6.  To add more FastTabs, right-click **DetailsTab**, click **New Control**, and then click **TabPage**. A tab page control is added to the tab. To add fields to that FastTab, click the tab page control, and then repeat the previous three steps in this procedure. For more information about how to add a FastTab and how to specify the summary fields, see [How to: Add FastTabs to a Form](how-to-add-fasttabs-to-a-form.md).

7.  Right-click the form and then click **Save**.

To view the form, right-click the form and then click **Open**. To close the form, click the **Close** button in the status bar.

You will see the splitter when you have fields in both the grid and details tab of the form. If either is empty, the splitter does not appear on the form.

If the simple list and details form displays dependent data (the form opens in the context of another record), you might want to add a title group to the form. For information about how to add a title group, see [How to: Add a Page Title Group to a Simple List Form](how-to-add-a-page-title-group-to-a-simple-list-form.md).

## See also

[How to: Customize the Action Pane Strip](how-to-customize-the-action-pane-strip.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

