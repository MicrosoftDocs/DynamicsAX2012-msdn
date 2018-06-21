---
title: Date Effective Data Sources for Forms
TOCTitle: Date Effective Data Sources for Forms
ms:assetid: 699cb717-7e88-4643-bd85-280a90609eff
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ129663(v=AX.60)
ms:contentKeyID: 46687527
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Date Effective Data Sources for Forms [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To add date effective fields to a form, you have to add a valid time state table to the **Data Sources** node of the form. A date effective field has date and time information that tracks changes to the value of the field. A valid time state table is a table where the **ValidTimeStateFieldType** property is set to a date type. For more information about valid time state tables, see [Valid Time State Tables and Date Effective Data](valid-time-state-tables-and-date-effective-data.md).

For example, the **Position** form uses date effective data that shows the worker currently assigned to a position. You can use the form to specify a different date and see the worker who was assigned to the position on that date.

## Adding a Valid Time State Table to a Form Data Source

To use date effective data in a form, you drop a valid time state table onto the **Data Sources** node of the form. A valid time state table can store date or date and time values to track changes in date effective field values. You specify **Date** when you want to track the date that a change occurred. You specify **UtcDateTime** when you want to include the time of day when the change occurred.

A form data source can include one or more valid time state tables. To use a date effective field together with the form, you populate the following properties of the form data source table.

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
<td><p><strong>ValidTimeStateAutoQuery</strong></p></td>
<td><p>Specify the type of query used to retrieve the value or values that appear on a form.</p>
<p>If the <strong>LinkType</strong> property is <strong>OuterJoin</strong>, <strong>InnerJoin</strong>, <strong>ExistJoin</strong>, or <strong>NotExistJoin</strong>, use the <strong>ValidTimeStateAutoQuery</strong> property of the root table of the form data source to specify the query behavior. In addition, the <strong>ValidTimeStateAutoQuery</strong> property of the joined table will be read-only.</p></td>
</tr>
<tr class="even">
<td><p><strong>ValidTimeStateUpdate</strong></p></td>
<td><p>Specify how a change to the field value is used to update one or more records in the database table. You use this property to specify how a change affects the valid-from and valid-to values of adjacent records.</p>
<p>You should set the property on the form data source table that references the valid time state table.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>If the <STRONG>ValidTimeStateFieldType</STRONG> property of a table is set to <STRONG>None</STRONG>, the <STRONG>ValidTimeStateAutoQuery</STRONG> and the <STRONG>ValidTimeStateUpdate</STRONG> properties of the form data source table will be read-only.</P>



To add date effective data to the form, you drag a field from the form data source table onto a group or control in the **Design** node of the form. You can add date effective data fields and the valid-from and valid-to fields to the form.

### ![JJ129663.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ129663.collapse_all(en-us,AX.60).gif")Setting the ValidTimeStateAutoQuery property

You use this property to specify the type of query that is used to retrieve values for the form. To specify the query behavior, set the property by using one of the following values.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Value</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>AsOfDate</strong></p></td>
<td><p>Retrieves the field value that existed on a specified date. The default value is the current date and time from the server.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>DateRange</strong></p></td>
<td><p>Retrieves all existing values. You use this property when you want the form to show past, current, and future record values.</p></td>
</tr>
</tbody>
</table>


### ![JJ129663.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ129663.collapse_all(en-us,AX.60).gif")Setting the ValidTimeStateUpdate property

You use this property to specify the type of updates that the form supports. To specify the update behavior, set the property to one of the following values.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Value</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CreateNewTimePeriod</strong></p></td>
<td><p>When you change a field value from a valid time state table, the current record in the table is closed and a new record is created. The current date, or current date and time, populate the <strong>ValidTo</strong> field of the closed record and the <strong>ValidFrom</strong> field of the new record.</p></td>
</tr>
<tr class="even">
<td><p><strong>Correction</strong></p></td>
<td><p>Enables you to make corrections to the field values and the <strong>ValidFrom</strong> and <strong>ValidTo</strong> values that appear on the form.</p>
<p>If you make changes that affect the date or time values associated with adjacent records, the values of the adjacent records are adjusted to reflect the change.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EffectiveBased</strong></p></td>
<td><p>Enables you to update current and future record values but prevents changes to past record values. You use this setting when the form requires the following behavior:</p>
<ul>
<li><p>You cannot change a past record. These records are read-only.</p></li>
<li><p>You can update the current record. The behavior is the same as you see with <strong>CreateNewTimePeriod</strong>.</p></li>
<li><p>You can update a future record. The behavior is the same as you see with <strong>Correction</strong>.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Using Date Effective Fields with Forms

You add a field from a valid time state table to a form when you want to show the value of that field. You can also add the **ValidFrom** and **ValidTo** fields to show the date and time range associated with the record. Typically you show the current value of the field. However, you can create forms that show a list of changes to a field and the date or date and time range associated with each value. In addition, you can use the form to enter future dates and times for **ValidFrom** and **ValidTo** fields. You use future dates and times when you can predict a future change to a record.

The use of date effective fields does include a minimum level of validation for the dates associated with changes to field values. For example, you cannot modify a date or date and time value that overlaps the date or date and time of an existing record. In addition, you can configure a valid time state table to specify whether the data can have gaps between the valid-to date of one record and the valid-from value of the next record. If the table does not allow for gaps, you get an error message when you enter a date or a date and time value that produces a gap.

When you add date effective fields to a form, you use one of the following patterns.

  - Show the current value.

  - Show a list of editable records.

  - Show a read-only list of records.

The following sections describe these patterns and the property values that you use to implement each pattern.

### ![JJ129663.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ129663.collapse_all(en-us,AX.60).gif")Show the Current Value

To show the current value of a date effective field on a form, you add a time state table to the **Data Sources** node of the form. You then set the **ValidTimeStateAutoQuery** property of the data source to **AsOfDate**. You also set the **ValidTimeStateUpdate** property to **CreateNewTimePeriod**. To add fields to the form, you drag the fields you want to appear onto a group or other control in the **Design** node of the form.

For example, the **Position** form includes a FastTab labeled **Worker assignment** that shows the worker currently assigned to that position. If you view the **HcmPosition** form in the AOT, you will find that **HcmPosition** in the **Data Sources** node of the form has the **ValidTimeStateAutoQuery** property set to **AsOfDate**.

![Form with ValidTimeStateAutoQuery set to AsOfDate](images/JJ129663.Client_ValidTimeStateAutoQuery(en-us,AX.60).png "Form with ValidTimeStateAutoQuery set to AsOfDate")

In addition, you will find a reference to the **HcmPositionWorkerAssignment** table in the **Data Sources** node of the form. Notice how the **ValidTimeStateAutoQuery** property is set to **AsOfDate** and the **ValidTimeStateUpdate** property is set to **CreateNewTimePeriod**.

![Form with ValidTimeStateAutoQuery set to AsOfDate](images/JJ129663.Client_ValidTimeStateAutoQuery(en-us,AX.60).png "Form with ValidTimeStateAutoQuery set to AsOfDate")

### ![JJ129663.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ129663.collapse_all(en-us,AX.60).gif")View and Update the List of Values

You can create a form that lists all past, current, and future values together with the valid-from and valid-to dates and times associated with each record. Typically, you use these types of forms to view and correct both field and date and time values.

To show past, current, and future values for a date effective field on a form, you add a reference to the valid time state table to the **Data Sources** node of the form. You then set the **ValidTimeStateAutoQuery** to **DateRange**. You also set the **ValidTimeStateUpdate** to **Correction**. To add fields to the form, you drag the fields you want to appear onto a grid or other control in the **Design** node of the form.

For example, the **Maintain position versions** form includes a tab labeled **Position worker assignments** that shows all the workers assigned to a position. In addition, the form shows the date the assignment started and when it ended. You can use this form to correct worker assignment information for a specified position. If you open the **HcmPositionDateManager** form in the AOT, you will find a reference to the **HcmPositionWorkerAssignment** table in the **Data Sources** node of the form. Notice how the **ValidTimeStateAutoQuery** property set to **DateRange** and the **ValidTimeStateUpdate** property set to **Correction**.

### ![JJ129663.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ129663.collapse_all(en-us,AX.60).gif")View a Read-Only List of Values

You can add a read-only collection of date effective fields to a grid in a form. The grid shows the current values and all past records. You add this information to show the history of changes to a date effective field. You must not change the values that appear in the grid.

To view or modify a record from the grid, you double-click the record and open the record in a dialog form. For information about how to open a form from a record in a grid, see [How to: Specify the Default Action for the List Page Grid](how-to-specify-the-default-action-for-the-list-page-grid.md). You then use the dialog form to view additional information about a past record, close the current record, or create a new record.

You can use a dialog form to work with date the effective fields in a grid. For information about dialog forms, see [Dialog Forms Overview](dialog-forms-overview.md). Use the following design patterns for the dialog form:

  - When you associate a dialog form with a grid that shows the history of a date effective record, do not use the dialog form to modify past records. You can use the dialog form to modify the current record.

  - To show past or current values for a date effective field on the dialog form, you first add the valid time state table to the **Data Sources** node of the form. You then set the **ValidTimeStateAutoQuery** property to **AsOfDate**.

  - To modify the current record in the dialog form, set the **ValidTimeStateUpdate** property to **EffectiveBased**.

  - To add fields to the dialog form, you drop the fields you want to appear onto a grid or other control in the **Design** node of the form.

For example, the **Purchase requisition control rule** form shows date effective fields for purchase requisitions. If you open the **PurchReqControlRule** form in the AOT, you will find a reference to the **PurchReqControlRule** table in the **Data Sources** node of the form. Notice how the **ValidTimeStateAutoQuery** property is set to **AsOfDate** and the **ValidTimeStateUpdate** property is set to **EffectiveBased**.

## Security

To grant access to the records in a valid time state table, you use the role-based security. You can specify whether a role can view, create, or update records in the table. Also, you specify whether the role can access records with current, past, or future date ranges. For more information about role-based security, see [Role-Based Security Concepts Overview](role-based-security-concepts-overview.md).

For example, the **HcmManager** role uses the **PastDataAccess**, **CurrentDataAccess**, and **FutureDataAccess** properties to define access to a valid time state table. As a result, a person assigned the **HcmManager** role can update date effective fields from a form where **ValidTimeStateUpdate** is set to **CreateNewTimePeriod**. In addition, a person assigned the **HcmManager** role can correct date ranges by using a form where **ValidTimeStateUpdate** is set to **Correction** or **EffectiveBased**.


> [!NOTE]
> <P>If you are assigned to multiple roles, you will use the maximum level of permission granted by all your roles.</P>



You can also add a permission to a role that gives the access level for a valid time state table. You use the **EffectiveAccess** property of the permission to specify the access level for the table. The effective access of the permission combined with access specified by the **PastDataAccess**, **CurrentDataAccess**, and **FutureDataAccess** properties determine the access available to the specified role. For more information about security role properties, see [Security Role Properties](security-role-properties.md).

For example, you have a role where you set the **PastDataAccess** property to **Read**, the **CurrentDataAccess** to **Update**, and **FutureDataAccess** to **Delete**. The role also includes a privilege that contains a permission to a valid time state table where the **EffectiveAccess** property is set to **Correct**. As a result, the role has read access to past records, update access to current records, and correct access to future records.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

