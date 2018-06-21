---
title: Form Design Properties
TOCTitle: Form Design Properties
ms:assetid: b30888f9-3ae1-475d-8d2c-96ca86b98927
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa857335(v=AX.60)
ms:contentKeyID: 35132745
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Form Design Properties [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Most properties on the form **Design** node also exist on the individual controls, for example, the Width and Height properties.

When you set a property on the **Design** node, however, as opposed to setting it on a control, the setting affects the entire form.

A few properties exist only on the **Design** node. They are described in the following table.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Description</p></th>
<th><p>New in this version of<br />
 Microsoft Dynamics AX</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>AlignChild</strong></p></td>
<td><p>Specifies whether a control within a group follows the <strong>AlignChildren</strong> property setting for the group or the overall form design. For example, if <strong>AlignChildren</strong> is set to <strong>Yes</strong> on the form <strong>Design</strong> node, you might not want a particular group to be arranged with the other groups. In that case, set <strong>AlignChild</strong> for that group to <strong>No</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>AlignChildren</strong></p></td>
<td><p>Aligns the child controls within a container.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>AllowDocking</strong></p></td>
<td><p>Specifies whether or not a form may be attached to the client workspace. The default value is <strong>No</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>AllowFormCompanyChange</strong></p></td>
<td><p>Specifies whether the form supports company changes when used as a child form with a cross-company dynalink. The default value is <strong>No</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>AllowUserSetUp</strong></p></td>
<td><p>Specifies whether a user can move controls on a form, and whether a user can change the value of control properties. This property is also found on the design of a form. The property has the following values: AllowUserSetup</p>
<ul>
<li><p><strong>No</strong> – users cannot customize any controls in this container.</p></li>
<li><p><strong>Restricted</strong> – users can change properties of individual controls, but cannot move controls.</p></li>
<li><p><strong>Yes</strong> – no restrictions on user setup.</p></li>
</ul>
<p>The default value is <strong>Yes</strong>.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Hh404129.alert_caution(en-us,AX.60).gif" title="Caution note" alt="Caution note" class="note" /><strong>Caution</strong>
</div>
<div class="mtps-row">
Full user setup is not allowed if any of the parent containers for the control have restrictions on the user setup level. The <strong>AllowAdd</strong> property on form data sources determines whether a user can add a field to a form.
</div>
</div></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>AlwaysOnTop</strong></p></td>
<td><p>Specifies whether the form is always displayed on top of other windows in the z-order. The default value is <strong>No</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>ArrangeMethod</strong></p></td>
<td><p>Specifies whether child field groups should be arranged in columns or in rows.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>ArrangeWhen</strong></p></td>
<td><p>Specifies when to arrange the controls in the container. The options are as follows:</p>
<ul>
<li><p>Startup</p></li>
<li><p>On demand</p></li>
<li><p>Never</p></li>
<li><p>Default</p></li>
<li><p>Auto</p></li>
</ul>
<p>The default value is <strong>Startup</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>BackgroundColor</strong></p></td>
<td><p>Determines the color used for the background of the control. To set the background to opaque or transparent, use the <strong>BackStyle</strong> property.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>BottomMargin</strong></p></td>
<td><p>Sets in pixels the bottom margin of the form. The default value is <strong>Auto</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>Caption</strong></p></td>
<td><p>Specifies the heading for grouped controls. Use a label for this property.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>ColorScheme</strong></p></td>
<td><p>Specifies the color palette for the control. To change the color palette for an entire form, set the <strong>ColorScheme</strong> property for the largest container and keep the default values for the individual controls.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>Columns</strong></p></td>
<td><p>Specifies the number of columns that display the information.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Hh404129.alert_caution(en-us,AX.60).gif" title="Caution note" alt="Caution note" class="note" /><strong>Caution</strong>
</div>
<div class="mtps-row">
Field groups on the underlying table are never split into more than one column.
</div>
</div></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>ColumnSpace</strong></p></td>
<td><p>Sets the amount of space between columns in container controls.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>DataSource</strong></p></td>
<td><p>Determines which table data is displayed from in the control. To set a particular field within this table, use the <strong>DataField</strong> property. If the control opens another form, relations between the data source specified here for the control and the data source on the other form will ensure that records in the second form are dynamically selected. For example, if a customer is selected in one form, and the control opens up a form showing customer transactions, a range of customer transactions applying to the current customer would be displayed in the second form.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Hh404129.alert_caution(en-us,AX.60).gif" title="Caution note" alt="Caution note" class="note" /><strong>Caution</strong>
</div>
<div class="mtps-row">
If you set the <strong>DataSource</strong> and <strong>DataField</strong> properties, this will override any settings made on the <strong>DataMethod</strong> or <strong>ExtendedDataType</strong> properties.
</div>
</div></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>Font</strong></p></td>
<td><p>Enables you to select another font for the control by opening the <strong>Font</strong> dialog. Use the dialog to specify the <strong>Font</strong>, <strong>Font style</strong>, , and <strong>Size</strong> properties of the font.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>Frame</strong></p></td>
<td><p>Specifies the frame style used by the form.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Height</strong></p></td>
<td><p>Specifies the height of the form or control. The height is specified in pixels.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>HideIfEmpty</strong></p></td>
<td><p>Enables you to hide a container control if it is empty. This property has no affect if the container control has its <strong>Width</strong> and <strong>Height</strong> properties set to <strong>Auto</strong> because the size of the control is then zero.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>HideToolBar</strong></p></td>
<td><p>Hides form-specific buttons on the toolbar.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ImageMode</strong></p></td>
<td><p>Defines how the bitmap specified by the <strong>ImageName</strong> property appears in a control. The options are as follows:</p>
<ul>
<li><p>Normal</p></li>
<li><p>Size to fit</p></li>
<li><p>Side by side</p></li>
<li><p>Center</p></li>
</ul>
<p>The default value is <strong>Normal</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>ImageName</strong></p></td>
<td><p>Specifies the image that is displayed for a control. You can select only .bmp files. To use one of the Microsoft Dynamics AX resource files, use the <strong>ImageResource</strong> property instead.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>ImageResource</strong></p></td>
<td><p>Specifies the image from the image resource file that is displayed for a control. Specify the ID of the image. You can select only an image from the integrated resource file. To use another file type, use the <strong>ImageName</strong> property.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>LabelFont</strong></p></td>
<td><p>Changes the font for the text supplied in the <strong>Label</strong> property.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>Left</strong></p></td>
<td><p>Changes the position of the uppermost left corner of the form. There are a number of predefined settings. You can also specify an exact position in pixels. The predefined settings include the following:</p>
<ul>
<li><p>Auto (left)</p></li>
<li><p>Auto (right)</p></li>
<li><p>Left edge</p></li>
<li><p>Right edge</p></li>
<li><p>Center</p></li>
</ul>
<p>The default value is <strong>Auto (left)</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>LeftMargin</strong></p></td>
<td><p>Changes the default left margin of the form The margin is specified in pixels.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaximizeBox</strong></p></td>
<td><p>Specifies whether to include the maximize box in the upper-right corner of the enclosing window. The default value is <strong>Yes</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>MinimizeBox</strong></p></td>
<td><p>Specifies whether to include the minimize box in the upper-right corner of the enclosing window. The default value is <strong>Yes</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>Mode</strong></p></td>
<td><p>Determines the data entry mode for the form.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Model</strong></p></td>
<td><p>Specifies the model that the form is in.</p>
<p>A model is a logical grouping of elements in a layer. An element can exist in exactly one model in a layer. The same element can exist in a customized version in a model in a higher layer.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>RightMargin</strong></p></td>
<td><p>Changes the default right margin of the form. The margin is specified in pixels.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>SaveSize</strong></p></td>
<td><p>The size of the form is saved if the property is set to <strong>Yes</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrollBars</strong></p></td>
<td><p>Determines whether scroll bars are enabled on the form.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>SetCompany</strong></p></td>
<td><p>Causes the system to change the company when the form gets focus.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
</div>
<div class="mtps-row">
If the <strong>SaveDataPerCompany</strong> property on a table is set to <strong>Yes</strong>, the <strong>SetCompany</strong> property on a form design that uses the table as a data source must also be set to <strong>Yes</strong>.
</div>
</div></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>StatusBarStyle</strong></p></td>
<td><p>Determines how to display the status bar on a form. Use this property to hide the status bar, display only help information, display status bar elements based on the <strong>WindowType</strong>, or to always display the full status bar.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
</div>
<div class="mtps-row">
Forms with a <strong>WindowType</strong> of <strong>ListPage</strong>, <strong>ContentPage</strong>, or <strong>Workspace</strong> ignore this property.
</div>
</div></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Style</strong></p></td>
<td><p>Specifies the style of the form. This property controls the form design pattern being used with the form. The styles include the following:</p>
<ul>
<li><p>Auto</p></li>
<li><p>DetailsFormMaster</p></li>
<li><p>DetailsFormTransaction</p></li>
<li><p>Dialog</p></li>
<li><p>DropDialog</p></li>
<li><p>FormPart</p></li>
<li><p>ListPage</p></li>
<li><p>Lookup</p></li>
<li><p>SimpleList</p></li>
<li><p>SimpleListDetails</p></li>
<li><p>TableOfContents</p></li>
</ul>
<p>The default is <strong>Auto</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>TitleDataSource</strong></p></td>
<td><p>Determines the data source to be used in the form caption.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Top</strong></p></td>
<td><p>Changes the position of the top of the form. There are a number of predefined settings or you can specify in pixels an exact position. The predefined settings are as follows:</p>
<ul>
<li><p>Auto</p></li>
<li><p>Top edge</p></li>
<li><p>Bottom edge</p></li>
<li><p>Center</p></li>
</ul>
<p>The default value is <strong>Auto</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>TopMargin</strong></p></td>
<td><p>Sets in pixels the top margin of the form. The default value is <strong>Auto</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>UseCaptionFromMenuItem</strong></p></td>
<td><p>Specifies whether to replace the form caption with the label from the calling menu item.</p>
<p>Enables the caption of the form to be changed when the form is opened. The default value is <strong>No</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>ViewEditMode</strong></p></td>
<td><p>Specifies whether the form opens in a read-only mode or as a form that allows you to change fields. The options are as follows:</p>
<ul>
<li><p><strong>View</strong> - Opens as read-only.</p></li>
<li><p><strong>Edit</strong> - Opens in edit mode.</p></li>
<li><p><strong>Auto</strong> - Opens in appropriate mode.</p></li>
</ul>
<p>The default is <strong>Auto</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>Visible</strong></p></td>
<td><p>Enables you to hide the Form.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Hh404129.alert_caution(en-us,AX.60).gif" title="Caution note" alt="Caution note" class="note" /><strong>Caution</strong>
</div>
<div class="mtps-row">
You cannot use the <strong>Visible</strong> property to enforce access restrictions. The user can change the visibility for the controls in the Form Setup dialog. Use the <strong>Enabled</strong> and <strong>NeededAccessLevel</strong> properties instead.
</div>
</div></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>Width</strong></p></td>
<td><p>Changes the width in pixels of the form.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>WindowResize</strong></p></td>
<td><p>Determines whether forms can be resized.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>WindowType</strong></p></td>
<td><p>Specifies the window type.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>WorkflowDataSource</strong></p></td>
<td><p>Sets root data source for workflow on a form. This should be the same root data source specified in the query used for the <strong>Document</strong> property on the workflow template. For more information, see <a href="how-to-create-a-workflow-document-class.md">How to: Create a Workflow Document Class</a>.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>WorkflowEnabled</strong></p></td>
<td><p>Enables the workflow menu bar on the form when set to <strong>Yes</strong>. The default value is <strong>No</strong>.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>WorkflowType</strong></p></td>
<td><p>Specifies the workflow type, which determines the following items:</p>
<ul>
<li><p>The workflow document to use. The workflow document exposes calculated fields and identifies the query that exposes data fields for the workflow.</p></li>
<li><p>Whether tasks and approvals can be configured by the end user.</p></li>
<li><p>The Workflow categories to use when assigning a workflow type to a specific module.</p></li>
<li><p>Menu items and event handlers.</p></li>
</ul></td>
<td><p>AX 2012</p></td>
</tr>
</tbody>
</table>


## See also

[Form Control Properties](form-control-properties.md)

[Best Practices for Form Design Properties](best-practices-for-form-design-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

