---
title: Enhanced Preview
TOCTitle: Enhanced Preview
ms:assetid: 8dacc902-4eea-47d5-a285-fb254ec54bd8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh129455(v=AX.60)
ms:contentKeyID: 35589806
ms.date: 05/18/2015
mtps_version: v=AX.60
f1_keywords:
- enhanced preview
---

# Enhanced Preview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Enhanced preview is a window that appears when you point to a control on a form that references data from another table. Enhanced preview is available for foreign key fields that include the **View Details** menu option. The default enhanced preview shows values from the **TitleField1** and **TitleField2** properties of the referenced table in the form data source. The following figure shows an enhanced preview for a field in a list.

![Another system-generated enhanced preview](images/Hh129455.EnhancedPreview03(en-us,AX.60).png "Another system-generated enhanced preview")

**Enhanced Preview**

## Custom Enhanced Previews

You can customize the enhanced preview to show additional information from the related table. Typically, you want enhanced preview to show important information about the related record so that you do not have to leave the current form. For example, the enhanced preview for the customer account field of the sales orders list page shows important information from the customer record.


> [!WARNING]
> <P>The related information in the enhanced preview should not be information that is required by the current form. For example, you should not use enhanced preview as an overflow container for fields that do not fit on the form. In addition, enhanced preview is not a substitute for application functionality and is not meant to display Help content. For more information about enhanced preview, see <A href="enhanced-preview-user-experience-guidelines.md">Enhanced Preview User Experience Guidelines</A>.</P>



To customize the values or the format that appears in the enhanced preview, you can use the title fields for the table, the AutoIdentification group for the table, or a part. A part is a specialized type of control that shows a collection of data. To customize enhanced preview, you use the same type of info part or form part that you use to add a FactBox to some forms. For information about parts, see [Parts](parts.md).

The following table shows the properties you use to specify the enhanced preview. In addition, the table lists the precedence used to find the enhanced preview. When you point to a control with enhanced preview, the system uses the value of the **PreviewPartRef** property of the control to identify the part. If the control property is empty, the system looks for values in the **PreviewPartRef** property of the table, and then the field group and titlefields of the table, For example, if the **PreviewPartRef** property of the control specifies an info part, that info part is used for the enhanced preview and the values of the table **PreviewPartRef**, **AutoIdentification**, and **TitleField** properties are ignored.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property name</p></th>
<th><p>Object type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>PreviewPartRef</strong></p></td>
<td><p>Control</p></td>
<td><p>Specify the name of the info part or form part you want to use in the enhanced preview.</p></td>
</tr>
<tr class="even">
<td><p><strong>PreviewPartRef</strong></p></td>
<td><p>Table</p></td>
<td><p>Specify the name of the info part or form part you want to use in the enhanced preview.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AutoIdentification</strong> field group and <strong>TitleField2</strong></p></td>
<td><p>Table</p></td>
<td><p>Specify that you want the fields in the field group and the titlefield property to appear in the enhanced preview.</p></td>
</tr>
<tr class="even">
<td><p><strong>TitleField1</strong> and <strong>TitleField2</strong></p></td>
<td><p>Table</p></td>
<td><p>Specify that you want the titlefield properties of the table to appear in the enhanced preview.</p></td>
</tr>
</tbody>
</table>


## Controls with Enhanced Previews

To use an info part or form part, you populate the **PreviewPartRef** property of the control or table with the name of an info part or form part. The following list shows the controls that include the **PreviewPartRef** property.

  - Checkbox

  - Combobox

  - DateEdit

  - IntEdit

  - Int64Edit

  - ListBox

  - RadioButtton

  - RealEdit

  - SegmentedEntry

  - StaticText

  - StringEdit

  - TimeEdit

  - UtcDateTimeEdit

  - Window

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

