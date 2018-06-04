---
title: Cues and Cue Groups
TOCTitle: Cues and Cue Groups
ms:assetid: 0d29c49f-1b64-443e-a44e-dbffed62d5d1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg843613(v=AX.60)
ms:contentKeyID: 35240428
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Cues and Cue Groups 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following sections describe cues and cue groups. You use cues and cue groups to show related information on forms and role center pages.

## Cues

A cue is a type of part that represents a query. A cue shows the number of the records that the query retrieves. You use cues to provide the information that appears in a cue group in the FactBox pane of a form. Cues are also used on a role center pages for Enterprise Portal.

You add a new cue to **Cues** in the **Parts** node of the AOT. For information about how to create cues, see [How to: Create a Cue](how-to-create-a-cue.md). To show a cue in the FactBox pane of a form, you add the cue to a cue group part. For information about how to add a cue to a cue group part, see [How to: Create a Cue Group](how-to-create-a-cue-group.md).


> [!IMPORTANT]
> <P>You can also use a list page in the Microsoft Dynamics AX client to create and save cues. However, these cues do not appear in the AOT and cannot be added to a cue group.</P>



### ![Gg843613.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843613.collapse_all(en-us,AX.60).gif")Cue Data Source

To get the count that appears in the cue group or role center, a cue uses a query as a data source. You use a menu item to specify the query for the cue. The cue uses the query to get the count that appears in the cue group in the FactBox pane of a form. You use the **MenuItemName** property of the cue to specify the menu item that points to the query you want to use.


> [!NOTE]
> <P>While most cues use a query, you can also use the <STRONG>Table</STRONG>, <STRONG>DataField</STRONG>, and <STRONG>ShowSum</STRONG> properties of the cue to get the data value for the cue.</P>



To update the cue result that appears in a cue group every time that you display a different record in the form, you have to have a dynamic link. A dynamic link creates a relationship between the data source of the form and the data source of the cue. You create a dynamic link when you add a cue group to the FactBox pane of a form.

A dynamic link requires that you have previously defined a table relation between the main table of the form data source and the table that is used in the query data source for the cue. If the table relation exists, you can use the dynamic link without having to do any additional configuration. For more information about dynamic links, see [How to: Link Two Forms by Using Dynamic Links](how-to-link-two-forms-by-using-dynamic-links.md).

A cue data source does not have to use a dynamic link. You can have a cue with a query that does not have a relation to the form data source. If a dynamic link between the form data source and the cue data source does not exist, the data in the cue result does not update when you display a different record in the form.

### ![Gg843613.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843613.collapse_all(en-us,AX.60).gif")Cue Actions

Each cue from a cue group in the FactBox pane or a role center page can act as a link to open a form related to the cue. To open the form, you double-click the cue. The form opens and lists the records retrieved by the cue query.

To specify the form that opens when you double-click a cue, you set the **ObjectType** property of the menu item to **Form**. You then set the **Object** property to the name of the form to be opened. You should select a form with a data source that matches the query that is used for the cue data source. For cues that appear in a role center page, the cue should set the **WebMenuItemName** property to indicate the web menu item that opens a list page to show the query result. If the **WebMenuItemName** property is not set, you cannot click the cue in EP to open a separate page.


> [!TIP]
> <P>To quickly create a cue, you can use a copy of the menu item for a secondary list page. These menu items include the same query and form properties you use to create a cue.</P>



### ![Gg843613.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843613.collapse_all(en-us,AX.60).gif")Cue Appearance

To configure how the cue appears in a cue group FactBox or a role center page, you use the following properties.

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
<td><p><strong>CueMax</strong></p></td>
<td><p>The maximum number of items that will be shown for the cue. The default value is <strong>50</strong>.</p>
<p>You use this property when the cue appears in a role center page.</p></td>
</tr>
<tr class="even">
<td><p><strong>Label</strong></p></td>
<td><p>Specifies the label for the cue. Typically, the cue label is not specified, so the cue uses the label from the menu item. When the cue appears in a FactBox, you double-click the label to open the cue in a form.</p>
<p>To specify the cue label, select the label you want to use to describe the cue. The label appears when you add the cue to a cue group.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PreviewPartReference</strong></p></td>
<td><p>Select an info part that appears when you place the pointer over the cue in a cue group. This resembles the enhanced preview you see with data fields on a form.</p>
<p>You should use an info part that lists only the first ten records from the cue.</p></td>
</tr>
<tr class="even">
<td><p><strong>ShowAlert</strong></p></td>
<td><p>Specifies whether a warning icon displays for the cue. The default value is <strong>No</strong>. The appearance of a warning icon also requires values in the <strong>ShowAlertValue</strong> and <strong>ShowAlertWhen</strong> properties.</p>
<p>You use this property when the cue appears in a role center page.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ShowAlertValue</strong></p></td>
<td><p>Indicates the quantity of items returned from the query that will cause a warning icon to be displayed for the cue. The value is used with the criteria in the <strong>ShowAlertWhen</strong> property</p>
<p>You use this property when the cue appears in a role center page.</p></td>
</tr>
<tr class="even">
<td><p><strong>ShowAlertWhen</strong></p></td>
<td><p>Specifies the criteria that determine when a warning icon is displayed for the cue. The criteria use the value in the <strong>ShowAlertValue</strong> property.</p>
<p>You use this property when the cue appears in a role center page.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ShowSum</strong></p></td>
<td><p>Specifies whether to show a sum for the cue. The default value is <strong>No</strong>. To calculate a sum, the field must be one of the following Extended Data Types:</p>
<ul>
<li><p><strong>AmountCur</strong></p></li>
<li><p><strong>AmountMST</strong></p></li>
</ul>
<p>In addition, the table in the data source must have a field of type <strong>CurrencyCode</strong>.</p></td>
</tr>
</tbody>
</table>


In Enterprise Portal, a cue value can be displayed pictorially as a stack of pages. A larger stack indicates that a larger value was returned for the cue. The size of the stack is computed based on the ratio of the value of the count returned for the cue and value for the **CueMax** property. The value you specify for **CueMax** indicates the value that will show the stack at full height. Any value returned for the cue that is less than **CueMax** will show the stack at a proportional height. For example, if **CueMax** is the default value of 50, and the query for the cue returned a value of 25, the stack would be shown at 50% of the maximum height.

### ![Gg843613.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843613.collapse_all(en-us,AX.60).gif")Cue Security

A cue does not include properties that you can use to implement security restrictions. However, you can use the security permissions of the menu item to provide restriction for the cue. For more information about the security permissions for a menu item, see [Walkthrough: Design Permissions for a Form that is Started from a Menu Item](walkthrough-design-permissions-for-a-form-that-is-started-from-a-menu-item.md).


> [!WARNING]
> <P>If you use the menu item to specify security permissions for a cue, those security permissions are not used when the cue appears on a role center page. The role center does not use the security permissions in the menu item so the security restrictions are not enforced.</P>



## Cue Groups

A cue group is a type of part that contains one or more cues. You can create a cue group that can appear in forms for both the client and EP. In addition, you can use cue groups to add information to a role center page.

Cue groups are located in the **Parts** node of the AOT. To create a cue group, you add a part to **Cue Groups**, populate the properties of the cue group, and then add cue references. For more information about how to create a cue group, see [How to: Create a Cue Group](how-to-create-a-cue-group.md).

### ![Gg843613.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843613.collapse_all(en-us,AX.60).gif")Cue Group Metadata

To appear in both the client and EP, the cue group part uses metadata. The client and EP can interpret the metadata and show the cue group in the FactBox pane of a form, or as a web part on a web page. You use the properties of the cue group to supply values for the metadata model. Typically, you use a cue group to show a list of query results from the cues in the group.

### ![Gg843613.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843613.collapse_all(en-us,AX.60).gif")Cue References

You use a cue reference to add a cue to the cue group. To show information in the FactBox pane of a form, the cue group must have one or more cue references. The cue retrieves the values that appear in the FactBox pane. To create a cue reference, you use the AOT to drag a cue to a cue group. A cue reference requires values for the following properties.

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
<td><p><strong>Name</strong></p></td>
<td><p>A name that identifies the cue reference.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cue</strong></p></td>
<td><p>Specifies the cue to be displayed in the cue group.</p></td>
</tr>
</tbody>
</table>


### ![Gg843613.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843613.collapse_all(en-us,AX.60).gif")Cue Group Appearance

To specify the text that appears in the title bar of the cue group, you use the **Label** property. A cue group should have a label that describes the information that appears in the cue group. A common label for cue groups is **Related Items**, but you can use a different label if appropriate.

## See also

[Parts](parts.md)

[FactBox Panes](factbox-panes.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

