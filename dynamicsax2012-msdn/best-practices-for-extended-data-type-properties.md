---
title: Best Practices for Extended Data Type Properties
TOCTitle: Extended Data Type Properties
ms:assetid: 28504b1b-40fe-4772-8227-30c893b680aa
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa621435(v=AX.60)
ms:contentKeyID: 35241721
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Extended Data Type Properties 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, the Best Practices for extended data type properties are listed in the following table. For more information about properties, see [Extended Data Type Properties](https://msdn.microsoft.com/en-us/library/aa575242\(v=ax.60\)).

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
<td><p><span id="rx19name"></span> Name</p></td>
<td><p>The names of extended data types should reflect the real-world items they model.</p>
<p>If the extended data type belongs to an application module (such as customers or vendors), the name must be prefixed with the name of the module (Cust, Vend, and so on).</p>
<p>If an extended data type extends another extended data type, its name can be the name of the parent followed by its own specialization. If it is used in another module, however, it can be prefixed.</p>
<p>If it is a data type for identification purposes, such as for a key field in a table, the name must be postfixed with &quot;Id.&quot; For example, JournalId, InventJournalId, CustGroupId, and VendId.</p>
<p>Other common postfix terms can also be used, but avoid &quot;Code,&quot; &quot;Num,&quot; and &quot;Type.&quot;</p>
<p>If you attempt to create an extended data type with a name that has already been used, an error occurs. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="even">
<td><p><span id="rx43label"></span> Label</p></td>
<td><p>Do not set the Label property to the same value as the HelpText property. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p>
<p>The label should be defined at the most generic place, and not be duplicated down the hierarchy. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /> Use the LabelId extended data type.<img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="odd">
<td><p><span id="rx42helptext"></span> HelpText</p></td>
<td><p>Do not set the HelpText property to the same as the Label property. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /> Make it more descriptive and helpful.</p>
<p>The HelpText property should be defined at the most generic place, and not be duplicated down the hierarchy. For instance, if an extended data type inherits from an enumeration, the HelpText property should be reused, not duplicated. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /> Use the LabelId extended data type. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="even">
<td><p>FormHelp</p></td>
<td><p>Set FormHelp only when the standard lookup system facilities are not useful.</p></td>
</tr>
<tr class="odd">
<td><p>AnalysisDefaultSort</p></td>
<td><p>Set to Descending if the values in this field are more commonly sorted in descending order, for example, the date on which an e-mail was received.</p></td>
</tr>
<tr class="even">
<td><p>AnalysisGrouping</p></td>
<td><p>Set to Discouraged if the values in the fields with this type are likely to be unique, for example, phone numbers.</p></td>
</tr>
<tr class="odd">
<td><p>DisplayLength</p></td>
<td><p>Set to Auto.</p></td>
</tr>
<tr class="even">
<td><p>Extends</p></td>
<td><p>If a part of a hierarchy, it must inherit an &quot;is-a&quot; type.</p></td>
</tr>
<tr class="odd">
<td><p>DisplayLength</p></td>
<td><p>Set to Auto.</p></td>
</tr>
<tr class="even">
<td><p><span id="rx67enumtyp"></span> EnumType</p></td>
<td><p>If an extended data type is of type enum, it is mandatory to set the EnumType property. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="odd">
<td><p>Style</p></td>
<td><p>Set to Auto. <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /></p></td>
</tr>
</tbody>
</table>


## See also

[Best Practices for Extended Data Types](best-practices-for-extended-data-types.md)

[Extended Data Types (EDTs)](extended-data-types-edts.md)

[How to: Create an Extended Data Type](how-to-create-an-extended-data-type.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

