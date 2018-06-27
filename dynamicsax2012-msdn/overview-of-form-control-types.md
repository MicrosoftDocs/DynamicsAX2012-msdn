---
title: Overview of Form Control Types
TOCTitle: Form Control Types
ms:assetid: 281c521e-8b8e-45b9-891b-d504acf410e1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa601664(v=AX.60)
ms:contentKeyID: 35241700
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Overview of Form Control Types 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes the types of controls that you can use on a form. For general information about form controls, see [Form Controls Overview](form-controls-overview.md) and [How to: Add a Control to a Form](how-to-add-a-control-to-a-form.md).

Some form controls require that you specify a data source. The data source supplies the values that appear in the control. You can add controls to a form by dragging a field or field group onto the **Design** node of the form. The data source property of the control is populated with name of the table for that field or field group. For more information, see [How to: Add a Control to a Form](how-to-add-a-control-to-a-form.md).


> [!NOTE]
> <P>If you set the data source for a control by using the <STRONG>DataMethod</STRONG> property and the method that you want to use is on a table that is used as a data source in the form, you must also set the <STRONG>DataSource</STRONG> property. You do not have to set the <STRONG>DataSource</STRONG> property if the method is on the form or is on the <STRONG>Data Source</STRONG> node in the form.</P>



If a control does not automatically identify a data source, use the information in the following table to populate the data source property of that control.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Control name</p></th>
<th><p>Description</p></th>
<th><p>Data source</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ActionPane</strong></p></td>
<td><p>A control that adds the action pane bar to a form.</p></td>
<td><p>Use the <strong>DataSource</strong> property to associate a data source with the action pane. The default data source is the primary data source of the form.</p></td>
<td><p>Use an action pane to show the action pane tab controls for the form.</p></td>
</tr>
<tr class="even">
<td><p><strong>ActionPaneTab</strong></p></td>
<td><p>A control that displays and labels a collection of related actions.</p></td>
<td><p>Not applicable.</p></td>
<td><p>Use an action pane tab to group actions by task or Microsoft Dynamics AX role. To display an action pane tab in the action pane, add one or more button group controls.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ActiveX</strong></p></td>
<td><p>Any ActiveX control available on the computer.</p></td>
<td><p>The control type is selected when you create the control, and is displayed in the <strong>ClassName</strong> property.</p></td>
<td><p>Enables you add ActiveX controls to a form. To learn about ActiveX controls on forms, see <a href="how-to-add-activex-controls-to-forms.md">How to: Add ActiveX Controls to Forms</a>.</p>

> [!caution]  
> <P>The ActiveX control is considered deprecated. To add a Windows Form or Windows Presentation Foundation control to a form, use the <strong>ManagedHost</strong> control.</P>

</td>
</tr>
<tr class="even">
<td><p><strong>Animate</strong></p></td>
<td><p>A control that is used to display an .avi file.</p></td>
<td><p>The .avi file is set by using the <strong>AnimateFile</strong> property.</p></td>
<td><p>Use the control to show animated images. The .avi file must not have a sound track.</p>

> [!note]  
> <P>If you set the <strong>AutoPlay</strong> property to <strong>Yes</strong> and the <strong>Loops</strong> property to <strong>0</strong>, the system plays the designated .avi file indefinitely.</P>

</td>
</tr>
<tr class="odd">
<td><p><strong>Button</strong></p></td>
<td><p>A rectangular button.</p></td>
<td><p>The behavior for the button is set by overriding the clicked method for the control.</p>
<p>If the button displays an image, the image is set by using the <strong>NormalImage</strong> or the <strong>NormalResource</strong> property.</p></td>
<td><p>Use a button to start an action. Buttons are usually grouped under a <strong>ButtonGroup</strong> control.</p>
<p>If you want to create a button for a frequently used command (for example, <strong>Open</strong> or <strong>Save</strong>) or to open a system menu, use a <strong>CommandButton</strong> control.</p>
<p>The <strong>ButtonDisplay</strong> property determines whether the button displays an image.</p>
<p>For a form where the <strong>Style</strong> property of the <strong>Design</strong> node is set to <strong>Dialog</strong>, you can set the <strong>DefaultButton</strong> property of the button to <strong>Yes</strong> to select the button when you press <strong>Enter</strong> on the form.</p></td>
</tr>
<tr class="even">
<td><p><strong>ButtonGroup</strong></p></td>
<td><p>A control that is used to group buttons that belong together under a heading.</p></td>
<td><p>Use the <strong>DataSource</strong> property to associate a data source with the button group. The default data source is the primary data source of the form.</p></td>
<td><p>Use button groups to organize and label related action. All the buttons that appear in a <strong>ButtonGroup</strong> use the same size.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CheckBox</strong></p></td>
<td><p>A square box that is selected or cleared to turn an option on or off. More than one check box can be selected.</p></td>
<td><p>The data source is set by using the <strong>DataSource</strong> and <strong>DataField</strong> properties, or by using the <strong>DataMethod</strong> property.</p></td>
<td><p>Use this kind of control for fields that have an enumerated data type with two values.</p></td>
</tr>
<tr class="even">
<td><p><strong>ComboBox</strong></p></td>
<td><p>A text box that has an attached list. You can select an item from the list, or type a new value.</p></td>
<td><p>The data source is set by using the <strong>DataSource</strong> and <strong>DataField</strong> properties, or by using the <strong>DataMethod</strong> property.</p></td>
<td><p>Use this kind of control for fields that have an enumerated data type with more than two values.</p>
<p>To prevent a user from adding values to the control, set the <strong>ComboType</strong> property to <strong>List</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CommandButton</strong></p></td>
<td><p>A button to start a command. For example, to close the form, to save all, or to open one of the system menus.</p></td>
<td><p>Not applicable.</p></td>
<td><p>Use this kind of control when you want a button to start a function. The function of the control is set by using the <strong>Command</strong> property. You can select from many options. For example, <strong>New</strong>, <strong>Open</strong>, <strong>Save</strong>, <strong>Undo</strong>, <strong>Select All</strong>, and <strong>Next Tab Page</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DateEdit</strong></p></td>
<td><p>A control that is used to display and edit dates.</p></td>
<td><p>The data source is set by using the <strong>DataSource</strong> and <strong>DataField</strong> properties, or by using the <strong>ExtendedDataType</strong> property, or the <strong>DataMethod</strong> property.</p></td>
<td><p>Use this kind of control to show and edit date values. The following properties are inherited from the data type on which the control is based:</p>
<ul>
<li><p><strong>Alignment</strong></p></li>
<li><p><strong>DateFormat</strong></p></li>
<li><p><strong>DateSeparator</strong></p></li>
<li><p><strong>DateYear</strong></p></li>
<li><p><strong>DateMonth</strong></p></li>
<li><p><strong>DateDay</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>DropDialogButton</strong></p></td>
<td><p>A button that opens a small form you use to update specified field values.</p></td>
<td><p>The data source is set by using the <strong>DataSource</strong> property.</p></td>
<td><p>Use the <strong>MenuItemName</strong> property to specify a menu item. The menu item <strong>Object</strong> property specifies the form that appears when you click the button.</p></td>
</tr>
<tr class="even">
<td><p><strong>Grid</strong></p></td>
<td><p>A table that displays records from a database table.</p></td>
<td><p>The data source is set by using the <strong>DataSource</strong> property.</p></td>
<td><p>Open all data entry forms to an <strong>Overview</strong> tab that displays records in a grid.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Group</strong></p></td>
<td><p>A facility used to group several fields under a heading.</p></td>
<td><p>The data source is set by using the <strong>DataSource</strong> property.</p></td>
<td><p>Use this control to group and label related fields. This type of control is automatically created if you drag a field group onto the form design.</p></td>
</tr>
<tr class="even">
<td><p><strong>GuidEdit</strong></p></td>
<td><p>A control that is used to display and edit GUIDs.</p></td>
<td><p>The data source is set by using the <strong>DataSource</strong> and <strong>DataField</strong> properties, or by using the <strong>ExtendedDataType</strong> property or the <strong>DataMethod</strong> property.</p></td>
<td><p>Not applicable.</p></td>
</tr>
<tr class="odd">
<td><p><strong>HTML</strong></p></td>
<td><p>A control that is used to display and edit HTML-based text.</p></td>
<td><p>The content for this control is set by using the FormHTMLControl.setText method.</p></td>
<td><p>Not applicable.</p></td>
</tr>
<tr class="even">
<td><p><strong>IntEdit</strong> and <strong>Int64Edit</strong></p></td>
<td><p>The controls that were used to display and edit integers.</p></td>
<td><p>The data source is set by using the <strong>DataSource</strong> and <strong>DataField</strong> properties, or by using the <strong>ExtendedDataType</strong> property, or the <strong>DataMethod</strong> property.</p></td>
<td><p>Use this kind of control to show integer values on a form. The <strong>IntEdit</strong> controls are for 32-bit integers and the <strong>Int64Edit</strong> controls are for 64-bit integers.</p>
<p>Users can enter an expression in the control. The result is evaluated when they leave the control.</p>
<p>The following properties are inherited from the data type on which the control is based:</p>
<ul>
<li><p><strong>Alignment</strong></p></li>
<li><p><strong>DisplaceNegative</strong></p></li>
<li><p><strong>ShowZero</strong></p></li>
<li><p><strong>SignDisplayRotateSign</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Listbox</strong></p></td>
<td><p>A box that presents the user with a list of choices.</p></td>
<td><p>The data source is set by using the <strong>DataSource</strong> and <strong>DataField</strong> properties, or by using the <strong>ExtendedDataType</strong> property, the <strong>EnumType</strong> property, or the <strong>DataMethod</strong> property.</p></td>
<td><p>Not applicable.</p></td>
</tr>
<tr class="even">
<td><p><strong>ListView</strong></p></td>
<td><p>A list that displays a collection of items where each item consists of an icon and a label.</p></td>
<td><p>The content and behavior of a <strong>ListView</strong> control must be defined by using code.</p></td>
<td><p>Use this kind of control to show a list together with icons. The icons in a <strong>ListView</strong> are supplied by using an image list. For more information, see <a href="how-to-create-an-image-list-for-controls.md">How to: Create an Image List for Controls</a>.</p>
<p>A <strong>ListView</strong> control displays the icons that are contained in an image list. To organize the icons, specify a of value for the <strong>ViewType</strong> property:</p>
<ul>
<li><p><strong>Icon</strong></p></li>
<li><p><strong>Small icons</strong></p></li>
<li><p><strong>List</strong></p></li>
<li><p><strong>Report</strong></p></li>
</ul>
<p>The <strong>ViewType</strong> property values correspond to the Large Icons, Small Icons, List, and Details settings from the Views list of the Microsoft Windows Explorer toolbar.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ManagedHost</strong></p></td>
<td><p>A control that hosts a Windows Form or Windows Presentation Foundation control on a form.</p></td>
<td><p>The type of control is specifed by the <strong>TypeName</strong> and <strong>AssemblyName</strong> properties of the control.</p></td>
<td><p>Use this control to add Windows Form and Windows Presentation Foundation controls to a form. For information about how to add a .NET control to a form, see <a href="how-to-add-a-net-control-to-a-form.md">How to: Add a .NET Control to a Form</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>MenuButton</strong></p></td>
<td><p>A button that opens a submenu.</p></td>
<td><p>Not applicable.</p></td>
<td><p>Use this kind of control to provide access to a list of buttons. A <strong>MenuButton</strong> control can contain <strong>Button</strong>, <strong>CommandButton</strong>, and <strong>MenuItemButton</strong> controls, and <strong>Separators</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MenuItemButton</strong></p></td>
<td><p>A button to open a menu item.</p></td>
<td><p>The <strong>MenuItemType</strong> and <strong>MenuItemName</strong> properties identify the menu item to be opened.</p></td>
<td><p>Not applicable.</p></td>
</tr>
<tr class="even">
<td><p><strong>Progress</strong></p></td>
<td><p>A control that is used to show the percentage of completion of a lengthy operation. It consists of a bar that “fills” from left to right.</p></td>
<td><p>To use a progress control, you have to supply code that fills the progress bar.</p>
<p>For example, you add a progress control for an operation that starts when a button is clicked. To update the progress control, you have to add code to the clicked method of the button control that fills the progress bar as the operation runs.</p></td>
<td>
  
> [!note]  
> <P>Use a progress indicator from the progress indicator framework instead of a progress control. For information about how to use the progress indicator framework, see <a href="how-to-create-progress-indicators.md">How to: Create Progress Indicators</a>.</P>

</td>
</tr>
<tr class="odd">
<td><p><strong>RadioButton</strong></p></td>
<td><p>A round button used to select one of a group of mutually exclusive options.</p></td>
<td><p>The data source is set by using the <strong>DataSource</strong> and <strong>DataField</strong> properties, or by using the <strong>ExtendedDataType</strong> property, the <strong>EnumType</strong> property, or the <strong>DataMethod</strong> property.</p></td>
<td><p>Not applicable.</p></td>
</tr>
<tr class="even">
<td><p><strong>RealEdit</strong></p></td>
<td><p>A control that is used to display and edit real numbers.</p></td>
<td><p>The data source is set by using the <strong>DataSource</strong> and <strong>DataField</strong> properties, or by using the <strong>ExtendedDataType</strong> property or the <strong>DataMethod</strong> property.</p></td>
<td><p>Use this kind of control to show and edit numeric values. Users can enter an expression in the control. The result is evaluated when they leave the control.</p>
<p>The following properties are inherited from the data type on which the control is based:</p>
<ul>
<li><p><strong>Alignment</strong></p></li>
<li><p><strong>AutoInsSeparator</strong></p></li>
<li><p><strong>DecimalSeparator</strong></p></li>
<li><p><strong>DisplaceNegative</strong></p></li>
<li><p><strong>NoOfDecimals</strong></p></li>
<li><p><strong>RotateSign</strong></p></li>
<li><p><strong>ShowZero</strong></p></li>
<li><p><strong>SignDisplay</strong></p></li>
<li><p><strong>ThousandSeparator</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>ReferenceGroup</strong></p></td>
<td><p>The control you use to add a surrogate foreign key field to a form.</p></td>
<td><p>Use the <strong>DataSource</strong> property to specify the table in the form data source that contains the field you want bound to the control. Use the <strong>DataReference</strong> property to specify the field in the DataSource table that contains the surrogate foreign key value.</p></td>
<td><p>Use this control to enable the lookup of related records. The control contains a control that displays the fields that replace the surrogate foreign key value. The <strong>ReplacementFieldGroup</strong> specifies the field group that replaces the foreign key value. The control includes a lookup you can use to select or update the value that appears in the control.</p></td>
</tr>
<tr class="even">
<td><p><strong>SegmentedEntry</strong></p></td>
<td><p>The control you use to view or enter account number and associated dimensions as segments in a single field on a form.</p></td>
<td><p>Use the <strong>DataSource</strong> property to specify the table in the form data source that contains the field you want bound to the control. Use the <strong>DataReference</strong> property to specify the field in the DataSource table that contains the surrogate foreign key value.</p></td>
<td><p>Use this kind of control to show and edit account numbrs. The ReplacementFieldGroup specifies the field group that replaces the foreign key value. The control includes a lookup you can use to select or update the value that appears in the control. Use the <strong>ContextFlyout</strong> property to enable context flyout that helps identify each segment of the account number.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Separator</strong></p></td>
<td><p>A control that is used to add space between buttons in a button group or a menu button.</p></td>
<td><p>Not applicable.</p></td>
<td><p>Use the separator control to organize buttons into related groups or highlight a button that represents a key task or action.</p></td>
</tr>
<tr class="even">
<td><p><strong>StaticText</strong></p></td>
<td><p>A control that is used to display text.</p></td>
<td><p>The text to display in the form is specified by using the <strong>Text</strong> property.</p></td>
<td><p>Use a <strong>StringEdit</strong> control when you want to enable users to change text values.</p></td>
</tr>
<tr class="odd">
<td><p><strong>StringEdit</strong></p></td>
<td><p>A control that is used to display and edit text strings.</p></td>
<td><p>The data source is set by using the <strong>DataSource</strong> and <strong>DataField</strong> properties, or by using the <strong>ExtendedDataType</strong> property or the <strong>DataMethod</strong> property.</p></td>
<td><p>Use a <strong>StringEdit</strong> control to show text that can span multiple lines. This is defined by the <strong>MultiLine</strong> property.</p>
<p>The following properties are inherited from the data type on which the control is based:</p>
<ul>
<li><p><strong>Alignment</strong></p></li>
<li><p><strong>Uppercase</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Tab</strong></p></td>
<td><p>A group control that contains <strong>TabPage</strong> controls.</p></td>
<td><p>Not applicable.</p></td>
<td><p>Use this kind of control to organize a group of tab pages. The <strong>Tab</strong> property controls which tab pages should be displayed when the user opens the form. Best practice is to leave this property set to <strong>Auto</strong> to display the first tabbed page.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table</strong></p></td>
<td><p>A spreadsheet-like table with rows and columns.</p></td>
<td><p>The content of a <strong>Table</strong> control must be defined by using code.</p></td>
<td><p>Use this kind of control to show a list of data in a grid. The <strong>Table</strong> control is not associated with the database. This control resembles a <strong>Grid</strong> control, but it can display values for different types in a single column.</p></td>
</tr>
<tr class="even">
<td><p><strong>TabPage</strong></p></td>
<td><p>An additional page on the form.</p></td>
<td><p>Not applicable.</p></td>
<td><p>Use this kind of control to organize and label a collection of fields on a form. A <strong>TabPage</strong> control is typically used when there is too much information to display in a single dialog box.</p>
<p>You can create a <strong>TabPage</strong> control only in a <strong>Tab</strong> control.</p>
<p>The <strong>Caption</strong> property determines the text that is displayed on the tab.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeEdit</strong></p></td>
<td><p>A control that is used to display and change a time.</p></td>
<td><p>The data source is set by using the <strong>DataSource</strong> and <strong>DataField</strong> properties, or by using the <strong>ExtendedDataType</strong>, or the <strong>DataMethod</strong> property.</p></td>
<td><p>Use this kind of control to show and edit time values. The following properties are inherited from the data type on which the control is based:</p>
<ul>
<li><p><strong>Alignment</strong></p></li>
<li><p><strong>TimeFormat</strong></p></li>
<li><p><strong>TimeHours</strong></p></li>
<li><p><strong>TimeMinute</strong></p></li>
<li><p><strong>TimeSeconds</strong></p></li>
<li><p><strong>TimeSeparator</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Tree</strong></p></td>
<td><p>A special list control that displays a set of objects as an indented outline based on their logical hierarchical relationship.</p></td>
<td><p>The content and behavior of a <strong>Tree</strong> control must be defined by using code.</p></td>
<td><p>Use this kind of control to show hierarchical data. The icons in a <strong>Tree</strong> control are supplied by using an image list. For more information, see <a href="how-to-create-an-image-list-for-controls.md">How to: Create an Image List for Controls</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UtcDateTimeEdit</strong></p></td>
<td><p>Automatically converts Coordinated Universal Times (UTC) into local date/time for display. Also converts local date/time into UTC for storage.</p></td>
<td><p>The data source is set by using the <strong>DataSource</strong> and <strong>DataField</strong> properties, or by using the <strong>ExtendedDataType</strong> property, or the <strong>DataMethod</strong> property.</p></td>
<td><p>Use this kind of control to show and edit date and time values. For more information, see <a href="time-zone-and-datetime-display-controls.md">Time Zone and DateTime Display Controls</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Window</strong></p></td>
<td><p>A window that displays a bitmap.</p></td>
<td><p>The bitmap can be specified by using the <strong>ImageName</strong> property, the <strong>ImageResource</strong> property, or the <strong>DataSource</strong> and <strong>DataField</strong> properties, or the <strong>DataMethod</strong> property.</p></td>
<td><p>Use this kind of control to add images to a form. For more information about Window controls, see <a href="how-to-add-an-image-to-a-form.md">How to: Add an Image to a Form</a>.</p></td>
</tr>
</tbody>
</table>


## See also

[How to: Add a Control to a Form](how-to-add-a-control-to-a-form.md)

[Form Control Properties](form-control-properties.md)

[Methods on Form Controls](methods-on-form-controls.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

