---
title: AxLookup
TOCTitle: AxLookup
ms:assetid: 1b79af5a-1496-474a-b5a2-f3c42d870602
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc567382(v=AX.60)
ms:contentKeyID: 28119405
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# AxLookup 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An AxLookup component displays a lookup in Enterprise Portal. It is used when creating lookups for non-bound fields. Bound fields (fields that are linked to an AxDataSource) can automatically display a lookup if one has been defined for the underlying field.

When you add an AxLookup component to the layout, use the context menu to specify the target control for the lookup. This is the field to which the selected value in the lookup will be returned.

## Properties

The AxLookup component has the following properties:

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
<td><p>AccessKey</p></td>
<td><p>The keyboard shortcut used by the control. Not used for Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>TabIndex</p></td>
<td><p>The tab order of the control.</p></td>
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
<td><p>BackColor</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>BorderColor</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>BorderStyle</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>BorderWidth</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>ButtonImageUrl</p></td>
<td><p>Specifies the image to be displayed for the lookup button. The value will have the form ~/_layouts/ep/images/&lt;image&gt;.</p></td>
</tr>
<tr class="even">
<td><p>CssClass</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>DisplayAnimationAfter</p></td>
<td><p>Specifies the amount of time that must elapse (in milliseconds) before the progress circle is displayed in the lookup when it is expanded. Setting this property to a large value will prevent the progress circle from being displayed, because the data for the lookup will have already been loaded.</p></td>
</tr>
<tr class="even">
<td><p>Font</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>ForeColor</p></td>
<td><p>This property is inherited from the base control. It is not specific to Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>HoverCssClass</p></td>
<td><p>Specifies the cascading style sheet class to use when the pointer is over the lookup control.</p></td>
</tr>
<tr class="odd">
<td><p>InitialLookupHeight</p></td>
<td><p>The height of the lookup when it is displayed.</p></td>
</tr>
<tr class="even">
<td><p>LookupWidth</p></td>
<td><p>The width of the lookup when it is displayed.</p></td>
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
<td><p>AllowMarking</p></td>
<td><p>Specifies whether multiple rows can be marked for the contents of the lookup.</p></td>
</tr>
<tr class="even">
<td><p>AllowPaging</p></td>
<td><p>Specifies whether paging functionality is enabled for the lookup.</p></td>
</tr>
<tr class="odd">
<td><p>AutoPostBack</p></td>
<td><p>When set to true, the lookup will post back when the OK button is clicked.</p></td>
</tr>
<tr class="even">
<td><p>ButtonOnClientClick</p></td>
<td><p>Specifies the client-side script that is run when the button is clicked.</p></td>
</tr>
<tr class="odd">
<td><p>Enabled</p></td>
<td><p>Specifies whether the lookup is enabled.</p></td>
</tr>
<tr class="even">
<td><p>EnableTheming</p></td>
<td><p>Indicates whether the control can be themed.</p></td>
</tr>
<tr class="odd">
<td><p>EnableViewState</p></td>
<td><p>Specifies whether the control automatically saves its state for use in round-trips.</p></td>
</tr>
<tr class="even">
<td><p>HideSelectField</p></td>
<td><p>When set to true, the field specified by the <strong>SelectField</strong> property will not be displayed in the lookup. The value for this field will still be returned by the lookup. This is useful when you do not want to show the value being returned by the lookup.</p></td>
</tr>
<tr class="odd">
<td><p>HideSpecificSelectFields</p></td>
<td><p>Not used for Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>LookupDataSetView</p></td>
<td><p>Specifies the view from the data set to use for the lookup content.</p></td>
</tr>
<tr class="odd">
<td><p>LookupType</p></td>
<td><p>Specifies the source of the data for the lookup. The possible values are:</p>
<p><strong>DataSetField</strong></p>
<p><strong>EDT</strong></p>
<p><strong>CustomDataSet</strong></p>
<p><strong>Custom</strong></p></td>
</tr>
<tr class="even">
<td><p>PageSize</p></td>
<td><p>The number of items in each page of the lookup contents.</p></td>
</tr>
<tr class="odd">
<td><p>PredefinedButtons</p></td>
<td><p>Specifies what buttons are displayed for the lookup. The possible values are:</p>
<p><strong>None</strong></p>
<p><strong>Cancel</strong></p>
<p><strong>Ok</strong></p>
<p><strong>OkCancel</strong></p></td>
</tr>
<tr class="even">
<td><p>RunLookupDataSetWhenOkClicked</p></td>
<td><p>When set to true, the lookup will post back when the OK button is clicked. You may need to set this property to true to have custom lookups work properly.</p></td>
</tr>
<tr class="odd">
<td><p>SelectField</p></td>
<td><p>The field returned from the lookup when OK is clicked.</p></td>
</tr>
<tr class="even">
<td><p>Separator</p></td>
<td><p>When multiple rows can be marked in the lookup, specifies the character that is placed between the field for each marked row that is returned from the lookup.</p></td>
</tr>
<tr class="odd">
<td><p>ShowFilter</p></td>
<td><p>Specifies whether the filter controls will be displayed in the lookup.</p></td>
</tr>
<tr class="even">
<td><p>SkinID</p></td>
<td><p>The SkinId of the control skin that provides the skin of the control.</p></td>
</tr>
<tr class="odd">
<td><p>Target</p></td>
<td><p>The control to which the value from the lookup will be returned.</p></td>
</tr>
<tr class="even">
<td><p>ToolTip</p></td>
<td><p>Not used for Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>Visible</p></td>
<td><p>Indicates whether the control is visible and rendered.</p></td>
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
<td><p>Expressions</p></td>
<td><p>The expressions that are bound to properties of the control.</p></td>
</tr>
<tr class="even">
<td><p>DataLookupField</p></td>
<td><p>The field from the data set view that will be used for the lookup. Applies when the <strong>LookupType</strong> is set to <strong>DataSetField</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>DataSet</p></td>
<td><p>The data set from which the data for the lookup will be retrieved. Applies when the <strong>LookupType</strong> is set to DataSetField.</p></td>
</tr>
<tr class="even">
<td><p>DataSetView</p></td>
<td><p>The view from the data set from which data for the lookup will be retrieved. Applies when the <strong>LookupType</strong> is set to DataSetField.</p></td>
</tr>
<tr class="odd">
<td><p>ExtendedDataType</p></td>
<td><p>The extended data type that will be used for the lookup. Applies when the <strong>LookupType</strong> is set to EDT.</p></td>
</tr>
<tr class="even">
<td><p>ExtendedDataTypeArrayIndex</p></td>
<td><p>The index of the array element to use from the extended data type. Applies when the <strong>LookupType</strong> is set to EDT.</p></td>
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
<td><p>Height</p></td>
<td><p>The height of the control.</p></td>
</tr>
<tr class="even">
<td><p>Width</p></td>
<td><p>The width of the control.</p></td>
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
<td><p>LookupStyle</p></td>
<td><p>Specifies when the items for the lookup will be loaded. Choosing OnDemand causes the lookup items to be loaded only when the user clicks on the lookup button. Choosing PreLoad causes the lookup items to be loaded at the time when the page loads.</p></td>
</tr>
</tbody>
</table>


### Misc

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
<td><p>ID</p></td>
<td><p>The programmatic name of the control.</p></td>
</tr>
<tr class="even">
<td><p>CacheScope</p></td>
<td><p>Specifies the level at which the lookup content is cached.</p></td>
</tr>
<tr class="odd">
<td><p>CausesValidation</p></td>
<td><p>Specifies whether the controls in the validation group specified by the <strong>ValidationGroup</strong> property will be validated when the lookup is clicked.</p></td>
</tr>
<tr class="even">
<td><p>Fields</p></td>
<td><p>Not used for Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>ValidationGroup</p></td>
<td><p>The name of the validation group for which the validation controls will be validated when the lookup is clicked. Each validation control has a <strong>ValidationGroup</strong> property that specifies which validation group it is part of.</p></td>
</tr>
</tbody>
</table>


## Events

The AxLookup component has the events listed in the following table.

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
<td><p>DataBinding</p></td>
<td><p>Occurs when the server control binds to a data source.</p></td>
</tr>
<tr class="even">
<td><p>Disposed</p></td>
<td><p>Occurs when a server control is released from memory, which is the last stage of the server control lifecycle when an ASP.NET page is requested.</p></td>
</tr>
<tr class="odd">
<td><p>Init</p></td>
<td><p>Occurs when the server control is initialized, which is the first step in its lifecycle.</p></td>
</tr>
<tr class="even">
<td><p>Load</p></td>
<td><p>Occurs when the server control is loaded into the System.Web.UI.Page object.</p></td>
</tr>
<tr class="odd">
<td><p>Lookup</p></td>
<td><p>Occurs when the lookup button is clicked.</p></td>
</tr>
<tr class="even">
<td><p>OkClicked</p></td>
<td><p>Occurs when the OK button for the lookup is clicked.</p></td>
</tr>
<tr class="odd">
<td><p>PreRender</p></td>
<td><p>Occurs after the System.Web.UI.Control object is loaded but prior to rendering.</p></td>
</tr>
<tr class="even">
<td><p>Unload</p></td>
<td><p>Occurs when the server control is unloaded from memory.</p></td>
</tr>
</tbody>
</table>


## See also

[Lookups](lookups.md)

