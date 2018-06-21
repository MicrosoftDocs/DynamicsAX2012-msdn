---
title: Reference Data Sources for Forms
TOCTitle: Reference Data Sources for Forms
ms:assetid: 3e4ecfff-2e64-4f1d-a4ba-f3ad1e29f91f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg845085(v=AX.60)
ms:contentKeyID: 35242941
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Reference Data Sources for Forms [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A reference data source supplies data values that replace the foreign key value when that key refers to a surrogate primary key. You use a reference data source any time that you add a foreign key field that represents a surrogate key in another table to a form. In the AOT, you find reference data sources under the **Data Sources** node of a form.

## Replacing the Foreign Key Value

A surrogate key is a computer-generated identification (ID) value that means nothing to the user. Therefore, you would not want to display the ID in a form or control. You can replace the surrogate ID value with one or more meaningful data fields from the specified record in the referenced table. You replace the surrogate key when you want to create forms or controls that display data values that you recognize and understand.

To replace a surrogate foreign key, the form data source has to include a join to the table that contains the meaningful replacement fields. You use a field group from the referenced table to specify the data fields that replace the surrogate foreign key. To ensure the timely retrieval of field group data, the joined table must have an index that includes all the fields in the field group. For more information about how to create tables that support surrogate foreign key replacement, see [How to: Add a Relation to a Table](how-to-add-a-relation-to-a-table.md).

The default field group used to replace the surrogate foreign key is the **AutoIdentification** field group. The **AutoIdentification** field group includes the natural key fields from the referenced table. However, you can use a different field group to replace the surrogate foreign key. For more information about how to use **AutoIdentification** and other field groups, see [Defining Field Groups](defining-field-groups.md).


> [!NOTE]
> <P>Natural foreign keys use data fields that have values that uniquely identify the record in the referenced table. As a result, you do not have to replace the key value when it is displayed in a control. In addition, natural foreign keys do not always require a join to the referenced table.</P>



## Adding a Reference Data Source

You must create the reference data source before you can bind the surrogate foreign key to a control or lookup form. The following table describes the types of reference data sources you can use with a form.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Implicit</p></td>
<td><p>The reference data source is automatically created and configured when you drag a surrogate key field from the field list in the form data source to the <strong>Design</strong> node of the form. The reference data source retrieves the values that replace the surrogate key when you open the form.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
</div>
<div class="mtps-row">
If you create an implicit reference data source, the <strong>Reference Data Sources</strong> node under the <strong>Data Sources</strong> of the form does not add a node for the new reference data source. You cannot see an implicitly created reference data source in the AOT.
</div>
</div></td>
</tr>
<tr class="even">
<td><p>Explicit</p></td>
<td><p>You use the AOT to manually add a reference data source and populate the data source properties. Typically, you use explicit creation when you have to customize the following properties of the reference data source:</p>
<ul>
<li><p>You want to specify the <strong>JoinRelation</strong> to use with the reference data source.</p></li>
<li><p>You want to specify the <strong>AllowDeferredLoad</strong> behavior of the reference data source.</p></li>
<li><p>You want to specify the <strong>OnlyFetchActive</strong> active behavior of the reference data source.</p></li>
</ul></td>
</tr>
</tbody>
</table>


### ![Gg845085.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845085.collapse_all(en-us,AX.60).gif")Specifying the join relationship

The **JoinRelation** property of the reference data source specifies a relation object from a table in the form data source. The field group you use to replace the surrogate foreign key comes from the joined table specified by the relation.

### ![Gg845085.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845085.collapse_all(en-us,AX.60).gif")Deferred loading of surrogate key values

To replace a surrogate foreign key, the reference data source specifies a join to the table that contains the replacement data fields. If the form data source includes many reference data sources, the number of joins might affect how quickly the form opens and updates.

To specify the behavior of the join in a reference data source, you can use the **AllowDeferredLoad** property. The **AllowDeferredLoad** property specifies whether to defer the loading of surrogate foreign key replacement fields until the form needs the data. The following table describes the use of the **AllowDeferredLoad** property.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>AllowDeferredLoad</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Yes</p></td>
<td><p>The replacement values are retrieved when the control that displays the surrogate foreign key is visible or the data is accessed programmatically.</p>
<p>The <strong>AllowDeferredLoad</strong> property is set to <strong>Yes</strong> when you implicitly create a reference data source.</p></td>
</tr>
<tr class="even">
<td><p>No</p></td>
<td><p>The replacement values are immediately retrieved from the joined table.</p>
<p>The <strong>AllowDeferredLoad</strong> property is set to <strong>No</strong> when you explicitly create a reference data source.</p></td>
</tr>
</tbody>
</table>


To use deferred loading, you set the **AllowDeferredLoad** property to **Yes**. However, your choice is permanently overridden in the following situations:

  - You use the surrogate key field to sort or filter the records on the form.

  - You add the surrogate key to a grid control.

  - You add code that programmatically accesses the surrogate key field.

## Using a Reference Data Source with a Form

A reference data source enables you to add the replacement fields for a surrogate foreign key replacement to a form. The following sections describe the controls and forms that you use to display a surrogate foreign key replacement fields.

### ![Gg845085.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845085.collapse_all(en-us,AX.60).gif")Controls

To add a surrogate foreign key to a form you use one of the following controls. These controls use surrogate foreign key replacement to display the surrogate key replacement fields on the form.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Control name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ReferenceGroup</p></td>
<td><p>The control you use to add a surrogate foreign key to a form. The control contains other controls that display the individual replacement fields. The control includes a lookup you can use to select or update the foreign key value.</p></td>
</tr>
<tr class="even">
<td><p>SegmentedEntry</p></td>
<td><p>The control you use to view or enter account number and associated dimensions as segments in a single field on a form.</p></td>
</tr>
</tbody>
</table>


### ![Gg845085.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845085.collapse_all(en-us,AX.60).gif")Lookup forms

To set or update a surrogate foreign key, click the lookup button that appears next to the foreign key replacement fields in the form. A lookup form opens and lists the records that you can link to the current record. Typically, the lookup form lists the surrogate foreign key replacement fields. When you select a record in the lookup window, the ID of that record becomes a surrogate foreign key. For more information about lookup forms, see [Lookup Forms Overview](lookup-forms-overview.md) or [How to: Add a Control with a Lookup Form](how-to-add-a-control-with-a-lookup-form.md).


> [!NOTE]
> <P>The fields in the lookup form are read-only.</P>



The **ReferenceGroup** control opens a standard lookup form. However, you can change the lookup form that opens to use a custom lookup form.

## Using a Reference Data Source with a Dialog

You can use a dialog to look up data that is not included with the data source of the current form. To create the dialog, you use X++ or a **ReferenceGroup** control to show a list of values. You use the dialog to show the values associated with an extended data type (EDT). The EDT represents a surrogate key. To retrieve the selected record, you use X++ to get the ID value from the lookup form.

For example, you create a dialog form, add a **ReferenceGroup** control and then populate the **ExtendedDataType** property of the control. You populate the property by using the name of the EDT that represents the data that you want to appear in the dialog box.

## See also

[Form Data Sources](form-data-sources.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

