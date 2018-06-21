---
title: 'How to: Add a FastTab to a Details Form'
TOCTitle: 'How to: Add a FastTab to a Details Form'
ms:assetid: 0ebf50a9-c362-4392-a152-f28d1cca87cf
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh528501(v=AX.60)
ms:contentKeyID: 37835249
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a FastTab to a Details Form [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A FastTab is an expandable and collapsible tab you use to show fields in the header of a details form. You can add FastTabs to the header of both the details form and the details form with lines. For more information about the types of details forms, see [Details Form Overview](details-form-overview.md).

These procedures assume that you used the **DetailsFormMaster** or **DetailFormTransaction** template to create the form. For information about how to use a template to create a form, see [How to: Create a Details Form](how-to-create-a-details-form.md).


> [!NOTE]
> <P>If you are working on a form that did not use the template, the location and names that you see in the <STRONG>Design</STRONG> node of the form that identify the tabs and tab pages of the header view may be different.</P>



### To find the tab and set the tab Style property

1.  In the AOT, expand **Forms** and find the form to which you want to add a FastTab.

2.  Expand the form node, expand **Designs**, right-click **Design**, and then click **Properties**. The **Properties** window opens. Click the **Style** property and note whether the form style is set to **DetailsFormMaster** or **DetailsFormTransaction**.

3.  Expand **Design**, and find the **HeaderDetails** tab. The location of the tab depends on the value of the **Style** property that you found in the previous step. The following table shows where the tab can be found for each template.
    
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
    <td><p>Expand <strong>Design</strong>, expand <strong>Tab</strong>, expand <strong>TabPageDetails</strong>, and then click <strong>HeaderDetailsTab</strong>.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>DetailsFormTransaction</strong></p></td>
    <td><p>Expand <strong>Design</strong>, expand <strong>Tab</strong>, expand <strong>TabPageDetails</strong>, expand <strong>DetailsTab</strong>, expand <strong>HeaderView</strong>, and then click <strong>HeaderDetailsTab</strong>.</p></td>
    </tr>
    </tbody>
    </table>


4.  In the property sheet, click **Style** and verify the property value is set to **FastTabs**.
    

    > [!IMPORTANT]
    > <P>When you set the tab style to <STRONG>FastTabs</STRONG>, all of the tab pages associated with that tab use FastTab behavior.</P>



### To add the tab page

1.  Right-click the **HeaderDetailsTab**, click **New control**, and then click **TabPage**. The tab page is added to the form.

2.  In the property sheet, click **Name** and type a name that uniquely identifies the tab page.

3.  Click **Caption** and specify the label that you want to appear in the title of the FastTab.

4.  To change the order that FastTabs appear on the form, click the tab page in the AOT, and then press ALT+UP ARROW or ALT+DOWN ARROW.

### To add fields to the tab page

1.  In the form node, right-click **Data Sources** and then click **Open New Window**. A second AOT window opens and shows the data sources for the form.

2.  In the new AOT window, expand **Data Sources** and find the table that includes the fields you want to add to the form. Expand the **Fields** node of the table.

3.  Drag a field or field group from the data source to the tab page you added to the form. Repeat this step for each field or field group that you want to appear in the FastTab. A control is added to the tab page for each field.

4.  To add a field value to the summary fields of the FastTab, you use the **FastTabSummary** property of the control.
    

    > [!NOTE]
    > <P>The <STRONG>FastTabSummary</STRONG> property does not appear on all controls. For example, the reference group control does not include the <STRONG>FastTabSummary</STRONG> property.</P>

    
    To specify whether a field value appears in the summary fields, click the control that has the value that you want to display in the summary and then click one of the following values.
    
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


5.  Right-click the form, and then click **Save**.

A FastTab can include an action pane strip. For information about how to add an action pane strip, see [Action Pane Strip Overview](action-pane-strip-overview.md).

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

