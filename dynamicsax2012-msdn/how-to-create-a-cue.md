---
title: 'How to: Create a Cue'
TOCTitle: 'How to: Create a Cue'
ms:assetid: 95711170-92b1-46df-93a8-666850c5366d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg841851(v=AX.60)
ms:contentKeyID: 35247628
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Cue 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A cue is a type of part that represents a query. You use a cue to show a count of data records that the query retrieves. Cues appear in cue groups in the FactBox pane and on a role center page. Before you create a cue, you must complete the following tasks:

1.  To get the record count that appears in the cue group or role center, you should identify an existing query or create a new query that retrieves the specified records. For information about how to create a query, see [How to: Create Queries by using the AOT](how-to-create-queries-by-using-the-aot.md).

2.  If you want to click the cue and open a form to display the records accessed by the cue, you must identify a form that shows the type of data records the query retrieves. Typically, you select a form with a form data source that uses the query from the previous step. For information about how to create a form, see [Forms in Microsoft Dynamics AX](forms-in-microsoft-dynamics-ax.md).

The following steps show how to create a menu item for a cue.

### To Create the Menu Item

1.  In the AOT, expand **Menu Items**, right-click **Display**, and then click **New Menu Item**.

2.  Click the new menu item. In the property sheet, click **Name** and specify a name that uniquely identifies the menu item.

3.  Click **Label** and select the label for the menu item. The menu item label appears in the FactBox when the **Label** property of the cue is empty.

4.  Click **Query** and then click the name of the query that you want to use to retrieve the data records.

5.  Click **ObjectType** and select **Form**.

6.  Click **Object** and then click the name of the form that you use to show the records from the query. If you do not want to open a form from the cue, you can leave the property empty.

7.  If the cue appears in Enterprise Portal, click **WebMenuItemName** and select a **WebMenuItem**. Use a **WebMenuItem** that opens a list page that can display the set of records that the cue retrieved.

8.  Right-click the menu item and then click **Save**.

### To Create the Cue

1.  In the AOT, expand **Parts**, right-click **Cues**, and then click **New Cue**. A cue is added to the list of **Cues** in the AOT.

2.  Click the new cue. In the property sheet, click **Name** and specify a name that uniquely identifies the cue.

3.  Click **Label** and select the label you want to appear in a FactBox. This step is optional. If the label is not specified, the cue uses the label from the menu item.

4.  Click **MenuItemName** and select the menu item that you created for the cue. This menu item specifies the query you want to use, as well as the form (for the Microsoft Dynamics AX client) or list page (for EP) that will be opened when the cue is clicked.

5.  Right-click the cue and then click **Save**.

## See also

[Cues and Cue Groups](cues-and-cue-groups.md)

[How to: Create a Cue Group](how-to-create-a-cue-group.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

