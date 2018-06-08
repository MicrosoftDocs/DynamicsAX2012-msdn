---
title: Segmented Entry
TOCTitle: Segmented Entry
ms:assetid: e6e9cebd-5444-4b00-93ca-d7dd6bd6c79d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh300646(v=AX.60)
ms:contentKeyID: 36595196
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Segmented Entry 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Microsoft Dynamics AX chart of accounts is a structured list of the general ledger accounts for a legal entity. The collection of accounts defines the financial framework of the legal entity. In addition, each main account can include one or more segments called financial dimensions. You use the financial dimensions to track and report activity in an account. For example, you might use financial dimensions that represent Department, Cost center, and Purpose for expense accounts. The following sections describe how you use a control, class, and data source to show an account that has one or more financial dimensions on a form.

## Segmented Entry Control

To show an account number that has more than one financial dimension on a form, you use a specialized control that is named the segmented entry control. The control has segments that show the financial dimensions that are associated with the account. In addition, you can use the control to select the value that appears in each segment.

You add a segmented entry control to a form when you want that form to show an account number and related dimensions from the chart of accounts. In addition, you use the segmented entry control to associate an account and related financial dimensions with the record that appears in the form. To update the values in the control, you can use a lookup or a list of recently used values to select a value for each segment. Finally, you can have the control validate the updated segments to ensure the account and financial dimensions are a valid combination. For information about how to add a segmented entry control to a form, see [How to: Add a Segmented Entry Control to a Form](how-to-add-a-segmented-entry-control-to-a-form.md).

When you add a segmented entry control to a form, you must associate the control with an Int64 field from the form data source. In addition, the field and data source must be configured to support multi-segment fields. You will find more information about the data source requirements later in this topic. When you add a segmented entry control to a form, you must populate the following control properties.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DataSource</strong></p></td>
<td><p>Specify the table in the form data source that contains the field you want to appear on the form.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferenceField</strong></p></td>
<td><p>Specify the Int64 field from the table that represents the account numbers you want to appear on the form.</p></td>
</tr>
</tbody>
</table>


After you add the control to the form, you must provide the control with the ability to retrieve data, select a value for a segment, and validate the selected values. Typically, you use a controller class to override several segmented entry control methods. You will find more information about controller classes in the following section. To enable the control to perform the expected actions, use the controller class to override the following methods.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Method</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>jumpRef</p></td>
<td><p>Provides access to a detail form for a specified segment. This method is called when you right-click a segment and then click <strong>View details</strong> from the menu.</p>
<p>You must override this method with a method from a controller class that opens the detail form for the specified record. For example, you use the jumpRef method of the LedgerDimensionAccountController class to specify the form that opens.</p></td>
</tr>
<tr class="even">
<td><p>loadAutoCompleteData</p></td>
<td><p>Gets the values that appear in the most recently used (MRU) list or the lookup form. This method is called when a segment receives focus.</p>
<p>You must override this method with a method from a controller class that retrieves the MRU or lookup information based on the segment that has focus. For example, you use the loadAutoCompleteData method of the LedgerDimensionAccountController class to get the MRU values for the segment.</p></td>
</tr>
<tr class="odd">
<td><p>loadSegments</p></td>
<td><p>Gets the display string that populates each segment with a value. This method is called when the segmented entry control is initialized.</p>
<p>You must override this method with a method from a controller class that retrieves the value that appears in each segment. For example, you use the loadSegments method of the LedgerDimensionAccountController class to load the correct number of segments and populate each segment with a value.</p></td>
</tr>
<tr class="even">
<td><p>segmentValueChanged</p></td>
<td><p>Performs actions every time that the contents of a segment change. This method is called when the value in a segment changes.</p>
<p>You must override this method with a method from a controller class that validates the value of the segment. For example, you use the segmentValueChanged method of the LedgerDimensionAccountController class to validate the segment value.</p></td>
</tr>
<tr class="odd">
<td><p>validate</p></td>
<td><p>Validates the contents of all the segments that appear in the control. This method is called after you change a segment and when the control exits.</p>
<p>You must override this method with a method from a controller class that validates the contents of the control. For example, you use the validate method of the LedgerDimensionAccountController class. Use the class method to identify whether the value in each segment is valid. If the value in a segment is not valid, you should change segment appearance, open a dialog that shows the error, or updated the information that appears in the status bar for the form.</p></td>
</tr>
</tbody>
</table>


## Controller Class

The segmented entry control only shows segment values. To handle the events that the control raises you have to bind a controller class to the control. You use the methods of the controller class to complete the following actions:

  - You retrieve the values that appear in the control.

  - You create a list of recently used values.

  - You validate a change to a segment value.

  - You save the changes that you made.

To use the controller class, you override the methods of the segmented entry control with methods from the class. The following table lists the most frequently used controller classes:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Controller class</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DimensionDynamicAccountController</p></td>
<td><p>Use this controller class when you expect that the segmented entry control will show different kinds of account numbers.</p></td>
</tr>
<tr class="even">
<td><p>LedgerDimensionAccountController</p></td>
<td><p>Use this controller class when you use the segmented entry control to show and update the main account and dimensions.</p></td>
</tr>
<tr class="odd">
<td><p>LedgerDimensionDefaultAccountController</p></td>
<td><p>Use this controller class when you use the segmented entry control to show and update just the main account.</p></td>
</tr>
</tbody>
</table>


You add a controller class to each form that has a segmented entry control. For example, you use the LedgerDimensionAccountController class for a segmented entry control that shows financial accounts. In addition, each segmented entry control must be bound to an instance of a controller class. You use the parmControl method to bind the class to the control. If you do not add the controller class to the control, the segmented entry control will not show any information.

## Form Data Source

To add a segmented entry control to a form, the form data source must include a table with a field that supports the use of multi-segment values. You bind that field to the segmented entry control that appears on the form. To determine whether the field supports multi-segment values, open the table, find the field, and verify that the field includes the following characteristics:

1.  The field must be of type Int64 and should be named **LedgerDimension**.

2.  The field should have the **ExtendedDataType** property set. Typically, you see **LedgerDimensionDefaultAccount**. However, you might see **DimensionDynamicAccount** used when the segmented entry control is expected to show different kinds of account numbers.
    

    > [!TIP]
    > <P>If you add a new Int64 field to a table and you set the <STRONG>ExtendedDataType</STRONG> property, you might be asked to confirm that you want to create a ForeignKey relation. Click <STRONG>Yes</STRONG> to create the table relation.</P>



When you use the segmented entry control, the field that you bind to the control stores a surrogate foreign key value from the DimensionAttributeValueCombination table. The surrogate key identifies each segment that is associated with the account number for that record. The surrogate key values are replaced by account and dimension values when the account number appears on the form. For information about surrogate foreign key replacement, see [Reference Data Sources for Forms](reference-data-sources-for-forms.md).

To use surrogate foreign key replacement, the field must be a member of a table relation that creates a join between that table and the DimensionAttributeValueCombination table. To support the use of a segmented entry control, the table relation must have the following characteristics:

  - The **Relations** node of the table includes a relation where the **Table** property is set to **DimensionAttributeValueCombination**.

  - The relation has a foreign key relationship that specifies the field you want to bind to the segmented entry control and the RecId field of the DimensionAttributeValueCombination table.

## See also

[How to: Add a Segmented Entry Control to a Form](how-to-add-a-segmented-entry-control-to-a-form.md)

[Form Control Properties](form-control-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

