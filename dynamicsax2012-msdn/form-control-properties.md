---
title: Form Control Properties
TOCTitle: Form Control Properties
ms:assetid: 99224323-4273-40a3-81ab-1c5053dfcd62
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa845161(v=AX.60)
ms:contentKeyID: 35132739
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Form Control Properties 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes the properties for form controls and provides recommendations for their use. It is mandatory to set values for some properties. For more information, see [Best Practices for Form Control Properties](best-practices-for-form-control-properties.md). Please note that not all properties detailed here are present on every control.

Use the automatic property settings for controls (Auto settings) wherever possible. They save time, help to create a uniform application interface, and interact dynamically with other Auto settings. For example, the Auto settings for dimension properties, such as **Top**, **Width**, and **Left**, make allowances for changes to properties, such as **Font** and **FontSize**.

For bound controls (those associated with an underlying database field), set the properties on the field in the form data source. The same properties are applied if the same control is used more than once on the form.

Some properties are inherited from the data type that the control is based on (or the data type for the field that is displayed in the control).

The properties set on container controls (ButtonGroup, Group, Tab, and TabPage) can override the settings on the child controls.

The properties for form controls are listed in the following table.

A, B, C, D, E, F, G, H, I, K, L, M, N, O, P, R, S, T, U, V, W

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
<td><p><span id="A"></span></p>
<p><strong>A</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>AcquireFocus</strong></p></td>
<td><p>Specify whether a button or menu button in an action pane gets focus. Use <strong>Yes</strong> to have the button temporarily get focus when clicked. Use <strong>No</strong> when the button should not get focus. The default value is <strong>Yes</strong>.</p>
> [!caution]  
> <P>Set the property to <strong>Yes</strong> when a button or menu button control appears in an action pane.</P>
</td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>ActiveBackColor</strong></p></td>
<td><p>Sets the background color of the current record in a grid.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>ActiveForeColor</strong></p></td>
<td><p>Sets the text color of the current record in a grid.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>AlignChild</strong></p></td>
<td><p>Determines whether a control within a group should follow the <strong>AlignChildren</strong> property setting for the group or overall form design.</p>
<p>For example, if <strong>AlignChildren</strong> is set to <strong>Yes</strong> on the form <strong>Design</strong> node, you might not want a particular group to be arranged with the other groups. In that case, set <strong>AlignChild</strong> to <strong>No</strong> on that group.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>AlignChildren</strong></p></td>
<td><p>Aligns the child controls within a container.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>AlignControl</strong></p></td>
<td><p>Defines whether controls should be aligned. The top left corner of the controls are aligned according to the longest label.</p>
<p>Use this property to align a number of edit fields.</p>
<p>To align all the controls within a group, use the <strong>AlignChildren</strong> property.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Alignment</strong></p></td>
<td><p>Changes the alignment of the text in the control (Left, Right, Center).</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>AllowEdit</strong></p></td>
<td><p>Specify whether you can modify the data in the control.</p>
<p>When this property is set on a container control, modifications are disabled or enabled for all controls within the container.</p>
> [!caution]  
> <P>The fields that appear in a ListView control remain editable after you set <strong>AllowEdit</strong> to <strong>No</strong>.</P>
</td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>AllowNegative</strong></p></td>
<td><p>Determines whether integers displayed in IntEdit, Int64Edit, and RealEdit controls can be negative.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>AllowUserSetup</strong></p></td>
<td><p>Specifies whether users can move controls on a form, and whether they can change control properties.</p>
<p>This property is also found on the design of a form. The property has the following outcomes:</p>
<ul>
<li><p>No – users cannot customize any controls in this container.</p></li>
<li><p>Restricted– users can change properties of individual controls, but cannot move controls.</p></li>
<li><p>Yes – no restrictions on user setup.</p></li>
</ul>
<p><strong>Yes</strong> is the default value for <strong>AllowUserSetup</strong>.</p>
<p>Full user setup is not allowed if any of the parent containers for the control have restrictions on the user setup level.</p>
<p>The <strong>AllowAdd</strong> property on form data sources determines whether a user can add a new field to a form.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>AlternateRowShading</strong></p></td>
<td><p>Determines whether alternate rows of a Grid control are shaded or not.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>AnimateFile</strong></p></td>
<td><p>Specifies the name of the .avi file to be used in an Animate control. For a list of the .avi files supplied with Microsoft Dynamics AX, see the AviFiles macro.</p>
> [!note]  
> <P>The .avi file must not have a soundtrack.</P>
</td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>AppendNew</strong></p></td>
<td><p>Adds new text to the list of options in a ComboBox control.</p>
<p>This enables users to add new options to the list.</p>
<p>This property can be used only on unbound controls (those not linked to a table field).</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ArrangeMethod</strong></p></td>
<td><p>Determines how the controls within a container control should be arranged (Vertical, Horizontal flush left, Horizontal flush right).</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>ArrangeWhen</strong></p></td>
<td><p>Determines when the controls in the container should be arranged (Startup, On demand, Never).</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ArrayIndex</strong></p></td>
<td><p>Specifies the array element to be displayed in the control. If <strong>ArrayIndex</strong>=0, all elements are displayed.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>AssemblyName</strong></p></td>
<td><p>Specifies the name of the assembly that contains a ManagedHost control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>AutoArrange</strong></p></td>
<td><p>Determines whether the items in a ListView control should be arranged automatically.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>AutoDeclaration</strong></p></td>
<td><p>Determines whether the system should declare a variable of the same name as the control.</p>
<p>Set to Yes to refer to the control in X++ code on the form.</p>
> [!note]  
> <P>Each control must have a unique name.</P>
</td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>AutoInsSeparator</strong></p></td>
<td><p>Determines whether a decimal separator is inserted automatically in a RealEdit control.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>AutoPlay</strong></p></td>
<td><p>Determines whether the .avi file in an Animate control should play automatically when the form is opened.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>AutoRefreshData</strong></p></td>
<td><p>Determines whether the .data in the datasource associated with the control is refreshed when the control is clicked.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="B"></span></p>
<p><strong>B</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>BackgroundColor</strong></p></td>
<td><p>Determines the color used for the background of the control. To set the background to opaque or transparent, use the <strong>BackStyle</strong> property.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>BackStyle</strong></p></td>
<td><p>Sets the background of the control to opaque or transparent.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Big</strong></p></td>
<td><p>Specifies whether to make the control big.Large buttons should be used to represent the most frequently used tasks in a button group.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>Bold</strong></p></td>
<td><p>Displays text in another style (for example, Semi-bold, Bold, Heavy).</p>
<p>For more information about styles, see the <strong>Font</strong> and <strong>Underline</strong> properties later in this topic.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Border</strong></p></td>
<td><p>Determines the border type of the control (None, Single line, 3D).</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>BottomMargin</strong></p></td>
<td><p>Sets the default bottom margin in pixels of the controls within a container.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ButtonDisplay</strong></p></td>
<td><p>Determines whether button controls display an image, text only, or both text and the image.</p>
<p>The button's text is set by using the <strong>Text</strong> property.</p>
<p>The image is set by using the <strong>NormalImage</strong> and <strong>DisabledImage</strong> properties.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="C"></span></p>
<p><strong>C</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheDataMethod</strong></p></td>
<td><p>Specifies whether the DataMethod is cached during the <strong>FormDataSource</strong> init method call.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>CanScroll</strong></p></td>
<td><p>Determines whether users can scroll down the list or tree items.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Caption</strong></p></td>
<td><p>Specifies the heading for grouped controls. Use a label for this property.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Center</strong></p></td>
<td><p>Determines whether the .avi file in an Animate control should be centered in the control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ChangeCase</strong></p></td>
<td><p>Determines whether the system should automatically change the case of any text entered in a StringEdit control. For example, text can be changed to uppercase or sentence-case.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>CheckBox</strong></p></td>
<td><p>Adds a check box to a ListView or Tree control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassName</strong></p></td>
<td><p>Specifies the class ID of an ActiveX control or an HTML control. The class ID is also used during run time.</p>
<p>The <strong>ClassName</strong> property is automatically set when you create the control and cannot be changed. For HTML controls, <strong>ClassName</strong> is always HTML Document. For ActiveX controls, <strong>ClassName</strong> depends on the type of ActiveX data object you select in the <strong>ActiveX Browser</strong> dialog when you create the control.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>ColorScheme</strong></p></td>
<td><p>Determines the control's color palette.</p>
<p>To change the color palette for an entire form, set the <strong>ColorScheme</strong> property for the largest container and keep the default values for the individual controls.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Column</strong></p></td>
<td><p>Determines which column is initially active in a Table control.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>ColumnHeader</strong></p></td>
<td><p>Determines whether the columns in a ListView control should have a heading.</p>
<p>This is only valid when the <strong>ViewType</strong> property is set to Details.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ColumnHeaderButton</strong></p></td>
<td><p>Places a button in the header of a ListView control that allows the sort order to be defined.</p>
<p>The <strong>ColumnHeaderButton</strong> property is only valid when the <strong>ColumnHeader</strong> property has also been set, and the <strong>ViewType</strong> property has been set to Details.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>ColumnImages</strong></p></td>
<td><p>Determines whether each item in the column of a ListView control includes an image.</p>
<p>Use the <strong>SmallIcons</strong> property to set the name of the file that contains the icons.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Columns</strong></p></td>
<td><p>Sets the number of columns that display the information.</p>
> [!note]  
> <P>Field groups on the underlying table are never split into more than one column.</P>
</td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>ColumnSpace</strong></p></td>
<td><p>Sets the amount of space between columns in container controls.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ComboType</strong></p></td>
<td><p>Sets the type of box to use in a ComboBox control (Standard or List).</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Command</strong></p></td>
<td><p>Defines the command to activate when the user presses a CommandButton control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfigurationKey</strong></p></td>
<td><p>Specifies the configuration key used to control display of this control.</p>
<p>If a user doesn't have access to the configuration key, the control will not be visible.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>ContextFlyout</strong></p></td>
<td><p>Specifies whether the context flyout is enabled.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>CopyCallerQuery</strong></p></td>
<td><p>Specifies whether to copy the query from the calling form to the target form. This enables the target form to show the same data that appeared in the original form. The following list describes the value that you can use. The default value is <strong>Auto</strong>.</p>
<ul>
<li><p><strong>Auto</strong> – If the value is <strong>Auto</strong> and the <strong>CopyCallerQuery</strong> property of the menu item is <strong>Auto</strong>, the caller query is not copied. If the value is <strong>Auto</strong> but the <strong>CopyCallerQuery</strong> property of the menu item is <strong>Yes</strong> or <strong>No</strong>, the menu item determines whether the query is copied.</p></li>
<li><p><strong>No</strong> – The caller query is not copied. The menu item properties determine the query that is used.</p></li>
<li><p><strong>Yes</strong> - The caller query is copied. In addition, the query specified by the <strong>Query</strong> property of the menu item is ignored.</p></li>
</ul></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>CountryRegionCodes</strong></p></td>
<td><p>Specifies the country region codes where the table is applicable or valid. The client framework and application may use this property to enable or disable country or region specific features. This is implemented as a comma-separated list of ISO country codes in a single string. The values must match data that is contained in the global address book.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>CountryRegionContextField</strong></p></td>
<td><p>Specify the field that sets the country context for the control. Populate this property with a <strong>DataAreaId</strong> or <strong>PartyId</strong> field. This property is related to the <strong>CountryRegionCodes</strong> property.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>Custom</strong></p></td>
<td><p>Opens the property sheet for an ActiveX control.</p>
<p>Click the button in this property field to access the ActiveX properties for control.</p>
> [!note]  
> <P>The form must be in Design view, before you select the button. Right-click on the <strong>Design</strong> node of the form and select <strong>Edit</strong>. Not all ActiveX controls have a property sheet, and some controls do not allow you to edit it.</P>
> <P>For more information, see <a href="how-to-add-activex-controls-to-forms.md">How to: Add ActiveX Controls to Forms</a>.</P>
</td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="D"></span></p>
<p><strong>D</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DataField</strong></p></td>
<td><p>Specifies which field on the underlying table supplies data for the control.</p>
<p>The table is set by using the <strong>DataSource</strong> property.</p>
> [!note]  
> <P>If you set the <strong>DataSource</strong> and <strong>DataField</strong> properties, any settings made on the <strong>DataMethod</strong> or <strong>ExtendedDataType</strong> properties will be overridden.</P>
</td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>DataGroup</strong></p></td>
<td><p>Specifies the group of fields from the underlying table that is displayed in a Grid or Group control.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DataMethod</strong></p></td>
<td><p>Activates a method on the control (instead of data being displayed from an underlying field). The method may be selected from the following:</p>
<ul>
<li><p>The table that is used as a data source for the form</p></li>
<li><p>The <strong>Methods</strong> node within the <strong>Data Sources</strong> node on the form</p></li>
<li><p>The <strong>Methods</strong> node on the form</p></li>
</ul>
> [!note]  
> <P>If you set the <strong>DataSource</strong> and <strong>DataField</strong> properties, any settings made on the <strong>DataMethod</strong> property will be overridden.</P>
</td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>DataSource</strong></p></td>
<td><p>Determines which table data is displayed from in the control.</p>
<p>To set a particular field within this table, use the <strong>DataField</strong> property.</p>
<p>If the control opens another form, relations between the data source specified here for the control and the data source on the other form will ensure that records in the second form are dynamically selected.</p>
<p>For example, if a customer is selected in one form, and the control opens up a form showing customer transactions, a range of customer transactions applying to the current customer would be displayed in the second form.</p>
> [!note]  
> <P>If you set the <strong>DataSource</strong> and <strong>DataField</strong> properties, this will override any settings made on the <strong>DataMethod</strong> or <strong>ExtendedDataType</strong> properties.</P>
</td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DateDay</strong></p></td>
<td><p>Determines how the day (within the date) should be displayed in a DateEdit control. You can also choose not to display the day.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>DateFormat</strong></p></td>
<td><p>Determines the layout of a date (the order in which day, month, and year are displayed).</p>
<p>If this property is set to Auto, settings are inherited from the extended data type. If this property is also set to Auto on the extended data type, system settings are used.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DateMonth</strong></p></td>
<td><p>Determine how the month should be displayed in a DateEdit control (text, digits, or not shown).</p>
<p>If this property is set to Auto, settings are inherited from the extended data type. If this property is also set to Auto on the extended data type, system settings are used.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>DateSeparator</strong></p></td>
<td><p>Determines the separator between year, month, and day in a DateEdit control.</p>
<p>If this property is set to Auto, settings are inherited from the extended data type. If this property is also set to Auto on the extended data type, system settings are used.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DateTimeValue</strong></p></td>
<td><p>Specifies the initial value in a UtcDateTimeEdit control.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>DateValue</strong></p></td>
<td><p>Enables you to specify a specific date for a DateEdit control instead of using a data source.</p>
> [!note]  
> <P>This property is not used if the <strong>DataSource</strong> and <strong>DataField</strong> properties are set.</P>
</td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DateYear</strong></p></td>
<td><p>Determines how the year should be displayed in a DateEdit control (two or four digits, or not shown).</p>
<p>If this property is set to Auto, settings are inherited from the extended data type. If this property is also set to Auto on the extended data type, system settings are used.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>DecimalSeparator</strong></p></td>
<td><p>Specifies the decimal separator for a RealEdit control (&quot;,&quot; or &quot;.&quot;).</p>
<p>If this property is set to Auto, settings are inherited from the extended data type. If this property is also set to Auto on the extended data type, system settings are used.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DefaultAction</strong></p></td>
<td><p>Determines the default action that is executed when a row in a Grid control is double-clicked or the ENTER key is pressed. Select the name of the action pane button that represents the action to perform.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>DefaultActionLabel</strong></p></td>
<td><p>Determines the name that displays in the context menu for the default action on a row in a Grid. The action is specified in the <strong>DefaultAction</strong> property.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DefaultButton</strong></p></td>
<td><p>Specifies whether a button control should be the default button.</p>
<p>If this property is set to Yes, the button is selected when the user presses ENTER when the form is open.</p>
> [!note]  
> <P>The <strong>Frame</strong> property on the form design must be set to Dialog for this property to have an effect.</P>
</td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Direction</strong></p></td>
<td><p>Specifies whether the progress bar should be drawn horizontally or vertically in a Progress control.</p>
> [!note]  
> <P>Do not use a Progress control in a form. Use the Progress Indicators framework instead. For more information, see <a href="how-to-create-progress-indicators.md">How to: Create Progress Indicators</a>.</P>
</td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DisabledImage</strong></p></td>
<td><p>Specifies the image to use when the button is disabled. If this property is not set, the system generates a disabled image based on the setting for the <strong>NormalImage</strong> property.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>DisabledImageLocation</strong></p></td>
<td><p>Specifies the location of the image to use for a disabled control. You can use images found in a file, the <strong>Resources</strong> node of the AOT, or an <strong>EmbeddedResource</strong>.</p>
<p>The selection made in this property determines what values are used to populate the <strong>DisabledImage</strong> property. If the property is not set, the system generates a disabled image based on the setting of the <strong>ImageLocation</strong> property.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>DisplaceNegative</strong></p></td>
<td><p>Indents a negative number to the right.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>DisplayHeight</strong></p></td>
<td><p>Limits the height of the control.</p>
<p>Use this property in conjunction with the <strong>MultiLine</strong> property to define a data entry field that can span several lines.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DisplayLength</strong></p></td>
<td><p>Limits the number of characters displayed in the control.</p>
<p>This property determines the width of the control in number of characters. The <strong>Width</strong> property is specified in pixels.</p>
<p>The <strong>LimitText</strong> property determines how many characters can be entered in the control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>DisplayOption</strong></p></td>
<td><p>Specifies whether the <strong>DateTimeEdit</strong> control should display the date and time, or just the date without the time.</p>
<p>The following list shows the valid values for this property, in the sequence that they are listed in the AOT Property window's drop-down list. The corresponding integer value for each label matches its position in the list, starting from 0:</p>
<ul>
<li><p>0 – <strong>Auto</strong></p></li>
<li><p>1 – <strong>Date and Time</strong></p></li>
<li><p>2 – <strong>Date</strong></p></li>
</ul>
<p><strong>Auto</strong> defaults to <strong>Date and Time</strong>. <strong>Auto</strong> is overridden if the parent (or another parent in the sequence) is specifically set to a value other than <strong>Auto</strong>.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DragDrop</strong></p></td>
<td><p>Enables the field to be moved with a drag-and-drop operation.</p>
> [!note]  
> <P>Drag-and-drop fields require code to support them. For examples, see the tutorial_FormListControl and tutorial_FormTreeControl forms.</P>
</td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="E"></span></p>
<p><strong>E</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>EditLabels</strong></p></td>
<td><p>Determines whether the user can change the name of a node in a Tree or ListView control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Enabled</strong></p></td>
<td><p>Disables the control when the property is set to <strong>No</strong>.</p>
<p>To allow the control to be disabled (depending on licensing rights and system configuration), use the <strong>ConfigurationKey</strong> property instead.</p>
<p>To allow access control for different user groups, use the <strong>NeededAccessLevel</strong> property.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>EnumType</strong></p></td>
<td><p>Gives a control access to the values in an enumerated type. For example, a control listing possible currencies.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ExtendedDataType</strong></p></td>
<td><p>Bases the control on an extended data type.</p>
> [!note]  
> <P>If you set the <strong>DataSource</strong> and <strong>DataField</strong> properties, or the <strong>DataMethod</strong> property, this will override any settings made on the <strong>ExtendedDataType</strong> property.</P>
</td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="F"></span></p>
<p><strong>F</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>FastTabSummary</strong></p></td>
<td><p>Specifies whether the value of the control appears in the Fast Tab header as a summary field. Options are <strong>Yes</strong>, <strong>No</strong>, <strong>Auto</strong>. Default is <strong>Auto</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>Font</strong></p></td>
<td><p>Enables you to select another font for the control by opening a font selection dialog.</p>
<p>The <strong>FontSize</strong>, <strong>Bold</strong>, <strong>Underline</strong>, and <strong>Italic</strong> properties can be set individually or by using the font selection dialog.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>FontSize</strong></p></td>
<td><p>Changes the size of the text in a control.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>ForcedToOverflow</strong></p></td>
<td><p>Specifies whether the control will always be forced to overflow.</p>
<p>If you have a rarely used button that has to be available but not visible, add that button to the button group overflow menu. The overflow menu provides access to any buttons that are not displayed on the action pane. To access the button, click the overflow menu indicator on the right side of the button group.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>ForegroundColor</strong></p></td>
<td><p>Determines the color used for the foreground of the control.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>FormatMST</strong></p></td>
<td><p>Determines whether the value in a RealEdit control is formatted according to the national currency. Following are the possible values:</p>
<ul>
<li><p>Auto – The national currency formatting depends on the data type.</p></li>
<li><p>No – The value is not formatted according to the national currency.</p></li>
<li><p>Yes – The value is formatted according to the national currency.</p></li>
</ul></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>FormViewOption</strong></p></td>
<td><p>Specifies the form mode to use. Options are Auto, Grid or Details. Default value is <strong>Auto</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>FrameOptionButton</strong></p></td>
<td><p>Allows you to add a button above a Group control. Following are the possible values:</p>
<ul>
<li><p>None – No button is added.</p></li>
<li><p>Check – Adds a check box that enables the user to disable all the fields in the group.</p></li>
<li><p>Radio – Adds radio buttons to a group of Groups. The Group controls must be nested inside another Group control. The user can then select one of the radio buttons, and the other groups of controls are disabled.</p></li>
<li><p>Hide – Adds a collapse button that enables the user to hide the fields in the group.</p></li>
</ul></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>FramePosition</strong></p></td>
<td><p>Changes the position of the frame for a ButtonGroup, Group, or Window control.</p>
<p>Changes to this property are not visible if the <strong>FrameType</strong> property is set to Auto or None.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>FrameType</strong></p></td>
<td><p>Changes the default frame type, which is None.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="G"></span></p>
<p><strong>G</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>GridLines</strong></p></td>
<td><p>Determines whether grid lines should be displayed in Grid, ListView, or Table controls.</p>
<p>For ListView controls, this property is only valid when the <strong>ViewType</strong> property is set to Details.</p>
<p>By default, this property is set to <strong>Yes</strong>.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>GridLinesStyle</strong></p></td>
<td><p>Determines which grid lines should be drawn in Grid, ListView, or Table controls. Options are Auto, None, Vertical, All</p>
<p>By default, this property is set to <strong>Auto</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><span id="H"></span></p>
<p><strong>H</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>HasButtons</strong></p></td>
<td><p>Determines whether expand/collapse buttons are displayed in a Tree control.</p>
<p>To display an expand/collapse button at the root of the tree, use the <strong>LinesAtRoot</strong> property.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>HasLines</strong></p></td>
<td><p>Determines whether connector lines are displayed in a Tree control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Headerdragdrop</strong></p></td>
<td><p>Makes it possible to rearrange the columns in a ListView control.</p>
<p>This property is valid only when the <strong>ViewType</strong> property is set to Details.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Height</strong></p></td>
<td><p>Changes the height of the control. The height is specified in pixels.</p>
> [!note]  
> <P>For more information about the <strong>Height</strong> and <strong>Width</strong> properties, see the tutorial_arrange form.</P>
</td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>HelpText</strong></p></td>
<td><p>Determines the Help string for the control. The Help string is shown in the status bar when a user points to the control with a mouse pointer.</p>
<p>If you don't enter a value for this property, it will be inherited from the field or the extended data type that the control is based on.</p>
> [!note]  
> <P>You must use a label to specify the content for this property.</P>
</td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>HideFirstEntry</strong></p></td>
<td><p>Emulates the behavior of an enum database field with the <strong>Mandatory</strong> property set to Yes—the user cannot select an empty value.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>HideIfEmpty</strong></p></td>
<td><p>Enables you to hide a container control if it is empty.</p>
<p>This property has no affect if the container control has its <strong>Width</strong> and <strong>Height</strong> properties set to Auto because the size of the control is then zero.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>HierarchyParent</strong></p></td>
<td><p>Specifies the parent of the element in the <strong>Model</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>HighlightActive</strong></p></td>
<td><p>Enables you to display the current record in a different color in a grid.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="I"></span></p>
<p><strong>I</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ImageLocation</strong></p></td>
<td><p>Specifies the location of the image to use, You can use images found in a file, the <strong>Resources</strong> node of the AOT, or an <strong>EmbeddedResource</strong>. The selection made in this property determines what values are used to populate the <strong>NormalImage</strong> property.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>ImageMode</strong></p></td>
<td><p>Defines how the bitmap specified by the <strong>ImageName</strong> property will be displayed in a Window control (Normal, Size to fit, Side by side, Center).</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ImageName</strong></p></td>
<td><p>Determines which image is displayed for a Window control. You can select only .bmp files.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>ImageResource</strong></p></td>
<td><p>Specifies the resource ID for the image displayed for a Window control.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>IMEMode</strong></p></td>
<td><p>Enables you to disable the Input Method Editor (IME) input mode for edit controls.</p>
<p>The IME mode enables the user to input data from non-Latin languages, such as Japanese.</p>
<p>This property is enabled by default.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Italic</strong></p></td>
<td><p>Displays the text in italics.</p>
<p>For more information, see the <strong>Font</strong> property in this topic.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Item</strong></p></td>
<td><p>Enables you to specify the label for each item in a ComboBox, ListBox, or RadioButton control.</p>
<p>Type the number of the item in the <strong>Item</strong> property box, and then set the <strong>Text</strong> property for that item. Repeat this for the next item(s).</p>
<p>The total number of items in the control must be set in the <strong>Items</strong> property.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>ItemAlign</strong></p></td>
<td><p>Aligns the items in a ListView control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Items</strong></p></td>
<td><p>Determines how many items are in a ComboBox, ListBox, or RadioControl control.</p>
<p>To specify the label for each item, type the number of the item in the <strong>Item</strong> property, and then set the <strong>Text</strong> property. Repeat this for the next item(s).</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="K"></span></p>
<p><strong>K</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>KeyTip</strong></p></td>
<td><p>Defines the character used for the key tip.</p>
<p>Key tips enable you to click action pane tabs, button groups, and buttons using the keyboard. When you press ALT the action pane displays a letter next to each tab, button group, or button that you can access. To click a button, press the key that represents the button that you want to use.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><span id="L"></span></p>
<p><strong>L</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Label</strong></p></td>
<td><p>Sets the text supplied as a label for the control.</p>
<p>If you don't enter a Label, it will be inherited from the field or the extended data type that the control is based on.</p>
<p>To specify the labels for each item in a ComboBox, ListBox or RadioButton control, use the <strong>Item</strong> and <strong>Text</strong> properties.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>LabelAlignment</strong></p></td>
<td><p>Determines the alignment of the label (Left, Right, Center). If there is more than one control in a group, the longest label defines the point of alignment.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>LabelBold</strong></p></td>
<td><p>Displays the label defined by the <strong>Label</strong> property in another style (for example, Semi-bold, Bold, Heavy).</p>
<p>For more information, see the <strong>LabelFont</strong> property in this topic.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>LabelFont</strong></p></td>
<td><p>Changes the font for the text supplied in the <strong>Label</strong> property.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>LabelFontSize</strong></p></td>
<td><p>Changes the size of the text supplied in the <strong>Label</strong> property.</p>
<p>For more information, see the <strong>LabelFont</strong> property in this topic.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>LabelForegroundColor</strong></p></td>
<td><p>Changes the color used for the label foreground.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>LabelHeight</strong></p></td>
<td><p>Not used.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>LabelItalic</strong></p></td>
<td><p>Italicizes the text supplied in the <strong>Label</strong> property.</p>
<p>For more information, see the <strong>LabelFont</strong> property in this topic.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>LabelPosition</strong></p></td>
<td><p>Determines whether the label appears to the left of the control or above it.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>LabelUnderline</strong></p></td>
<td><p>Underlines the text supplied in the <strong>Label</strong> property.</p>
<p>For more information, see the <strong>LabelFont</strong> property in this topic.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>LabelWidth</strong></p></td>
<td><p>Not used.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Left</strong></p></td>
<td><p>Changes the position of the uppermost left corner of the control.</p>
<p>There are a number of predefined settings (for example, Auto (left) and Auto (right)). You can also specify an exact position in pixels.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>LeftMargin</strong></p></td>
<td><p>Changes the default left margin of the controls in a container control. The margin is specified in pixels.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>LimitText</strong></p></td>
<td><p>Limits the number of characters that can be entered in a control.</p>
<p>The <strong>DisplayLength</strong> property limits the number of characters displayed in the control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>LinesAtRoot</strong></p></td>
<td><p>Determines whether there is an expand/collapse button at the root of the tree.</p>
<p>To display expand/collapse buttons for the remainder of the tree, use the <strong>HasButtons</strong> property.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>LookupButton</strong></p></td>
<td><p>Displays a button to look up a value in the database for the control.</p>
<p>The Lookup is set up by using a relation on the database table used as a data source for the field.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Loops</strong></p></td>
<td><p>Defines the number of times the .avi file should be played for an Animate control.</p>
<p>If you set <strong>Loops</strong> to 0 (zero), the .avi file will play indefinitely.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="M"></span></p>
<p><strong>M</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Mandatory</strong></p></td>
<td><p>Determines whether users must enter data in the control.</p>
<p>If <strong>Mandatory</strong> is set to Yes, a red wavy line is displayed on empty fields, and a warning is displayed if the user tries to navigate away from the field without completing it.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>MaxDateLabel</strong></p></td>
<td><p>Specifies the text to be displayed when the value is the maximum date value.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>MenuItemName</strong></p></td>
<td><p>Determines which menu item is run for a MenuItemButton control.</p>
<p>You must also set the <strong>MenuItemType</strong> property.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>MenuItemType</strong></p></td>
<td><p>Determines which type of menu item is run for a MenuItemButton control (Display, Output, or Action).</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>MinNoOfDecimals</strong></p></td>
<td><p>Determines whether trailing zeros are removed when the data is displayed for a RealEdit control.</p>
<p>For example, if you set the <strong>MinNoOfDecimals</strong> to 6, a value of 2.1234500000 would be truncated to 2.12450.</p>
<p><span id="yb22minnodecim"></span> If you set <strong>MinNoOfDecimals</strong>, it must be less than the value given for the <strong>NoOfDecimals</strong> property.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Model</strong></p></td>
<td><p>Specifies the model that includes the control.</p>
<p>A model is a logical grouping of elements in a layer. An element can be located in exactly one model in a layer. Examples of elements are a table or class. The same element can be located in a customized version in a model in a higher layer.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>MoreRowsIndicator</strong></p></td>
<td><p>Specifies whether an ellipsis indicator row should be displayed in a Grid control when more rows are available but not shown.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>MultiLine</strong></p></td>
<td><p>Enables text to span several lines in a StringEdit control. If the property is set to Yes, vertical scroll bars are automatically added.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>MultiSelect</strong></p></td>
<td><p>Determines whether a button is active when the user makes multiple selections, or, on a Grid control, the property determines whether it is possible to make multiple selections.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="N"></span></p>
<p><strong>N</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Name</strong></p></td>
<td><p>Determines the name of the control.</p>
> [!note]  
> <P>Each control name must be unique—it allows the automatic declaration of controls as variables.</P>
</td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>NeededPermission</strong></p></td>
<td><p>Specifies the minimum permission level needed to allow access to the control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>NeedsRecord</strong></p></td>
<td><p>Specifies whether the control will be enabled when no records are present.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>NoOfDecimals</strong></p></td>
<td><p>Determines the number of decimals shown when a value is displayed in a RealEdit control.</p>
<p>To remove trailing zeros at the end of the value set, the <strong>MinNoOfDecimals</strong> property.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>NormalImage</strong></p></td>
<td><p>Specifies the button image to be used when the button is enabled.</p>
<p>To set the image for the button when it is disabled, use the <strong>DisabledImage</strong> property.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="O"></span></p>
<p><strong>O</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>OneClickActivate</strong></p></td>
<td><p>Determines whether the items in a ListView control can be activated with a single click.</p>
<p>This property is valid only when the <strong>ViewType</strong> property is set to Details.</p>
<p>For more information, see <strong>TwoClickActivate</strong> in this topic.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>OpenMode</strong></p></td>
<td><p>Specifies the view mode of the target form. The possible values include the following:</p>
<ul>
<li><p>Auto</p></li>
<li><p>View</p></li>
<li><p>Edit</p></li>
<li><p>New</p></li>
</ul>
<p>The default value is <strong>Auto</strong>.</p>
<p>You use this property to specify whether the target form opens in edit or read-only mode.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>OptionalRecordControl</strong></p></td>
<td><p>Specifies whether the checkbox state controls the optional record associated with the <strong>Datasource</strong> property. Default is <strong>No</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>OptionValue</strong></p></td>
<td><p>Enables you to select a button that was added by using the <strong>FrameOptionButton</strong> property. For example, if the <strong>FrameOptionButton</strong> property is set to Check, setting the <strong>OptionValue</strong> property to 1 selects the check box when the form is opened.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="P"></span></p>
<p><strong>P</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Parameters</strong></p></td>
<td><p>Specifies one or more values passed to an object. These resemble the parameters passed to method. A parameter supplies a value that is then used to perform the task. There is no default value.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>PasswordStyle</strong></p></td>
<td><p>Enables you to display asterisks (*) instead of the characters that a user enters when they type data in a StringEdit control.</p>
<p>Because of security considerations, it is not advisable to store credentials in the database. When you want to protect functionality with a password, prompt users to enter it each time, and use the <strong>PasswordStyle</strong> property to obscure the password as the user types it in.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Pos</strong></p></td>
<td><p>Enables you to set a non-default initial value for a Progress control. If you don't set this property, the initial value will be the value specified by the <strong>RangeLo</strong> property. The maximum value of <strong>Pos</strong> is determined by the <strong>RangeHi</strong> property.</p>
> [!note]  
> <P>Do not use a Progress control in a form. Use the Progress Indicators framework instead. For more information, see <a href="how-to-create-progress-indicators.md">How to: Create Progress Indicators</a>.</P>
</td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>PresenceDataField</strong></p></td>
<td><p>Specifies the field containing a lookup value to supply to get <strong>PresenceFileData</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>PresenceDataSource</strong></p></td>
<td><p>Specifies the data source containing the <strong>getPresenceFieldData</strong> for the control.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>PresenceIndicatorAllowed</strong></p></td>
<td><p>Specifies whether or not to display a presence indicator.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>PreviewPartRef</strong></p></td>
<td><p>Specifies the <strong>Info Part</strong> or <strong>Form Part</strong> to be used in the enhanced preview.</p>
<p>An info part shows a collection of data fields from a specified query. An info part uses metadata to describe how the data appears. A form part represents a pointer to a form.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>Primary</strong></p></td>
<td><p>Specifies whether a control is primary or secondary in display priority.</p>
<p>A primary is a control that overrides the position rules that the control group uses to add controls to the overflow menu. Specify a control as primary when you want that control to be the last added to control group overflow menu.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressType</strong></p></td>
<td><p>Determines how progression is shown in a Progress control (Normal or Smooth).</p>
> [!note]  
> <P>Do not use a Progress control in a form. Use the Progress Indicators framework instead. For more information, see <a href="how-to-create-progress-indicators.md">How to: Create Progress Indicators</a>.</P>
</td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="R"></span></p>
<p><strong>R</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>RangeHi</strong></p></td>
<td><p>Sets the maximum range of the progress bar for a Progress control.</p>
> [!note]  
> <P>Do not use a Progress control in a form. Use the Progress Indicators framework instead. For more information, see <a href="how-to-create-progress-indicators.md">How to: Create Progress Indicators</a>.</P>
</td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>RangeLo</strong></p></td>
<td><p>Sets the minimum range of the progress bar for a Progress control.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>RealValue</strong></p></td>
<td><p>Determines the initial value for a RealEdit control. This is typically used for an unbound control (a control not bound to a data field).</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferenceField</strong></p></td>
<td><p>Specifies a reference field on the bound data source to use as the physical binding.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplacementFieldGroup</strong></p></td>
<td><p>Specifies the field group that appears in the form when you add a surrogate foreign key field to that form.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceOnLookup</strong></p></td>
<td><p>Determines whether look-up text replaces the current content of the field or adds to the current content.</p>
<p>If <strong>ReplaceOnLookup</strong> is set to Yes, the content of the field is replaced by text selected in a look-up. If <strong>ReplaceOnLookup</strong> is set to No, the text selected in a look up is added to the existing content of the field at the cursor position.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>RightMargin</strong></p></td>
<td><p>Changes the default right margin of the controls within a container control. The margin is specified in pixels.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>RotateSign</strong></p></td>
<td><p>Negates the number in an IntEdit, Int64Edit, or RealEdit control (changes - to + and vice versa).</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Row</strong></p></td>
<td><p>Determines which row in a Table control is active when the form or tab is opened.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Rows</strong></p></td>
<td><p>Changes the number of rows used to display information.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>RowSelect</strong></p></td>
<td><p>Determines whether an entire row is selected when it is clicked in a ListView control (rather than a single element).</p>
<p>This property is valid only when the <strong>ViewType</strong> property is set to Details.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>RTLCapable</strong></p></td>
<td><p>Determines whether an ActiveX, HTML, or ManagedHost control supports RTL languages.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="S"></span></p>
<p><strong>S</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>SaveRecord</strong></p></td>
<td><p>Determines whether changes to the current record are saved when a Button, CommandButton, MenuButton, or MenuItemButton control is selected.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Scrollbars</strong></p></td>
<td><p>Determines whether scroll bars are enabled on a TabPage control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>SearchMode</strong></p></td>
<td><p>Sets the search mode in grids for edit controls.</p>
<p>By default, this property is set to None. If you set <strong>SearchMode</strong> to <strong>SearchAfterInput</strong>, text typed into the control is applied as a filter when the user presses ENTER. If you set it to <strong>SearchOnTyping</strong>, the grid scrolls to the first record that matches the text that the user typed.</p>
<p>The <strong>SearchMode</strong> property is most relevant for controls that can't be edited. Use this property with caution—the grid will load all the records that are available to do the text-matching.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>SelectControl</strong></p></td>
<td><p>Determines whether the first control is selected when a user opens a tabbed page.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Selection</strong></p></td>
<td><p>Sets the initial value for a ComboBox, ListBox, or RadioButton control.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>SendExternalContext</strong></p></td>
<td><p>Specifies whether or not the external record context of this form should be sent as the menu item’s external record context. Default value is <strong>No</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>ShowColLabels</strong></p></td>
<td><p>Determines whether the label defined by the <strong>Label</strong> property is shown as a column heading for controls on Grids or Tables.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>ShowLabel</strong></p></td>
<td><p>Determines whether the label defined by the <strong>Label</strong> property is displayed for the control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ShowRowLabels</strong></p></td>
<td><p>Displays a column where the current record in a grid or table is indicated by an arrow, and new records are indicated by an asterisk.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>ShowSelAlways</strong></p></td>
<td><p>Determines whether an item in a Tree or ListView control should remain selected when the user moves focus away from the item.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ShowShortCut</strong></p></td>
<td><p>Determines whether access keys should be displayed.</p>
<p>An access key is a keyboard shortcut (letter+ALT) for opening a menu item or button. The letter is underlined in the name of the menu item.</p>
<p>Access keys are generated automatically.</p>
<p>This property is typically set to No when a form has so many buttons that no more letters are available.</p>
<p>For more information about access keys, see <a href="access-keys-on-forms.md">Access Keys on Forms</a>.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>ShowTabs</strong></p></td>
<td><p>Determines whether tabbed pages should be displayed on a Tab control. If set to No, information on only the first tabbed page is shown.</p>
<p>You can reference the other tabbed pages from your X++ code.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ShowZero</strong></p></td>
<td><p>Determines whether the value zero is displayed in an IntEdit, Int64Edit, or RealEdit control, or whether an empty field is shown instead.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>SignDisplay</strong></p></td>
<td><p>Displays the sign of a number if the value is negative. Also determines whether the sign is displayed before or after the number. The default value is Auto.</p>
> [!note]  
> <P>If you set the property to None, the sign might not be hidden when the control appears on a form.</P>
</td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>SingleSelection</strong></p></td>
<td><p>Determines whether the user can select several objects at a time in a ListView or Tree control, or whether the selections should be mutually exclusive.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>SizeHeight</strong></p></td>
<td><p>Sets all buttons in a ButtonGroup control to the same height.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>SizeWidth</strong></p></td>
<td><p>Sets all buttons in a ButtonGroup control to the same width.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Sizing</strong></p></td>
<td><p>Determines the size of a ManagedHost control. Set to SizeToContent if you want resizing to be governed by the control (up to the limits of the form size). Set to SizeToHost if you want the size to be set by the host.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Skip</strong></p></td>
<td><p>Determines whether the control is skipped when the TAB key is used to navigate through the form.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Sort</strong></p></td>
<td><p>Enables you to sort the data in a <strong>ListView</strong> control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Step</strong></p></td>
<td><p>Defines the integer value that the progress bar increases in one step.</p>
> [!note]  
> <P>Do not use a Progress control in a form. Use the Progress Indicators framework instead. For more information, see <a href="how-to-create-progress-indicators.md">How to: Create Progress Indicators</a>.</P>
</td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Style</strong></p></td>
<td><p>Specifies the style of the control. The default is <strong>Auto</strong>.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span id="T"></span></p>
<p><strong>T</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Tab</strong></p></td>
<td><p>Determines which tabbed page should be active when the form is opened.</p>
<p>If you do not set this property, the first tabbed page (<strong>Overview</strong> tab) opens by default.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>TabAppearance</strong></p></td>
<td><p>Enables you to display tabbed pages as buttons instead of tabs.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>TabAutoChange</strong></p></td>
<td><p>Changes the result of a user pressing the TAB key on the form. This action would normally result in a jump to the next field. If you set the <strong>TabAutoChange</strong> property, pressing the tab key instead results in a jump to the next tabbed page.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>TabLayout</strong></p></td>
<td><p>Defines how the tabs should be arranged if there are too many to fit in the default form width. You can arrange tabs on more than one line or add a scroll bar (Tunnel option).</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>TabPlacement</strong></p></td>
<td><p>Defines the position of the tabbed pages in a Tab control (Top, Left, Right, Bottom).</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Text</strong></p></td>
<td><p>Specifies a static text for the control. You must use a label to set this property.</p>
<p>For ComboBox, Listbox, and RadioButton controls, the <strong>Text</strong> property enables you to specify the label for each item in the control. Type the number of the item in the <strong>Item</strong> property, and then set the <strong>Text</strong> property for that item. (You must first set the total number of items by using the <strong>Lines</strong> property.) The <strong>Text</strong> property is typically set for controls that are not associated with an underlying data source. If the control is bound, the list or button text comes from the underlying data source.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>ThousandSeparator</strong></p></td>
<td><p>Sets the thousands separator for a RealEdit control—None, Comma, Dot, Space, or Apostrophe.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeFormat</strong></p></td>
<td><p>Changes the default time format (24 hour or AM/PM).</p>
<p>If this property is set to Auto, settings are inherited from the extended data type. If this property is also set to Auto on the extended data type, system settings are used.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>TimeHours</strong></p></td>
<td><p>Determines whether hours should be shown in a TimeEdit control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeMinute</strong></p></td>
<td><p>Determines whether minutes should be shown in a TimeEdit control.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>TimeSeconds</strong></p></td>
<td><p>Determines whether seconds should be shown in a TimeEdit control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeSeparator</strong></p></td>
<td><p>Determines the separator between hours, minutes, and seconds in a TimeEdit control (Colon, Dot, Space, Comma, Slash).</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZone</strong></p></td>
<td><p>The <strong>TimeZone</strong> property on the <strong>UTCDateTime</strong> control is a runtime only property (cannot be set in the AOT). Use this property to specify the time zone value to be displayed in the <strong>DateTimeEdit</strong> control when <strong>TimeZoneIndicator</strong> resolves to Always and <strong>TimezonePreference</strong> resolves to No Conversion.</p>
<p>This property has no effect on the date/time value displayed in the DateTimeEdit control.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZoneIndicator</strong></p></td>
<td><p>Specifies whether the small icon for displaying the time zone used for conversion from UTC should be visible on the DateTimeEdit control. This property setting is ignored if the <strong>TimezonePreference</strong> property setting resolves to <strong>No Conversion</strong>.</p>
<p>The following list shows the valid values for this property, in the sequence that they are listed in the AOT Property window's drop-down list. The corresponding integer value for each label matches its position in the list, starting from 0:</p>
<ul>
<li><p>0 – Auto</p></li>
<li><p>1 – Never</p></li>
<li><p>2 – Always</p></li>
</ul>
<p>If the <strong>TimezonePreference</strong> property resolves to User, the setting of <strong>Auto</strong> defaults to <strong>Always</strong> for <strong>TimeZoneIndicator</strong>. However, if <strong>TimezonePreference</strong> resolves to <strong>No Conversion</strong>, the setting of <strong>Auto</strong> defaults to <strong>Never</strong> for <strong>TimeZoneIndicator</strong>.</p>
<p><strong>Auto</strong> is overridden if the parent (or another parent in the sequence) is specifically set to a value other than <strong>Auto</strong>.</p>
<p>If <strong>TimeZoneIndicator</strong> is explicitly set to <strong>Always</strong>, and <strong>TimezonePreference</strong> is explicitly set to <strong>No Conversion</strong>, the time zone displayed by the icon is UTC.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>TimezonePreference</strong></p></td>
<td><p>Specifies the time zone that the DateTimeEdit control should use to convert to and from UTC.</p>
<p>The following list shows the valid values for this property, in the sequence that they are listed in the AOT Property window's drop-down list. The corresponding integer value for each label matches its position in the list, starting from 0:</p>
<ul>
<li><p>0 – Auto</p></li>
<li><p>1 – User</p></li>
<li><p>2 – No Conversion</p></li>
</ul>
<p><strong>Auto</strong> defaults to User. <strong>Auto</strong> is overridden if the parent (or another parent in the sequence) is specifically set to a value other than <strong>Auto</strong>.</p>
<p>The User value means the time zone preference configured for the current user.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ToggleButton</strong></p></td>
<td><p>Specifies the type of the toggle button. Options are Auto, None, Check, and Radio. The default value is <strong>Auto</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>ToggleValue</strong></p></td>
<td><p>Specifies the type of the toggle button. The default value is <strong>Off</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>Top</strong></p></td>
<td><p>Changes the position of the top of the control.</p>
<p>There are a number of predefined settings or you can specify in pixels an exact position.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>TopMargin</strong></p></td>
<td><p>Sets in pixels the default top margin of the controls within a container.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>TrackSelect</strong></p></td>
<td><p>Highlights each element within a ListView control when the user moves the mouse pointer across it.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Transparent</strong></p></td>
<td><p>Determines whether the background should be transparent for an Animate control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>TwoClickActivate</strong></p></td>
<td><p>Determines whether the items in a ListView control are activated with a double-click.</p>
<p>This property is valid only when the <strong>ViewType</strong> property is set to Details.</p>
<p>For more information, see <strong>OneClickActivate</strong> in this topic.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Type</strong></p></td>
<td><p>Specifies the type of control. Read-only.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>TypeName</strong></p></td>
<td><p>Sets the name of the type for a Managed control. Use the fully qualified name of the type.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="U"></span></p>
<p><strong>U</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Underline</strong></p></td>
<td><p>Underlines the text for the control.</p>
<p>For more information, see the <strong>Font</strong> property in this topic.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="V"></span></p>
<p><strong>V</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Value</strong></p></td>
<td><p>Sets the initial value for a CheckBox, GuidEdit, IntEdit, Int64Edit, or TimeEdit control.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>VerticalSpacing</strong></p></td>
<td><p>Changes the amount of space in pixels above and below the control.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ViewEditMode</strong></p></td>
<td><p>Specifies whether the control is in read-only mode or enables you to change values.</p>
<ul>
<li><p><strong>View</strong> - Opens as read-only</p></li>
<li><p><strong>Edit</strong> - Opens in edit mode</p></li>
<li><p><strong>Auto</strong> - Opens in appropriate mode</p></li>
</ul>
<p>The default is <strong>Auto</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>ViewType</strong></p></td>
<td><p>Defines the appearance of items in a ListView control (for example, with large or small icons).</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Visible</strong></p></td>
<td><p>Enables you to hide the control.</p>
> [!note]  
> <P>You cannot use the <strong>Visible</strong> property to enforce access restrictions. The user can change the visibility for the controls in the <strong>Form Setup</strong> dialog. Use the <strong>Enabled</strong> and <strong>NeededAccessLevel</strong> Properties instead.</P>
</td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>VisibleCols</strong></p></td>
<td><p>Limits the number of columns to be displayed for a Grid control. A scroll bar is automatically added to enable scrolling to the remaining columns.</p>
<p>When set to Auto, all columns are displayed.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>VisibleRows</strong></p></td>
<td><p>Limits the number of rows to be displayed for a Grid control. A scroll bar is automatically added to enable scrolling to the remaining rows.</p>
<p>When set to Auto, all rows are displayed.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span id="W"></span></p>
<p><strong>W</strong></p></td>
<td><p>N/A</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Width</strong></p></td>
<td><p>Changes the width in pixels of the control.</p>
> [!note]  
> <P>For more information about using the <strong>Height</strong> and <strong>Width</strong> properties, see the tutorial_arrange form.</P>
</td>
<td><p></p></td>
</tr>
</tbody>
</table>


## See also

[Form Controls Overview](form-controls-overview.md)

[Overview of Form Control Types](overview-of-form-control-types.md)

[Best Practices for Form Control Properties](best-practices-for-form-control-properties.md)

[Form Data Source Properties](form-data-source-properties.md)

[Form Design Properties](form-design-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

