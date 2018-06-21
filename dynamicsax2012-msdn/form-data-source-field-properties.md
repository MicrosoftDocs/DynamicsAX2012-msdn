---
title: Form Data Source Field Properties
TOCTitle: Form Data Source Field Properties
ms:assetid: b9123462-8da0-4eb0-9b57-e1395be6b16e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa860145(v=AX.60)
ms:contentKeyID: 35132746
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Form Data Source Field Properties [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Form data source field properties are described in the following table.


> [!NOTE]
> <P>It is best practice to use the properties on data source fields rather than the properties on the controls. This ensures that all occurrences of the field on the form are displayed consistently and helps make upgrades easier.</P>



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
<td><p><strong>AllowAdd</strong></p></td>
<td><p>Specify whether you can use personalization to add a field to a form.</p>
<p>The default value is <strong>Restricted</strong>. You use Restricted when you want the field to be added as a read-only field on the form.</p>
<p>If <strong>AllowAdd</strong> is set to <strong>Yes</strong>, you can use personalization to add the field to the form.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
</div>
<div class="mtps-row">
The container control where the field is to be added must have the <strong>AllowUserSetup</strong> property set to <strong>Yes</strong>.
</div>
</div></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>AllowEdit</strong></p></td>
<td><p>Specify whether you can modify the value of the field.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>DataField</strong></p></td>
<td><p>Specify the name of the field from the table in the form data source.</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>Enabled</strong></p></td>
<td><p>Allows controls that display in the field to receive focus.</p>
<p>The default value is <strong>Yes</strong>. If set to <strong>No</strong>, controls bound to this field are disabled.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Tip" alt="Tip" class="note" /><strong>Tip</strong>
</div>
<div class="mtps-row">
If a field is used in several places on a form, set the <strong>Enabled</strong> property on the data source instead setting it on every control.
</div>
</div></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Mandatory</strong></p></td>
<td><p>Informs the user that this field must be completed. If set to <strong>Yes</strong>, the field has a red wavy line in the user interface.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Skip</strong></p></td>
<td><p>Determines whether controls bound to the field are skipped when the TAB key is used to navigate the form.</p>
<p>The default value is <strong>No</strong>.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Tip" alt="Tip" class="note" /><strong>Tip</strong>
</div>
<div class="mtps-row">
Even if the <strong>Skip</strong> property is set to Yes, users can still select the control by using the mouse pointer. You can also set the <strong>Skip</strong> property on a specific control.
</div>
</div></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Visible</strong></p></td>
<td><p>Determines whether controls bound to the field are visible.</p>
<p>The default value is <strong>Yes</strong>.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Tip" alt="Tip" class="note" /><strong>Tip</strong>
</div>
<div class="mtps-row">
You cannot use the <strong>Visible</strong> property on controls to enforce access restrictions—the user can change the visibility for the controls in the <strong>Form Setup</strong> dialog.
</div>
</div></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## See also

[Form Control Properties](form-control-properties.md)

[Form Data Source Properties](form-data-source-properties.md)

[Form Design Properties](form-design-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

