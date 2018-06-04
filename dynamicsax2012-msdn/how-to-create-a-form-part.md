---
title: 'How to: Create a Form Part'
TOCTitle: 'How to: Create a Form Part'
ms:assetid: e14ea103-5fe1-4cae-96b8-0aff53263664
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg864890(v=AX.60)
ms:contentKeyID: 35253089
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Form Part 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A form part is a pointer to an existing form. You use a form part to make the form appear in the FactBox pane of a form, the preview pane of a list page, or the enhanced preview of a control.

Take care to select a form that fits the location where the form part appears. For example, a form with a large grid and several controls might not fit the space available for a FactBox or enhanced preview. Typically, you select a form that was designed for use in the FactBox pane, preview pane, or enhanced preview. For design guidelines, see the FactBoxes section of the [List Page User Experience Guidelines](list-page-user-experience-guidelines.md).

The following steps describe how to validate the form and create the form part. Use the validation steps to verify that the form includes the specified property values.

### To validate the form

1.  In the AOT, expand **Forms**, expand the form you want to appear in the form part, expand **Designs**, right-click **Design**, and then click **Properties**. The design properties of the form appear in the **Properties** sheet.
    

    > [!WARNING]
    > <P>If you cannot change the properties of the existing form without adversely affecting other areas of Microsoft Dynamics AX, create a copy of the form and set the properties of the copy to the specified values.</P>



2.  Verify that the following form design properties have the specified value.
    
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
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>FormPart</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ViewEditMode</strong></p></td>
    <td><p><strong>View</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Width</strong></p></td>
    <td><p><strong>Column width</strong></p></td>
    </tr>
    </tbody>
    </table>


3.  Expand the **Design** node to view the controls that appear on the form. Click each control and verify that the **Width** property of the control is set to **Column width**.

4.  If the form includes a grid control, verify that the **Style** property of the control is set to **SimpleReadOnly**.

5.  If you made changes to the properties of the form or the controls, click **Save**.

### To create the form part

1.  In the AOT, expand **Parts**, right-click **Form Parts**, and then click **New Form Part**. A form part is added to the list of form parts.

2.  Click the form part that you added. The **Properties** window shows the properties for the part. Click **Name** and specify a name that uniquely identifies the form part.

3.  Click **Caption** and select the label that you want to appear in the title bar of the FactBox.

4.  Click **Form** and then click the name of the form you want to use.

5.  If the form part will appear in Enterprise Portal (EP), click the **ManagedContentItem**, and then click the name of the managed content item (User Control) that you want to appear in the FactBox. If the form part does not appear in EP, this step is not needed.

6.  Right-click the form part and then click **Save**.

## See also

[How to: Add a Part to the FactBox Pane](how-to-add-a-part-to-the-factbox-pane.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

