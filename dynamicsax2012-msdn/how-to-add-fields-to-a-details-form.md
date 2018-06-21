---
title: 'How to: Add Fields to a Details Form'
TOCTitle: 'How to: Add Fields to a Details Form'
ms:assetid: fc738a39-a7c7-48f4-a18c-a92824b78fb5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh528514(v=AX.60)
ms:contentKeyID: 37835261
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add Fields to a Details Form [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to add fields to the editable grid and the header of a details form. All details forms have two view modes that you can use to create, view, or update a record. The details view displays the header which contains the collection of fields associated with a single record. The grid view displays a subset of the header fields, but in a grid control with similar records. You use buttons in the status bar or action pane to switch between the details view and the grid view. When you create or customize a details form, consider whether the field can appear in the following views.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>View</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Details</p></td>
<td><p>The view that shows a collection of fields about a specified record. You typically use the header to create, view, or update a single record. The header view uses one or more FastTabs to organize and display groups of fields.</p></td>
</tr>
<tr class="even">
<td><p>Editable grid</p></td>
<td><p>A grid that lists records. You should use the grid to show just the fields required to create or update a record. You typically use the editable grid to quickly find and update a record.</p></td>
</tr>
</tbody>
</table>


To follow these steps, you must first add one or more tables to the **Data Sources** node of the form. For information about how to add a data source to a form, see [How to: Add a Data Source to a Details Form](how-to-add-a-data-source-to-a-details-form.md).


> [!WARNING]
> <P>The following steps assume that you created the details form based on the <STRONG>DetailsFormMaster</STRONG> or <STRONG>DetailsFormTransaction</STRONG> template. If you did not use the template or you changed the values supplied by the template, the location and names of the tabs, and tab pages, in the <STRONG>Design</STRONG> node may be different. For information about how to create a details form that is based on a template, see <A href="how-to-create-a-details-form.md">How to: Create a Details Form</A>.</P>



## Adding Fields to the Editable Grid

If you used the template to create the form, the template adds the tab, tab page, and grid. To complete the form, you add fields to the grid. The grid should contain the fields required to create or update a record. The editable grid is intended to help you quickly find and update a record. Try to minimize the number of fields that appear in the grid. The following steps show how to add fields to the grid.

### To specify the data source for the grid

1.  Expand **Design**, expand **Tab**, expand **TabPageGrid**, expand **GridGroup**, and then click **HeaderGrid**.

2.  In the property sheet, click the **DataSource** property and then select the table you want to use as the data source for the grid.
    
    For example, the grid that appears on the **Customers** form specifies **CustTable** as the **DataSource**.

### To add fields to the grid

1.  In the AOT window that shows the data source tables, expand the table that you specified as the data source for the grid. Expand the **Fields** node for the table.

2.  Click a field and drag that field onto the grid. Repeat this step for each field that you want to appear in the grid.

3.  Right-click the form and then click **Save**.

To view the details form, right-click the form, and then click **Open**. To see the editable grid view, click the **Grid View** button in the status bar of the form.

## Adding Fields to the Header

If you used the template to create the form, the template adds several tabs, and tab page controls that create the basic components of the header. The fields you added to the grid should also be added to the header. However, you can add other fields to the header that provide additional information about the specified record. The following steps show you how to add fields to an existing tab page in the header of the form.

### To add fields to the header tab page

1.  Right-click the **Data Sources** node of the form and then click **Open New Window**. The data source opens in a separate AOT window. Expand the table nodes in the window to show the fields you want to add to the form.

2.  In the AOT window that shows the form, locate the tab page where you want to add fields. The location of the tab page for the header can vary by the form design style you specified for the details form.
    
    For example, the following table shows how to find the **HeaderGeneral** tab page that the template creates for each type of details form. To get the form design style for a form, view the **Style** property of the **Design** node.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Form design style</p></th>
    <th><p>Location</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>DetailsFormMaster</strong></p></td>
    <td><p>Expand <strong>Design</strong>, expand <strong>Tab</strong>, expand <strong>TabPageDetails</strong>, and then expand <strong>HeaderDetailsTab</strong>. You should see the <strong>HeaderGeneral</strong> tab page.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>DetailsFormTransaction</strong></p></td>
    <td><p>Expand <strong>Design</strong>, expand <strong>Tab</strong>, expand <strong>TabPageDetails</strong>, expand <strong>DetailsTab</strong>, expand <strong>HeaderView</strong>, and then expand <strong>HeaderDetailsTab</strong>. You should see the <strong>HeaderGeneral</strong> tab page.</p></td>
    </tr>
    </tbody>
    </table>


3.  To add a field or field group, drag a field or field group from the AOT window that lists fields to the tab page. Repeat this step for each field or field group that you want to appear in the form.

4.  To organize and label groups of fields, you can add one or more **Group** controls. You can use the **Caption** property of the group to label the collection of fields that appear in the group. To populate a group, you drag fields onto the group control.

You might want to add tabs to the header of a details form. For information about how to add a FastTab to the form, see [How to: Add a FastTab to a Details Form](how-to-add-a-fasttab-to-a-details-form.md).

## See also

[Details Form User Experience Guidelines](details-form-user-experience-guidelines.md)

[Details Form with Lines User Experience Guidelines](details-form-with-lines-user-experience-guidelines.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

