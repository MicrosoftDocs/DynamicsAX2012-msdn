---
title: 'How to: Add FastTabs to a Form'
TOCTitle: 'How to: Add FastTabs to a Form'
ms:assetid: 7229727d-09bb-4f92-9ab1-b6a0c423806a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh538481(v=AX.60)
ms:contentKeyID: 39508914
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add FastTabs to a Form [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You add a FastTab to a form when you want a collection of fields to appear in an expandable and collapsible section of the form. You can add FastTabs to the details view of several types of forms. If you use a form template to create the form, the template adds controls for FastTabs. In addition, you can add a FastTab to a form that has an existing collection of FastTabs. For more information about forms and FastTabs, see [FastTabs](fasttabs.md).

### To add the tab control

1.  In the application object tree (AOT), expand **Forms** and then find and expand the form where you want to add the FastTab.
    

    > [!TIP]
    > <P>If you want to add a FastTab to a form that has an existing collection of FastTabs, you do not have to add a new tab control. To add the FastTab, you should add a tab page to the existing tab control. To learn how to add a tab page to a tab, proceed to the next section.</P>



2.  Expand **Designs**, expand **Design**, and then find the group control or tab page control where you want to add the FastTab.

3.  Right-click the group, or the tab page control where you want to add the tab, click **New Control**, and then click **Tab**.

4.  Right-click the tab control and then click **Properties**. Use the property sheet to specify values for the following properties:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Height</strong></p></td>
    <td><p><strong>Column height</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p>Type a name that uniquely identifies the tab.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>FastTabs</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Width</strong></p></td>
    <td><p><strong>Column width</strong></p></td>
    </tr>
    </tbody>
    </table>


### To add the tab page control

1.  In the **Design** node of the form, find the tab where you want the FastTab to appear. This could be the tab you added in the earlier section or an existing tab where the **Style** property is set to **FastTabs**.

2.  Right-click the tab control, click **New Control**, and then click **TabPage**. A tab page is added to the tab.

3.  Right-click the tab page and then click **Properties**. Use the property sheet to specify values for the following properties:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Caption</strong></p></td>
    <td><p>Specify a label that identifies the fields that appear in the FastTab. The <strong>Caption</strong> value appears as the title for the FastTab.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Columns</strong></p></td>
    <td><p>Specify the number of columns that appear in the FastTab. A FastTab should have two columns but can show three columns. The default value is <strong>Auto</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>FastTabExpanded</strong></p></td>
    <td><p>Specify whether the FastTab appears expanded or collapsed. The default value is <strong>Auto</strong>.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p>Type a name that uniquely identifies the tab page on the form.</p></td>
    </tr>
    </tbody>
    </table>


### To add field values to the tab page

1.  Right-click the **Data Sources** node of the form, and then click **Open New Window**. The list of data sources appear in a second AOT window.

2.  In the second AOT window, expand **Data Sources**, expand the table that contains the fields you want to add to the FastTab. Expand **Fields** so that you can view the field and field groups for that table.

3.  Drag the field group or field onto the tab page control that you added earlier. A control is added to the tab page for each field. Repeat this step for each field group or field that you want to appear in the FastTab. You should not add more than four field groups to the tab page.

### To specify the summary fields

1.  In the tab page, click the control you want to modify. The properties for the control appear in the **Properties** window.

2.  In the property sheet, click the **FastTabSummary** property, and then click one of the following values:
    
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
    <td><p>The default value. Use this value when you want the values of the first five fields that are members of the <strong>AutoSummary</strong> field group of the table to appear as summary fields.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>No</strong></p></td>
    <td><p>Use this value when you want to prevent a field value from appearing as a summary field.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Yes</strong></p></td>
    <td><p>Use this value when you want the value in the selected control to appear as a summary field.</p></td>
    </tr>
    </tbody>
    </table>


3.  Right-click the form and then click **Save**.

## See also

[How to: Add a FastTab to a Details Form](how-to-add-a-fasttab-to-a-details-form.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

