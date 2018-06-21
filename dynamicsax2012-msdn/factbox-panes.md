---
title: FactBox Panes
TOCTitle: FactBox Panes
ms:assetid: e421e81b-faf7-41f4-97fb-cebbdddbbef3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg847986(v=AX.60)
ms:contentKeyID: 35253187
ms.date: 05/18/2015
mtps_version: v=AX.60
f1_keywords:
- FactBox panes
- parts
---

# FactBox Panes [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The FactBox pane is the area of a form where a part that you add to a form appears as FactBox. A part is a specialized type of control that can retrieve and show additional information. When you view the form, the part appears as a collection of read-only data called a FactBox. For information about parts, see [Parts](parts.md).

## Forms with a FactBox Pane

To have a FactBox appear in a form, the form must include a FactBox pane. The following types of forms include a FactBox pane:

  - List pages

  - Details forms

The FactBox pane is optional and if the form does not have any parts, the FactBox pane does not appear. A FactBox pane can show more than one FactBox.

The parts you add to the FactBox pane create FactBoxes that show additional information about the record that appears in the form. The FactBoxes enable you to view related information without having to find and open a separate form. In addition, you can configure the part so that the contents of the FactBox update when you move to a new record.


> [!NOTE]
> <P>You can also use a part to add a preview pane to a list page. A list page is the only type of form that has a preview pane. The preview pane provides additional details about the highlighted record in the list. For more information about the preview pane, see <A href="list-page-overview.md">List Page Overview</A>.</P>



## Types of FactBoxes

FactBoxes can be grouped into types based upon how they appear in the FactBox pane. The type of FactBox helps you to choose the type of part you use to create the FactBox. For more information about types of FactBoxes, see [List Page User Experience Guidelines](list-page-user-experience-guidelines.md) or [Details Form User Experience Guidelines](details-form-user-experience-guidelines.md). The following table lists the basic design patterns for the FactBoxes that appear in the FactBox pane of many forms.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>FactBox type</p></th>
<th><p>Part type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Fields and values</p></td>
<td><p>Info part or form part</p></td>
<td><p>A FactBox that shows a list of field names and values. The value can include a link that opens the record in a form.</p>
<p>The FactBox often includes a <strong>More</strong> link that opens a related form.</p></td>
</tr>
<tr class="even">
<td><p>List</p></td>
<td><p>Info part or form part</p></td>
<td><p>A FactBox that shows a small grid with fewer than 10 rows and 4 columns. The grid shows information that is related to the record on the page or to the whole page. The grid can include links that you click to open a record in a form.</p>
<p>The FactBox often includes a <strong>More</strong> link that opens a related form.</p></td>
</tr>
<tr class="odd">
<td><p>Related documents</p></td>
<td><p>Cue group</p></td>
<td><p>A FactBox that shows a list of document types and the number of each type of document. The list can include links that you click to view the list of documents in a form.</p>
<p>The FactBox often includes a <strong>More</strong> link that opens a related form.</p></td>
</tr>
</tbody>
</table>


## Part References

To associate a part with a form, you use a part reference. A part reference enables you to configure how the part appears in the FactBox pane. In addition, you can use the part reference to define a join relationship between the form data source and the data source of the part. The join enables the part to retrieve related data every time that you view a new record in the form.

To create a part reference, you must first create a menu item for the part. To create the menu item, use the AOT to drag the part from the **Parts** node to the **Display** node under **Menu Items**. You can then drag the menu item to the **Parts** node of the form. The part reference is added to the **Parts** node of the form. Many part reference properties are populated with default values when you drag the part onto the **Parts** node of the form. For more information, see [How to: Add a Part to the FactBox Pane](how-to-add-a-part-to-the-factbox-pane.md).

You use the **PartLocation** property of the part reference to indicate where the part will be displayed. The default value of **Auto** makes the part appear in the FactBox pane. When creating the preview pane for a list page, you will set the **PartLocation** property to **PreviewPane**. For more information about the preview pane, see [How to: Add a Preview Pane to a List Page](how-to-add-a-preview-pane-to-a-list-page.md). The **PreviewPane** setting does not apply for other form types.

To complete a part reference, you use the **DataSourceRelation** property to specify the table relation between the part data source and the form data source. The **DataSourceRelation** lists the table relations that exist between the **DataSource** specified in the part reference and the top-level data source of the part. If the data source specified by the **DataSource** property of the part reference is in the same inheritance hierarchy as the top-level data source of the query used by the part, select **SelfLink** from the list in the **DataSourceRelation** property.


> [!TIP]
> <P>The parts on a form retrieve data after a brief delay. The delay prevents queries from being generated as you scroll through the list. The delay is like setting the <STRONG>LinkType</STRONG> property of a form data source to <STRONG>Delayed</STRONG>. In addition, only parts for expanded FactBoxes generate a data query. The part for a collapsed or hidden FactBox does not query the server until that FactBox is opened.</P>



## See also

[Info Parts](info-parts.md)

[Cues and Cue Groups](cues-and-cue-groups.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

