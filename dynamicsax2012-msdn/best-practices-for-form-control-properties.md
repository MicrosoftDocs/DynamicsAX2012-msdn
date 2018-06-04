---
title: Best Practices for Form Control Properties
TOCTitle: Form Control Properties
ms:assetid: 028bd626-4c01-4fa4-a8bf-c9c39699f2a2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa498808(v=AX.60)
ms:contentKeyID: 35240148
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Form Control Properties 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The basic rule for [form control properties](form-control-properties.md) is to use the system's Auto property values wherever you can. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon") This ensures a uniform application interface and reduces repetitive work. For example, the Auto settings for Dimension properties such as Top, Left, Width, and Height make allowances for preferences in font, font style, font size, and so on, and allow the dimensions to change dynamically when a different font is selected.

Specific rules for a few control properties are described in the following table.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Rules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>All control names should be unique on a form. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="even">
<td><p>AutoDeclaration</p></td>
<td><p>Use the AutoDeclaration feature on controls that you address for programming from X++ code in the form. <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /></p></td>
</tr>
<tr class="odd">
<td><p>AllowEdit</p></td>
<td><p>If AllowEdit is set to No, set it as close to the table field as possible. The AllowEdit property is on:</p>
<ul>
<li><p>Each field in a table</p></li>
<li><p>Each field in a form data source</p></li>
<li><p>The form data source (the table)</p></li>
<li><p>Each control on a form, on container controls like tabs, and on individual controls</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>AutoDataGroup</p></td>
<td><p>Set the AutoDataGroup to Yes on Data group on forms, if possible. <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /> This is recommended for performance reasons.</p>
<p>The following best practices apply to the AutoDataGroup property:</p>
<div class="caption">
</div>
<div class="tableSection">
<div class="mtps-table">
<div class="mtps-row">
Message Description BPError code and label
</div>
<div class="mtps-row">
Control %1 bound to table field group has name that does not match default name of %2, consequently the control requires storage and cannot be optimized Checks for when a Group or Grid control has the <strong>DataGroup</strong> property set but the child control cannot automatically be created when the form is loaded. This is because the name bound to the table field group does not match the default name. The control must be saved as metadata. This requires storage and the control cannot be optimized. BPErrorFormGroupCannotBeOptimized @SYS68376
</div>
<div class="mtps-row">
The form group and table group have different fields at position %1: '%2' != '%3', consequently the control requires storage and cannot be optimized Checks that the Group or Grid control has the <strong>DataGroup</strong> property set but the child control cannot automatically be created when the form is loaded. This is because the controls in the form group must match the position in the table field group. If the position does not match, the position must be saved as metadata. This requires storage and the position cannot be optimized. BPErrorFormGroupControlDifFieldsAtPos @SYS68382
</div>
</div>
</div></td>
</tr>
<tr class="odd">
<td><p><span id="rx25helptextmand"></span> HelpText</p></td>
<td><p>Mandatory property. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="even">
<td><p><span id="rx14formconlabelprop"></span> Label</p></td>
<td><p>Mandatory property, for controls where this property appears. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="odd">
<td><p>BackgroundColor and BackStyle</p></td>
<td><p>For Tab controls, do not change the default BackgroundColor or BackStyle properties. Changing the default values will result in form drawing issues.</p></td>
</tr>
<tr class="even">
<td><p>Left and Top</p></td>
<td><p>Do not use <strong>RightEdge</strong>, <strong>BottomEdge</strong>, or <strong>TopEdge</strong> as values for the Left and Top properties.</p></td>
</tr>
</tbody>
</table>


## Deactivating Fields/Controls

Fields that the user should not be able to change by using form controls should be set as shown in the following table ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon").

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Value</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AllowEdit</p></td>
<td><p>No</p></td>
<td><p>Set to No to stop the user from changing the value.</p></td>
</tr>
<tr class="even">
<td><p>Skip</p></td>
<td><p>Yes</p></td>
<td><p>Set to Yes if you don't want the user to enter the field while they tab through the form.</p></td>
</tr>
<tr class="odd">
<td><p>Enabled</p></td>
<td><p>Yes</p></td>
<td><p>Set to Yes by default. This allows the user to navigate to the field to see the Help text or to copy the field value.</p></td>
</tr>
</tbody>
</table>


## See also

[Best Practices for Form Data Source Properties](best-practices-for-form-data-source-properties.md)

[Best Practices for Form Design Properties](best-practices-for-form-design-properties.md)

[Forms Best Practices](forms-best-practices.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

