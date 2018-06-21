---
title: Best Practices for Table Field Properties
TOCTitle: Table Field Properties
ms:assetid: 1c2161d4-0336-4b6d-8afc-81d740fcdb6b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa590501(v=AX.60)
ms:contentKeyID: 35241446
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Table Field Properties [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following table lists best practices for setting field properties.

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
<td><p>Type</p></td>
<td><p>Always ship a table field with the same base type as it has been shipped with before. The size of the field must be the same, or greater than it has been before.</p>
<p>Each field must be defined using a type, or you will get an error. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="even">
<td><p><span id="rx42nameprevious"></span> Name</p></td>
<td><p>A field should have the same name as the extended data type used, or it should have a logical name.</p>
<p>The field making up the key should be post-fixed &quot;Id,&quot; for example, &quot;ItemId.&quot;</p>
<p>You can remove the prefix if the name makes sense. For example CustTable.CustName could be CustTable.Name. But do not remove the prefix for ID fields (CustTable.CustId).</p>
<p>If you try to create a field with a name that has already been used in the previous version of Microsoft Dynamics AX, you will get an error. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p>
<p>A field cannot have the same name as an edit or display method on the same table. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="odd">
<td><p><span id="rx39tabfieldlabelprop"></span> Label</p></td>
<td><p>Mandatory property.<img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p>
<p>It is preferable to put labels on extended data types. If you choose to overwrite the value inherited from the extended data type, the value must be different from the one for the extended data type. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p>
<p>Do not set the Label property to the same property as the HelpText property. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p>
<p>The label must be unique for the table. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p>
<p>The label text cannot end with a period. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="even">
<td><p><span id="rx38helptext"></span> HelpText</p></td>
<td><p>Mandatory property. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p>
<p>It is preferable to put HelpText on the field’s extended data type. If you choose to overwrite the value, the value must be different than the one for the extended data type or enumeration. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p>
<p>HelpText must be a complete sentence and have ending punctuation ( &quot;.&quot;, &quot;?&quot; or &quot;!&quot;). <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p>
<p>Do not set the HelpText property to the same property as the Label property; <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /> the user should be provided with more detailed information than is available in the label. For more information, see <a href="helptext-guidelines.md">HelpText Guidelines</a>.</p></td>
</tr>
<tr class="odd">
<td><p>GroupPrompt</p></td>
<td><p>It is a best practice to leave this property blank. You can use this property to ensure that a field label does not repeat text that appears in a field group label. For example, if a field group on a form is labeled <strong>Customer</strong>, do not include this text in the <strong>GroupPrompt</strong> property for fields that are included in the group.</p>
<p>If you do use this property, you must use a label. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="even">
<td><p>SaveContents</p></td>
<td><p>Because virtual fields are rarely used, this property should usually be set to Yes.</p>
<p>Instead of virtual fields, you can use <a href="using-the-display-method-modifier.md">display and edit methods</a>.</p></td>
</tr>
<tr class="odd">
<td><p><span id="rx52mandpky"></span> Mandatory</p></td>
<td><p>If the field is the primary key (or part of the key), the property must be set to <strong>Yes</strong>. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p>
<p>You should set <strong>Mandatory = No</strong> for enum fields.</p>
<p>The following case is an exception:</p>
<p>If the enum first outcome (<strong>value = zero</strong>) is named <strong>None</strong> and has the label <strong>Not selected</strong>.<img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /></p>
<p>If you set it to <strong>Yes</strong> on an enum field, remember that <strong>zero</strong> is not a valid value.</p></td>
</tr>
<tr class="even">
<td><p>AllowEditOnCreate</p></td>
<td><p>Determines if you can edit the field on a new record. Use AllowEdit to indicate if you can edit the field on an existing record.</p>
<p>Usually set to Yes. When set to yes, the field will be editable when the record is first created.</p>
<p>Set to No when the field will be set programmatically for new records.</p>
<p>If AllowEdit is set to No, and AllowEditOnCreate is set to Yes, you can edit the field on a new record, but not on saved records.</p></td>
</tr>
<tr class="odd">
<td><p><span id="rx51alloweditpky"></span> AllowEdit</p></td>
<td><p>Determines if you can edit the field on a existing record. If the field is the primary key (or part of the key), the property must be set to No. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="even">
<td><p>Visible</p></td>
<td><p>Usually set to Yes, but it can be set to No for system-only information (information that will not be shown on the user interface), making the field accessible only from the code.</p></td>
</tr>
<tr class="odd">
<td><p><span id="rx49configkeyedt"></span> ConfigurationKey</p></td>
<td><p>This property must have a value to disable the field. It is better to put a Configuration key on the fields extended data type or enumeration.</p>
<p>If you decide to overwrite the value, the value that you give here must differ from the one for the extended data type or enum. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p>
<p>Disabling a table’s configuration key will also disable the fields in the table.</p></td>
</tr>
<tr class="even">
<td><p>AliasFor</p></td>
<td><p>If the user might think of other fields as keys for the table, in addition to the one that you have designated as the key, set them as alias fields. For example, on the item table, the bar code is an alias for the item ID.</p></td>
</tr>
<tr class="odd">
<td><p><span id="rx61analyvisib"></span> AnalysisDefaultTotal</p></td>
<td><p>Mandatory property if the AnalysisDefaultTotal property has been set for the table, unless the field property Visible has been set to No. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p>
<p>Set to <strong>DefaultField</strong> for fields that provide the most important information about a table.</p>
<p>Set to High for fields that are often used for reporting.</p>
<p>Set to Low for fields that are unlikely to be used for reporting.</p>
<p>Set to None for fields that should not be shown for end-user reporting.</p>
<p>Try to limit the number of fields that are set to <strong>DefaultField</strong> or High to no more than 15.</p>
<p><span id="yb26deffieldperspec"></span>If you have set AnalysisVisibility to DefaultField or High, the field must be included in at least one perspective. <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /></p></td>
</tr>
<tr class="even">
<td><p>ExtendedDataType</p></td>
<td><p>Mandatory property. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p>
<p>All fields must be defined by using an extended data type or an enum.</p>
<p>Fields that contain the same information must share the same extended data type or enumeration.</p></td>
</tr>
<tr class="odd">
<td><p><span id="rx00otherprops"></span> Other properties</p></td>
<td><p>Other properties for fields depend on the data type.</p>
<p>For integers and reals, it is a best practice to set FieldUpdate to Absolute.</p>
<p>For strings, StringSize and Adjustment should be set on the extended data type.</p>
<p>For reals, the CurrencyCode property must be set if the following two conditions exist:</p>
<ul>
<li><p>The data type extends the money system type</p></li>
<li><p>The AnalysisVisibility property has been set <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /> (for other reals, the property is unavailable)</p></li>
</ul>
<p>If the data type is derived from AmountMSTSecondary, you must set the CurrencyCode property to SecondaryCurrency. Otherwise, set it to CurrencyCodeField. If CurrencyCode is set to CurrencyCodeField, you must also set the CurrencyCodeTable property to one of the following:</p>
<ul>
<li><p>The table containing that field</p></li>
<li><p>A table for which a relationship exists from the table containing this field, and in which a unique index exists for the fields on the target end of the relationship</p></li>
</ul>
<p>If CurrencyCode is set to CurrencyCodeField, you must also set the CurrencyCodeField property to a field by using an extended data type derived from CurrencyCode, in the CurrencyCodeTable.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
</div>
<div class="mtps-row">
Do not use master currency amounts to set the CurrencyCode properties, because master currency amounts are always in the master currency for the associated company.
</div>
</div>
<p><span id="yb13cdatemoneymst"></span>For reals, the CurrencyDate property must be set if the data type extends the money or moneyMST system types. For other reals, the property is not available. <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /> This property must be set to CurrentRate or CurrencyDateField if the AnalysisVisibility property for the field is set to DefaultField, High, or Low. If the CurrencyDate property is set to CurrencyDateField:</p>
<ul>
<li><p><span id="rx99cdtnorelnouidx"></span>The CurrencyDateTable property must be set to one of the following:</p>
<ul>
<li><p>The table that contains that field</p></li>
<li><p>A related table in which a unique index exists for the fields on the target end of the relationship<img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></li>
</ul></li>
<li><p><span id="rx98curdatfedtdt"></span>The CurrencyDateField property must be set to a field by using an extended data type derived from Date. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></li>
</ul></td>
</tr>
</tbody>
</table>

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

