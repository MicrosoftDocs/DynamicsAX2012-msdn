---
title: Best Practices for Form Design Properties
TOCTitle: Form Design Properties
ms:assetid: c7aa8971-6086-4a9e-927f-83247b17ab57
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa866960(v=AX.60)
ms:contentKeyID: 35251150
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Form Design Properties 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The primary rule for form design is that all properties should keep their Auto or Default setting. Many form design properties also exist on the individual controls, for example the Width and Height properties.

Also refer to the description of design properties in:

  - [Form Design Properties](form-design-properties.md) (a general description of the properties)

  - [Lookup Forms](best-practices-for-lookup-forms.md) (best practice for lookup forms)

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
<td><p>Left, Top, Width, Height</p></td>
<td><p>Leave these properties set to Auto. <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /></p></td>
</tr>
<tr class="even">
<td><p>Caption</p></td>
<td><p>Mandatory property <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" />, unless the Visible property is set to No, or the form is a lookup form.</p>
<p>Set this property to the same value as the label for the table underlying the primary data source on the form (the one set in TitleDatasource property). <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /></p>
<p>The label on the menu item that is used for activating the form, the caption of the form, and the table label must be in balance.</p></td>
</tr>
<tr class="odd">
<td><p><span id="rx33titleds"></span> TitleDatasource</p></td>
<td><p>Set this property to the primary data source in the form. <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /> It is not necessary to set this property for the following controls: SimpleList, SimpleList and Details, or a Table of Contents.</p>
<p>The form title consists of the value of the Caption property, and, if a TitleDatasource is specified: a dash and the result of the caption method on the table underlying the specified data source</p>
<p>Examples:</p>
<ul>
<li><p>Customers - Customer Account: 4010, The Lamp Shop</p></li>
<li><p>Customers - Customer Account: 5000, New Record</p></li>
</ul>
<p>When a user creates a new record, the title will be appended with the text 'New Record'.</p></td>
</tr>
<tr class="even">
<td><p><span id="yb55framestd"></span> Frame</p></td>
<td><p>Typically, the Frame type is <strong>Standard</strong>. <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /></p>
<p>The other Frame types do not have a caption and are typically used when a new form is opened from within a form (for example, when a form is opened when the user clicks a lookup button <img src="images/Aa597861.LOOKUP(en-us,AX.60).gif" title="Lookup button" alt="Lookup button" />). Set to Border for lookup forms.</p></td>
</tr>
<tr class="odd">
<td><p>WindowResize</p></td>
<td><p>Keep the default setting. <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /></p></td>
</tr>
<tr class="even">
<td><p>WindowType</p></td>
<td><p><span id="yb25formpropstdwt"></span>Set to Standard, <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /> except for lookup forms, where it should be set to Popup.</p></td>
</tr>
<tr class="odd">
<td><p>HideToolbar</p></td>
<td><p>Set this property to No for all data entry forms. <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /></p>
<p>Set this property to Yes for lookup forms. <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /></p></td>
</tr>
<tr class="even">
<td><p>Columns</p></td>
<td><p>Keep the default setting (1) for all data entry forms. <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /></p></td>
</tr>
<tr class="odd">
<td><p>SetCompany</p></td>
<td><p>If the SaveDataPerCompany property on a table is set to Yes, then the SetCompany property on a form design that uses the table as a data source must also be set to Yes.</p></td>
</tr>
</tbody>
</table>


## See also

[Forms Best Practices](forms-best-practices.md)

[Best Practices for Form Control Properties](best-practices-for-form-control-properties.md)

[Form Control Properties](form-control-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

