---
title: 'How to: Add Line Details Information to a Details Form with Lines'
TOCTitle: 'How to: Add Line Details Information to a Details Form with Lines'
ms:assetid: 4988870e-9f39-43dd-89ff-fa5e1110e85d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh528503(v=AX.60)
ms:contentKeyID: 37835251
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add Line Details Information to a Details Form with Lines 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A details form with lines includes a single expandable and collapsible FastTab named Line details. When you expand **Line details** you see one or more tabs along the bottom of the form. These tabs show additional information for the record in the line header or the highlighted record in the lines grid. For information about how to customize the line header and lines grid, see [How to: Customize the Line View of a Details Form with Lines](how-to-customize-the-line-view-of-a-details-form-with-lines.md).

To add fields to the line details tab, you must first add a data source to the form. For information about how to add a data source, see [How to: Add a Data Source to a Details Form](how-to-add-a-data-source-to-a-details-form.md).

For information about how to add fields to the header of the form, see [How to: Add Fields to a Details Form](how-to-add-fields-to-a-details-form.md) or [How to: Add a FastTab to a Details Form](how-to-add-a-fasttab-to-a-details-form.md).

### To find the Line details tab and set the Style property

1.  In the AOT, expand the **Forms** node and find the form that you want to modify.

2.  Expand the form, expand **Designs**, expand **Design**, expand **Tab**, expand **TabPageDetails**, expand **DetailsTab**, expand **LineView**, expand **LineViewTab**, expand **LineViewLineDetails**, right-click **LineDetailsTabs**, and then click **Properties**. The **Properties** window opens.
    

    > [!NOTE]
    > <P>If you are working with a form that was not created based on a template, or the form had changed template values, know that the names and sequence specified in this and the remaining steps might be different.</P>



3.  In the property sheet, click **Style** and verify that the property value is set to **IndexTabs**.
    
    You use the **Style** property to specify how the tab pages appear. The tab headings in the line details section appear across the bottom of the form.

### To add the tab page

1.  If you used the **DetailsFormTransaction** template to create the form, you will find that the form includes an empty tab page name **LineGeneral**. To add fields to the **LineGeneral** tab page, use the following procedure that describes how to add fields to a tab page. If you want to add a new tab, continue to the next step.

2.  Right-click **LineDetailsTabs**, click **New Control**, and then click **TabPage**. A new tab page is added to the form.

3.  Click the tab page. In the property sheet click **Name** and type a name that uniquely identifies the tab page.

4.  Click **Caption** and specify the label that you want to appear as the tab heading.

5.  Move the tab page to the location where it will appear. Typically, the **LineGeneral** tab is first and all other tabs appear after it. To change the order of the tab pages in the **LineDetailsTabs**, click the tab page you want to move, and then press ALT+UP ARROW or ALT+DOWN ARROW.

### To add field values to the tab page

1.  In the AOT window that shows the form, right-click the **Data Sources** node, and then click **Open New Window**. The data sources for the form appear in a separate AOT window.

2.  Expand **Data Sources**, expand the table that contains the fields that you want to appear on the tab, and then expand **Fields**.

3.  Drag the field or field group to the tab page that you added earlier. A control is added to the tab page. Repeat this step for each field or field group that you want to appear in the tab.

4.  To specify the field values that appear in the summary fields of the tab, you use the **FastTabSummary** property of the control. The summary fields for **Line details** can show values from fields in more than one tab page.
    

    > [!NOTE]
    > <P>The <STRONG>FastTabSummary</STRONG> property does not appear on all controls. For example, the reference group control does not include the <STRONG>FastTabSummary</STRONG> property.</P>

    
    To add or remove a summary field, click the control and then click one of the following values.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>FastTabSummary</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Auto</strong></p></td>
    <td><p>The default value. The field value is added to the summary fields for the first five fields that are members of the <strong>AutoSummary</strong> field group of the table.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>No</strong></p></td>
    <td><p>The field value does not appear in summary fields of the FastTab.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Yes</strong></p></td>
    <td><p>Adds the value that appears in the control to the summary fields of the FastTab.</p></td>
    </tr>
    </tbody>
    </table>


5.  Right-click the form and then click **Save**.

## See also

[Details Form with Lines User Experience Guidelines](details-form-with-lines-user-experience-guidelines.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

