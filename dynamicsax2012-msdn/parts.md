---
title: Parts
TOCTitle: Parts
ms:assetid: 347f61a0-c3f7-4c9d-a2c1-3b9f6e286395
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg844683(v=AX.60)
ms:contentKeyID: 35242001
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Parts 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A Part is a specialized type of control you use to retrieve and show a collection of data. A part specifies how to retrieve the data that appears in the FactBox pane of a form, the preview pane of a list page, or the enhanced preview of a control. You use parts to provide information related to a record that appears in a form.

## Parts and Forms

When you add a part to a form, the collection of data that appears on the form is called a FactBox. A FactBox always represents a single part. To create or modify a FactBox, you create or modify the underlying part.

Unlike other form controls, a part is defined by using metadata. Each part you create extends a common metadata model for parts. The metadata model enables you to create parts that can appear in both the client and Enterprise Portal (EP). In addition, the metadata model enables you to create a part by populating a relatively small number of properties. For example, you do not have to specify values for properties like color, font size, borders, and margins.

To create or modify a part, you use the properties of that part to describe how to retrieve and show data. For example, you use a part property to specify the data source for the part. Typically, you use a query as the data source for a part. You also use properties to specify the data fields that show when the part appears as a FactBox on a form.


> [!NOTE]
> <P>To guarantee that a part can appear in both the client and EP, you cannot override methods for the part or the controls that appear in the part.</P>



To add a part to the FactBox pane or preview pane of a form, you add a part reference to the **Parts** node of the form. For information about how to add a part reference to a form, see [How to: Add a Part to the FactBox Pane](how-to-add-a-part-to-the-factbox-pane.md).

## Types of Parts

There are several types of FactBoxes that you can use in the FactBox pane of a form, the preview pane of a list page, or the enhanced preview for a control. For information about the types of FactBoxes, see [FactBox Panes](factbox-panes.md). To create each type of FactBox, you use one of the following part types.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Part type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Info Part</strong></p></td>
<td><p>A part that shows a collection of data fields from a specified query. An info part uses metadata to describe how the data appears. As a result, you can use an info part in both the client and EP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Form Part</strong></p></td>
<td><p>A part that represents a pointer to a form. You use a form part when you want a form to appear in the FactBox pane, enhanced preview, or preview pane.</p>
> [!caution]  
> <P>Enterprise Portal does not support the use of a form as a FactBox. To use a form part with Enterprise Portal, you use the <strong>ManagedContentItem</strong> property to specify a User Control. The specified User Control appears in Enterprise Portal as the FactBox.</P>
</td>
</tr>
<tr class="odd">
<td><p><strong>Cue Group</strong></p></td>
<td><p>A part that includes reference to one or more cues. You use a cue group to list a collection of query results. Typically, the list shows summary data that is related to a record or a task.</p></td>
</tr>
</tbody>
</table>


To create, modify, or remove a part, you use the **Parts** node of the AOT. If you remove a part, you must be certain that the part is not used in the FactBox pane of a form, the preview pane of a list page, the enhanced preview of a control, or in a User Control for Enterprise Portal.

## See also

[How to: Create a Form Part](how-to-create-a-form-part.md)

[Info Parts](info-parts.md)

[Cues and Cue Groups](cues-and-cue-groups.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

