---
title: 'How to: Customize the Line View of a Details Form with Lines'
TOCTitle: 'How to: Customize the Line View of a Details Form with Lines'
ms:assetid: c5a5fcf4-a51f-4699-80fb-fb4b6b69f544
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh528508(v=AX.60)
ms:contentKeyID: 37835255
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Customize the Line View of a Details Form with Lines 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The details form with lines contains a header and the corresponding lines. The action pane of a details form with lines includes two buttons that you use to switch between the header view (which displays all of the header) and the lines view (which displays a partial header and the corresponding lines). The following procedures show you how to customize the lines view. The lines view has the following components:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Line header</p></td>
<td><p>A FastTab that shows the fields that describe the record. You add the fields that are required to create the transaction and other fields that directly affect the lines that appear in the form.</p></td>
</tr>
<tr class="even">
<td><p>Lines</p></td>
<td><p>A grid that lists the lines that are associated with the record shown in the header. Typically, the fields that appear in the grid are the fields you use to create a new line.</p>
<p>Use the lines grid to show all the fields that are required columns to create a line item. You can add other fields that provide relevant information.</p></td>
</tr>
<tr class="odd">
<td><p>Line details</p></td>
<td><p>A FastTab that shows additional information about the header or the highlighted record in the grid. For information about how to customize <strong>Line details</strong>, see <a href="how-to-add-line-details-information-to-a-details-form-with-lines.md">How to: Add Line Details Information to a Details Form with Lines</a>.</p></td>
</tr>
</tbody>
</table>


This procedure assumes that you used the **DetailsFormTransaction** template to create the form. For information about how to create the form, see [How to: Create a Details Form](how-to-create-a-details-form.md). In addition, it is assumed that you have added tables to the form data source that supports the header and lines relationship. For information about how to create the data source for the form, see [How to: Add a Data Source to a Details Form](how-to-add-a-data-source-to-a-details-form.md).

The details form with lines also includes a header view that provides additional information about the record that appears in the header of the line view. For information about how to add fields to the header view, see [How to: Add Fields to a Details Form](how-to-add-fields-to-a-details-form.md) or [How to: Add a FastTab to a Details Form](how-to-add-a-fasttab-to-a-details-form.md).

### To add fields to the line header

1.  In the AOT, expand the **Forms** node and find the form to which you want to add fields.

2.  Expand the form, expand **Designs**, expand **Design**, expand **Tab**, expand **TabPageDetails**, expand **DetailsTab**, expand **LineView**, expand **LineViewTab**, and then click **LineViewHeader**. You will add the line header fields to this tab page.
    

    > [!NOTE]
    > <P>If you are working with a form that was not created based on a template, or the form had changed template values, know that the names and sequence specified in this and the remaining steps might be different.</P>



3.  Right-click the **Data Sources** node of the form and then click **Open New Window**. The data sources for the form appear in a separate AOT window.

4.  Expand the table that contains the header fields that you want to appear on the grid, and then expand **Fields**.

5.  Drag the field or field group to the tab page. A control is added to the grid for each field. To add more fields to the grid, repeat this step.
    
    For example, the **Sales order** form uses fields from SalesTable in the header section of the line view. In addition, **Sales order** uses several group controls to organize and label the fields that appear in the line header.

### To specify the data source for the lines grid

1.  In the **Design** node, click the **DetailsTab**, expand **LineView**, expand **LineViewTab**, expand **LineViewLines**, right-click **LinesGrid**, and then click **Properties**. The **Properties** window opens.

2.  Click **DataSource** and then select the table you want to use as the data source for the grid.
    
    For example, the **Sales order** form uses the SalesLine table as the data source for the lines grid.

### To add fields to the lines grid

1.  In the AOT window that shows the form data sources, expand **Data Sources**, expand the table that contains the line fields that you want to appear on the grid, and then expand **Fields**.

2.  Drag the field or field group to the grid control. A control is added to the grid for each field. To add more fields to the grid, repeat this step.
    
    For example, the lines grid in the **Sales order** form shows fields from the SalesLine table.

3.  Right-click the form and then click **Save**.

After you add the line header and lines grid, you might want to add fields to the **Line details** tab. For information about how to customize **Line details**, see [How to: Add Line Details Information to a Details Form with Lines](how-to-add-line-details-information-to-a-details-form-with-lines.md).

## See also

[Details Form with Lines User Experience Guidelines](details-form-with-lines-user-experience-guidelines.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

