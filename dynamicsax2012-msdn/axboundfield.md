---
title: AxBoundField
TOCTitle: AxBoundField
ms:assetid: ca5ec569-b5da-4953-9293-14b87d05e11d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc619841(v=AX.60)
ms:contentKeyID: 28119496
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
- xml
---

# AxBoundField [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An AxBoundField component displays a single value in a form or grid. The data for the field comes from the AxDataSource linked to the form or grid. You will use the **Bound Field Designer** to select and set the properties of the bound fields you want to use. This designer is accessed through the **Fields** property of the AxGroup component or the **Columns** property of the AxGridView component.

## Properties

You can edit the properties for an AxBoundField in the following places:

  - When choosing the fields to display for an AxGridView.

  - When choosing the fields to display for an AxHierarchicalGridView.

  - When choosing the fields to display for an AxHierarchicalGanttView.

  - When choosing the collection of fields for an AxGroup.

The AxBoundField component has the following properties:

### Accessibility

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
<td><p>AccessibleHeaderText</p></td>
<td><p>A string that specifies the abbreviated text read by screen reading software.</p></td>
</tr>
</tbody>
</table>


### Appearance

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
<td><p>FooterText</p></td>
<td><p>Specifies the string that is displayed in the footer item for the field.</p></td>
</tr>
<tr class="even">
<td><p>HeaderImageUrl</p></td>
<td><p>Specifies the fully qualified or relative URL to an image that is displayed in the header item for the field. The specified image will appear in place of the header text.</p></td>
</tr>
<tr class="odd">
<td><p>HeaderText</p></td>
<td><p>When the bound field is used in a grid, specifies the text displayed in the header item for the field. When the bound field is used in a form, specifies the text displayed for the field prompt. If no string is specified, the label for the field in the underlying table is displayed.</p></td>
</tr>
<tr class="even">
<td><p>MaxDateLabel</p></td>
<td><p>Specifies the text to use for the maximum DateTime value for a date-effective field.</p></td>
</tr>
</tbody>
</table>


### Behavior

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
<td><p>ApplyFormatInEditMode</p></td>
<td><p>Specifies whether the data should be shown with the DataFormatString formatting applied when in edit mode.</p></td>
</tr>
<tr class="even">
<td><p>AutoPostBack</p></td>
<td><p>Indicates whether the field is updated when a postback occurs.</p></td>
</tr>
<tr class="odd">
<td><p>ConvertEmptyStringToNull</p></td>
<td><p>When set to true, the field will return null if the value of the field is the empty string.</p></td>
</tr>
<tr class="even">
<td><p>HtmlEncode</p></td>
<td><p>Specifies whether the field is HTML encoded when it is displayed to the user.</p></td>
</tr>
<tr class="odd">
<td><p>HtmlEncodeFormatString</p></td>
<td><p>Specifies whether formatted text should be HTML encoded when it is displayed.</p></td>
</tr>
<tr class="even">
<td><p>InsertVisible</p></td>
<td><p>Specifies whether the field is shown when the form or grid is in insert mode.</p></td>
</tr>
<tr class="odd">
<td><p>LookupButtonDisplaySettings</p></td>
<td><p>Specifies when the lookup button for the field is displayed. The value can be one of the following:</p>
<p><strong>Auto</strong> - Shown when a lookup has been defined</p>
<p><strong>Always</strong> - Always shown</p>
<p><strong>Never</strong> - Never shown</p></td>
</tr>
<tr class="even">
<td><p>LookupCacheScope</p></td>
<td><p>Specifies how the content for the lookup is cached. The value can be one of the following:</p>
<p><strong>None</strong></p>
<p><strong>DataBindingContainer</strong> – Cached at the datasource level, so the lookup value will be the same within the page.</p>
<p><strong>Global</strong> – Cached at the company level, so the lookup value will be the same for any Enterprise Portal page.</p>
<p><strong>Custom</strong></p></td>
</tr>
<tr class="odd">
<td><p>Mandatory</p></td>
<td><p>Specifies whether a value is required for the field.</p></td>
</tr>
<tr class="even">
<td><p>NullDisplayText</p></td>
<td><p>Specifies the text to display for the field when the field value is null. The default value is the empty string.</p></td>
</tr>
<tr class="odd">
<td><p>ReadOnly</p></td>
<td><p>When set to true, the value of the bound field cannot be edited.</p></td>
</tr>
<tr class="even">
<td><p>ShowHeader</p></td>
<td><p>When used in a grid, specifies whether the header is shown for the field. When used in a form, specifies whether the prompt is shown for the field.</p></td>
</tr>
<tr class="odd">
<td><p>SortExpression</p></td>
<td><p>The sort expression that is used by the field to sort data.</p></td>
</tr>
<tr class="even">
<td><p>Visible</p></td>
<td><p>Specifies whether the field is shown.</p></td>
</tr>
</tbody>
</table>


### Data

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
<td><p>DataField</p></td>
<td><p>The field in the data source to which this field is bound.</p></td>
</tr>
<tr class="even">
<td><p>DataFormatString</p></td>
<td><p>The formatting that is applied to the bound value. For example, &quot;{0:d}&quot; or &quot;{0:c}&quot;.</p></td>
</tr>
</tbody>
</table>


### Layout

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
<td><p>FastTabSummary</p></td>
<td><p>Specifies whether to show the field value on the summary portion of the header for an AxSection. The value <strong>Auto</strong> indicates that the field will be shown in the summary if the field is part of the AutoSummary group for the table, or if the field is part of the summary group that is defined for the AxSection.</p></td>
</tr>
</tbody>
</table>


### Lookup

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
<td><p>LookupPageSize</p></td>
<td><p>Specifies the number of items to display in the lookup.</p></td>
</tr>
<tr class="even">
<td><p>LookupStyle</p></td>
<td><p>Specifies when the data for the lookup will be loaded. The value can be one of the following:</p>
<p><strong>OnDemand</strong> – Data for the lookup is loaded when the user displays the lookup</p>
<p><strong>PreLoad</strong> – Data for the lookup is loaded when the page is loaded</p></td>
</tr>
</tbody>
</table>


### Styles

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
<td><p>ControlStyle</p></td>
<td><p>The style applied to the control.</p></td>
</tr>
<tr class="even">
<td><p>FooterStyle</p></td>
<td><p>The style applied to the footer.</p></td>
</tr>
<tr class="odd">
<td><p>HeaderStyle</p></td>
<td><p>The style applied to the header.</p></td>
</tr>
<tr class="even">
<td><p>ItemStyle</p></td>
<td><p>The style applied to the item.</p></td>
</tr>
</tbody>
</table>


## Events

The AxBoundField component has the events listed in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Event</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DataChanged</p></td>
<td><p>Occurs when the data in the field has changed.</p></td>
</tr>
<tr class="even">
<td><p>FormattingValue</p></td>
<td><p>Occurs when the data in the field is formatted.</p></td>
</tr>
<tr class="odd">
<td><p>Lookup</p></td>
<td><p>Occurs when the lookup for the field is clicked.</p></td>
</tr>
</tbody>
</table>


## Accessing Bound Field Values

When an AxBoundField object is used in a component like an AxForm, you cannot access the value of the bound field through that component. Instead, you must access the bound field value through the current row of the AxDataSource component for the User Control. For examples of accessing bound field values from an AxDataSource component, see [Working with Data for Enterprise Portal](working-with-data-for-enterprise-portal.md).

## Accessing Bound Field Properties

To access the properties for an AxBoundField, you must examine the bound field collection for the component. The following function will retrieve a specific bound field from a collection of bound fields for a component. It is better to retrieve an AxBoundField object based on its name, instead of its index.

``` csharp
static AxBoundField GetField(DataControlFieldCollection fields, string name)
{
    foreach (DataControlField field in fields)
    {
        // Is this the field being searched for?
        AxBoundField boundField = field as AxBoundField;
        if (boundField != null && String.Compare(boundField.DataField, name, true) == 0)
        {
            return boundField;
        }

    }
    // Nothing found, so return null.
    return null;
}
```

The following example uses the method created in the previous example to set the ReadOnly property for the WorkOrderNum bound field in the RequestDetailsLeft AxGroup object for an AxForm.

``` csharp
AxBoundField WorkOrderNumField;
WorkOrderNumField = GetField(RequestDetailsLeft.Fields, "WorkOrderNum");
WorkOrderNumField.ReadOnly = true;
```

## Lookups for Bound Fields

When enough information is available to create one, a bound field will automatically have a lookup. For example, if the bound field is based on an extended data type, the EDT information will be used to define the content of the lookup.

You may want to use a custom lookup for the bound field, instead of the lookup that is created automatically. The content of a custom lookup for a bound field can be defined by a User Control that has been added to the AOT. You can add a LookupContentTemplate element to the markup for the AxBoundField component to specify the User Control that defines the content of the lookup. The following example shows the LookupContentTemplate element specifying that the WorkOrderList User Control will be used to define the lookup for the WorkOrderNum field.

``` xml
<dynamics:AxBoundField DataField="WorkOrderNum" DataSet="FCMWorkOrderAddEdit" DataSetView="FCMWorkOrders" SortExpression="WorkOrderNum">
    <LookupContentTemplate>
        <dynamics:AxContentPanel ID="AxContentPanel1" runat="server" ManagedContentItem="WorkOrderList" />
    </LookupContentTemplate>
</dynamics:AxBoundField>
```

For more information about how to create custom lookups based on User Controls, see [Lookups](lookups.md).

