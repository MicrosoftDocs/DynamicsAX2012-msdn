---
title: Lookup Forms Overview
TOCTitle: Lookup Forms Overview
ms:assetid: 12e11928-fb8e-42ac-af91-5d9e6ca07c8d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa597861(v=AX.60)
ms:contentKeyID: 35240576
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Lookup Forms Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A lookup form is a small form that you use to select a value for a control. To open a lookup form, click the lookup button (![Lookup button](images/Aa597861.LOOKUP(en-us,AX.60).gif "Lookup button")) that appears with the control. To select a value, double-click the record that you want to appear in the control.

A lookup form lists values in a grid or a similar type of form that shows the records that you can use to populate the control. The lookup form often shows several fields that help you find and select the correct value.

For example, you have a field that requires a customer account number. To help you select the correct customer account number, the lookup form shows both the customer account number and the customer name.


> [!NOTE]
> <P>The data fields that appear in a lookup form are read-only. You cannot use the lookup form to update the records that appear in the list.</P>



## Controls that use Lookup Forms

The following list shows the types of controls where you can use a lookup form:

  - **DateEdit**

  - **GuidEdit**

  - **Int64Edit**

  - **IntEdit**

  - **RealEdit**

  - **ReferenceGroup**

  - **StringEdit**

  - **TimeEdit**

The presence of the **Lookup** button on the control in the parent form is controlled by the **LookupButton** property of the control. To add a lookup button to a control, set the **LookupButton** property to **Auto**. If you set the **LookupButton** property to **Auto**, the lookup button appears when the form data source includes a table relation to the table with the lookup data.

## Types of Lookup Forms

You can show the most useful information in the lookup form by selecting the form that appears when you click the lookup button. The following sections describe the types of lookups you can use with a Microsoft Dynamics AX form.

### ![Aa597861.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa597861.collapse_all(en-us,AX.60).gif")Standard Lookup Forms

A standard lookup form is a system generated form that appears when you click the lookup button. To add a standard lookup form, you bind a control to a field from the main table of the form data source that references the ID of a record in another table. The standard lookup form uses a grid to list the records you can use to populate the control. The fields that appear in the lookup form are specified by a field group or another set of fields from the related table.

You should use a standard lookup form whenever possible. Standard lookups provide a consistent experience across forms. In addition, they are easier to maintain because changes to the field group appear in any lookup form that references the table.

### ![Aa597861.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa597861.collapse_all(en-us,AX.60).gif")Extended Data Types with Lookup Forms

The extended data type (EDT) for a field can specify the lookup form that opens when you click the lookup button. An EDT enables you to use a form from the AOT as the lookup form. To use an EDT lookup, you populate the **ExtendedDataType** property of the table field by using the name of the EDT.

To specify the lookup form, populate the **FormHelp** property of the EDT with the name of the form you want to use as a lookup. In addition, you might have to add code to the form that updates the value of the control when you select a record.

You can also use an EDT to specify the lookup form for an unbound control. For example, you add a control to a dialog box. You use the **ExtendedDataType** property of the control to specify an EDT. If the **FormHelp** property of that EDT specifies a form, that form becomes the lookup form for the control.

### ![Aa597861.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa597861.collapse_all(en-us,AX.60).gif")Run-Time Lookup Forms

A run-time lookup form is a custom form you create with X++ code. The code creates and opens the lookup button at the time that you click the lookup button. A run-time lookup is always associated with a single form. In addition, changes to the lookup form require updates to the X++ code. As a result, you should only use a run-time lookup form when a standard lookup or an EDT-based lookup do not provide the information that you need.

To add a run-time lookup form, you override the lookup or lookupReference method of a field in the form data source or a control in the form design. You use X++ code to create a run-time lookup form that is customized for the specified field or control. The following table describes the overrides you use to add a run-time lookup form.

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
<td><p>Field</p></td>
<td><p>Override the lookup or lookupReference method of the field in the form data source. You should use the lookup method of the field so that any control bound to that field uses the same run-time lookup form.</p></td>
</tr>
<tr class="even">
<td><p>Control</p></td>
<td><p>Override the lookup or lookupReference method of the control. For example, you might want to use a lookup form with an unbound control in a dialog box.</p>
> [!caution]  
> <P>Do not override the lookup method of the <strong>ReferenceGroup</strong> control. This method is not used. Always override the lookupReference method of a <strong>ReferenceGroup</strong> control.</P>
</td>
</tr>
</tbody>
</table>


If you override the lookup method, the run-time lookup replaces the standard lookup or the EDT-based lookup that is associated with the control. A run-time lookup is associated with a single field or control on a form and is not accessed by other forms. To change the lookup form, you must find and update the code in the lookup method. For more information, see [How to: Add a Run-Time Lookup Form](how-to-add-a-run-time-lookup-form.md).

In addition, you can use the lookup method to customize the fields that appear in the lookup form. For more information, see [How to: Add a Lookup Form to a Control](how-to-add-a-lookup-form-to-a-control.md).

## Standard Lookup Forms and Foreign Keys

You create a standard lookup form when you bind a control to a field that references data in a related table. The standard lookup form builds upon the table relation that you create between two tables.

When you select a record in a lookup form, you create a foreign key relationship between a record in the table of the form data source and a record in a related table. The value that appears in the control represents the foreign key to the record in the related table.

A standard lookup form has a grid that lists values for one or more fields from the related table. The fields that appear in the lookup form depend on the type of foreign key relationship that you use to create the table relation between the two tables.

### ![Aa597861.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa597861.collapse_all(en-us,AX.60).gif")Surrogate Foreign Key

A surrogate foreign key is a single, computer-generated ID value that links to a record ID in a joined table. Typically, you do not want the ID to appear in the control or the lookup form.

To create a lookup form for a surrogate foreign key, you add a **ReferenceGroup** control to the form. You use the **ReferenceGroup** control to have the lookup form show the fields in the **AutoIdentification** field group from the reference data source.


> [!WARNING]
> <P>Do not include an Enum field in the <STRONG>AutoIdentification</STRONG> field group for a lookup form. To use an Enum field, add a <STRONG>Reference Data Source</STRONG> that explicitly adds the Enum field for the lookup form.</P>



When you select a record in the lookup form, the ID value of that record is stored in the database. For more information about reference data sources and surrogate foreign key replacement, see [Reference Data Sources for Forms](reference-data-sources-for-forms.md).

### ![Aa597861.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa597861.collapse_all(en-us,AX.60).gif")Natural Foreign Key

A natural foreign key is one or more field values that uniquely identify a record in a joined table or an extended data type. A natural foreign key uses a Normal table relation to establish a join between two tables. For more information about table relations, see [Defining Table Relations](defining-table-relations.md).

The lookup form for a natural foreign key includes the following field values:

  - The value in the TitleField1 property of the related table

  - The value in the TitleField2 property of the related table

  - The fields you use to define the table relation


> [!NOTE]
> <P>If any of the fields are identical, the system omits the additional duplicate fields.</P>



When you use the lookup to specify a record in another table, you must supply values for all the fields in the natural key. In addition, the field values must identify a valid record in the related table. To help you select a valid record, the value that you chose for the field that represents the first relation field restricts the values that you will see in the field that represents the second relation field. The same type of filter is applied to each subsequent member field of the natural key.

To simplify a form, you might use code that specifies values for key fields that do not appear on the form. You should add this code to the initValue method of the form or the modified method of a control. These methods enable the values that you set in code to be included in the validation that is performed for the natural key. Validation is completed before the record is written to the database.


> [!WARNING]
> <P>Take care when you set the value of a natural key field in code. Do not use values that could prevent the natural key from specifying a valid record. In addition, the hidden values could filter the values that you see in the lookup and prevent you from seeing the value that you want to use in the field.</P>



For more information about how to create a natural key based lookup form, see [How to: Add a Control with a Lookup Form](how-to-add-a-control-with-a-lookup-form.md).

To illustrate the use of a natural key, the following example shows the lookup form for the customer group field. The lookup form appears when you click the lookup button on the **Customer group** field on the **General** tab of the CustTable form.

![A lookup form on the CustTable form](images/Aa597861.FORMLOK2(en-us,AX.60).gif "A lookup form on the CustTable form")

The lookup information is based on the relation on the CustGroupId extended data type that is used for the CustGroup field, as shown in the following figure.

![Relationship used to create a lookup](images/Aa597861.FORMLOK3(en-us,AX.60).gif "Relationship used to create a lookup")

**TitleField1** and **TitleField2** from the CustGroup table (the related table) are **CustGroup** and **Name**, respectively, as shown in the following figure.

![TitleField properties used for lookup](images/Aa597861.FORMLOK4(en-us,AX.60).gif "TitleField properties used for lookup")

The following are the components of the lookup form:

  - The CustGroup field is specified in the **TitleField1** property of the CustGroup table. The label for this field is **Customer group**.

  - The Name field is specified in the **TitleField2** property on the CustGroup table. The label for this field is **Description**.

  - The CustGroup field is specified as the relation on the CustGroupId extended data type. Because the CustGroup field is also used for the **TitleField1** value, only two fields are shown in the lookup form.

## See also

[How to: Add a Control with a Lookup Form](how-to-add-a-control-with-a-lookup-form.md)

[How to: Add a Run-Time Lookup Form](how-to-add-a-run-time-lookup-form.md)

[How to: Add a Lookup Form to a Control](how-to-add-a-lookup-form-to-a-control.md)

[Data Sources for Forms](data-sources-for-forms.md)

[Reference Data Sources for Forms](reference-data-sources-for-forms.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

