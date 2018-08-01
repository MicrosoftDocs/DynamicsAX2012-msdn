---
title: 'How to: Create a Table of Contents form'
TOCTitle: 'How to: Create a Table of Contents form'
ms:assetid: d223b2bb-6402-44d5-80ad-7fa14fe5abed
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh745338(v=AX.60)
ms:contentKeyID: 42607688
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Table of Contents form [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to use the AOT and a template to create a table of contents form. You can use a table of contents form to show a series of related tasks in a single form. For more information about table of contents forms, see [Table of Contents Forms Overview](table-of-contents-forms-overview.md).

For example, you can use a table of contents form to provide setup information for an area. You use the setup form to specify values for collections of parameters. Each collection of parameters appears on a vertical tab and is associated with one or more tables in the form data source. The following sections describe how to create the form and add vertical tabs.

### To create a table of contents form

1.  In the AOT, right-click **Forms**, click **New Form from template**, and then click **TableOfContents**. A form is added to the AOT.

2.  Right-click the form and then click **Properties**. The property sheet appears. Click **Name** and type a unique name for the form.

3.  Expand the form node, expand **Designs**, and then click **Design**. In the property sheet, find the **Style** property and verify that it is set to **TableOfContents**.

4.  Click **Caption** and then select a label that represents the name that you want to appear in the title of the form window.
    
    For example, **CustParameter** form sets the **Caption** to use a label that shows **Account receivable parameters**. The caption value appears in the form title section of the form.

5.  Expand the **Design** node. You should see that the template includes a tab control. Click the tab control. In the property sheet, notice the values that are used to populate the following properties:
    
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
    <td><p>The template sets the property to <strong>TOCTab</strong>. You can change the name of the form.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>VerticalTabs</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Width</strong></p></td>
    <td><p><strong>Column width</strong></p></td>
    </tr>
    </tbody>
    </table>


### To add the data source to the form

1.  Press CTRL+D to open a second AOT window. Expand **Data Dictionary**, and then expand **Tables**.

2.  Find the table you want to use as a data source for the form.

3.  Click the table and drag it onto the **Data Sources** node of the form that you created in the previous procedure.

4.  To supply the field values for each vertical tab, you might have to add more than one table to the form data source. Repeat the previous two steps for each table you want to add to the form.
    
    For example, the **CustParameters** form includes the CustParameters, SalesParameters, and several other tables in the form data source. The tables include the fields that appear in the content pane when you click a vertical tab.

### To add a vertical tab to the table of contents list

1.  In the AOT that shows the form, right-click the tab control, click **New Control**, and then click **TabPage**. A tab page control is added to the tab.
    

    > [!TIP]
    > <P>If you use the template to create the form, the first tab page control is already added to the tab. You should use that control for your first vertical tab. However, the tab page will not be visible until you add a field or control. You will find information about how to add a field in one of the following sections.</P>



2.  Click the tab page control. In the property sheet, click the **Name** property and type a name that uniquely identifies the tab page. The template will specify **TOCPage1** as the name of the first tab page control. You can change the name of the first tab page.

3.  Click **Caption** and specify a label or text value. The caption value appears in the list in the table of contents section of the form.
    
    For example, the first tab page control of the **CustParameters** form sets the **Caption** to use a label that shows **General**.

### To add the task instruction that appears in the content pane

1.  Right-click the tab page control, click **New Control**, and then click **Group**. The group control must be the first control for that tab page. If you have to move the control, click the control and then press ALT+UP ARROW or ALT+DOWN ARROW.
    

    > [!TIP]
    > <P>If you use the template to create the form, the group control for the task instructions is already added to the first tab page control. In addition, you will find the group contains two static text controls that you can use for task instructions. You should use these controls to add task instructions for the first vertical tab.</P>



2.  Click the group control. In the property sheet, specify values for the following properties:
    
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
    <td><p><strong>Name</strong></p></td>
    <td><p>Type a unique name for the group control.</p>
    <p>The template will set the <strong>Name</strong> of the first group control to <strong>TOCPage1Header</strong>. However, you can change the name.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>TOCTitleContainer</strong></p></td>
    </tr>
    </tbody>
    </table>


3.  To add a control for the main instruction, right-click the group control, click **New Control**, and then click **StaticText**.

4.  Click the static text control. The control for the main instruction must be the first control in the group. If you want to move the control, use ALT+UP ARROW or ALT+DOWN ARROW. In the property sheet, populate the following properties by using the specified values. If you use the static text control from the template, you have to populate only the **Text** property.
    
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
    <td><p><strong>Name</strong></p></td>
    <td><p>Type a unique name for the static text control.</p>
    <p>The template will set the <strong>Name</strong> of the static text control to <strong>TOCPage1HeaderMainInstruction</strong>. However, you can change the name.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>MainInstruction</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Text</strong></p></td>
    <td><p>Specify the instruction you want to appear at the top of the content pane section of the form. You can select a label or type the text you want to appear.</p>
    <p>For example, the static text control of the <strong>TabGeneral</strong> tab page of the <strong>CustParameters</strong> form uses a label to specify the text that appears as the main instruction.</p></td>
    </tr>
    </tbody>
    </table>


5.  To add a control for the supplemental instruction, right-click the group control, click **New Control**, and then click **StaticText**. However, a supplemental instruction is optional and you can decide not to add a second static text control. For example, the **TabGeneral** tab page of the **CustParameters** form does not include a supplemental instruction.

6.  Click the static text control. The control for the supplemental instruction must appear under the main instruction. If you want to move the control, use ALT+UP ARROW or ALT+DOWN ARROW. In the property sheet, populate the following properties by using the specified values. If you use the static text control from the template, you have to populate only the **Text** property.
    
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
    <td><p><strong>Name</strong></p></td>
    <td><p>Type a unique name for the static text control.</p>
    <p>The template will set the <strong>Name</strong> of the static text control to <strong>TOCPage1HeaderSupplemental</strong>. However, you can change the name.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>Auto</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Text</strong></p></td>
    <td><p>Specify the instruction you want to appear under the main instruction. You can select a label or type the text that you want to appear.</p></td>
    </tr>
    </tbody>
    </table>


### To add fields to the content pane

1.  Right-click the tab page control that you added earlier, click **New Control**, and the click **Group**. A group control is added to the tab page.
    

    > [!TIP]
    > <P>If you use the template to create the form, the group control that represents the body of the content pane is already added to the tab page. You should use that group control for your first vertical tab.</P>



2.  Click the group control. In the property sheet, specify values for the following properties:
    
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
    <td><p><strong>Name</strong></p></td>
    <td><p>Type a unique name for the group.</p>
    <p>The template will set the <strong>Name</strong> of this group control to <strong>TOCPage1Body</strong>. However, you can change the name.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Style</strong></p></td>
    <td><p>Click <strong>TOCTopicSimple</strong> if you want to add a collection of fields or fields groups to the tab page. The remaining steps in this procedure are based on <strong>TOCTopicSimple</strong>.</p>
    <p>Click <strong>TOCTopicList</strong> if you want to add a grid to the tab page. For more information about how to add a grid to a form, see <a href="how-to-create-a-simple-list-form.md">How to: Create a Simple List Form</a>.</p>
    <p>Click <strong>TOCTopicFastTabs</strong> if you want to add FastTabs to the tab page. For more information about how to add FastTabs to a form, see <a href="how-to-add-fasttabs-to-a-form.md">How to: Add FastTabs to a Form</a>.</p></td>
    </tr>
    </tbody>
    </table>


3.  Expand the **Data Sources** node of the form. Right-click the data source that contains the field or field group you want to appear on the form and then click **Open New Window**. The specified table opens in a separate AOT window.

4.  To see the available fields and field groups, expand **Fields**. Drag the field or field group from the table to the group control of the form. Repeat this step for each field or field group you want to appear on the form.

5.  Right-click the form and then click **Save**.

To add more vertical tabs to a form, you add tab pages to the tab control. Repeat the steps that add the vertical tab, task instructions, and fields to the form.

To view the form, right-click the form in the AOT, and then click **Open**. The form appears in a separate window.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

