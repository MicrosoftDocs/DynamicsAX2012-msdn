---
title: AxHyperLinkBoundField
TOCTitle: AxHyperLinkBoundField
ms:assetid: 8cf8147b-baba-4925-abf3-17bdaaad7c8f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc603636(v=AX.60)
ms:contentKeyID: 28119445
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# AxHyperLinkBoundField [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An AxHyperLinkBoundField component displays a single value in a form or grid. The data for the field comes from the AxDataSource linked to the form or grid. The field is also a hyperlink that when clicked will navigate to another page in Enterprise Portal.


> [!IMPORTANT]
> <P>The AxHyperLinkBoundField can be used to link to a record that is in the current company. It cannot be used to link to a record in another company.</P>



## Properties

The AxHyperLinkBoundField component has the same properties as the AxBoundField component. It also has the following additional properties:

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
<td><p>ImageUrl</p></td>
<td><p>Specifies the fully qualified or relative URL to an image that is displayed for the field.</p></td>
</tr>
<tr class="even">
<td><p>MenuItem</p></td>
<td><p>The Web Url menu item from the AOT that specifies what page is to be opened when the field is clicked.</p></td>
</tr>
<tr class="odd">
<td><p>RecordContextDataSource</p></td>
<td><p>Specifies the data source to use when passing the record context to the item being opened by the hyperlink. If no value is supplied, the default data source will be used.</p></td>
</tr>
<tr class="even">
<td><p>Target</p></td>
<td><p>Specifies the target window or frame in which to load the page specified by the <strong>MenuItem</strong> property. Choose one of the following values:</p>
<p><strong>_blank</strong> - Displays the content in a new browser window without frames.</p>
<p><strong>_parent</strong> - Displays the content in the immediate parent frameset.</p>
<p><strong>_search</strong> - This value is not used.</p>
<p><strong>_self</strong> -Displays the content in the frame that currently has focus.</p>
<p><strong>_top</strong> - Displays the content in the current browser window without frames.</p></td>
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
<td><p>DataMenuItemField</p></td>
<td><p>If a field in a data source contains the value that specifies the Web menu item to display when the field is clicked, set this property to the name of that field. This allows the hyperlink destination to be set based on the data being displayed.</p></td>
</tr>
</tbody>
</table>


## Events

The AxHyperLinkBoundField component has the events listed in the following table.

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

