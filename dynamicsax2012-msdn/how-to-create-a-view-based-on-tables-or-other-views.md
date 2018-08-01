---
title: 'How to: Create a View Based on Tables or Other Views'
TOCTitle: 'How to: Create a View Based on Tables or Other Views'
ms:assetid: 0bdfe470-cf3b-47c0-8497-2550d3d1720e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh272116(v=AX.60)
ms:contentKeyID: 36536726
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a View Based on Tables or Other Views [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, a view is a virtual table whose contents are defined by one or more sources of data. The sources of data can include queries, tables or views. For more information about how a view retrieves data, see [View Basics](view-basics.md).

Views are created in the Application Object Tree (AOT). Before you create a view, identify the tables or views that can provide the data records and fields that you want the new view to return.

## Create a View From a Table

1.  Press Ctrl+D to open the AOT.

2.  Expand the **Data Dictionary** node.

3.  Right-click **Views**, and then click **New View**. A view is added to the list of views in the AOT.

4.  Expand the new view, right-click the view, and then click **Properties**. The properties window opens and displays the view properties. Set the property values as shown in the following table.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Label</strong></p></td>
    <td><p>Specify a label for the view.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name for the new view.</p></td>
    </tr>
    </tbody>
    </table>


5.  Press Ctrl+D to open a second AOT window.

6.  In the second AOT, expand the **Tables** node.

7.  Drag a table onto the **Metadata** node of the new view in the first AOT.
    
    If you click on the data source name, you can see how the **Table** property of the new view is populated with the name of the table. The table is the data source for the new view.

## Create a View From Another View

1.  Under the **Metadata** node, right-click the table node that you just added, and then click **Delete**.

2.  In the second AOT window, expand the **Views** node, and then drag a view onto the **Metadata** node of the new view.
    
    If you click on the data source name, you can see how the **Table** property of the view is populated with the name of the view you dragged in. The table that it draws from is shown as well, in parentheses. The table provides the data source information for the view, which in turn provides the data for your new view.

3.  Click the new view to display the view properties in the properties window. Set values for the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>TitleField1</strong></p></td>
    <td><p>Specify a field to display in the window caption for the new view.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>TitleField2</strong></p></td>
    <td><p>Specify a field to display in the window caption for the new view.</p></td>
    </tr>
    </tbody>
    </table>


4.  Right-click the new view in the AOT, and then click **Save**.

You can create another view, and repeat the previous steps to nest one view within another.

## Test the View

The view is complete and ready to use. To see the data that the view returns, right-click the view in the AOT, and then click **Open**. The **Table browser** window opens and displays the view data. Use the **Table browser** to verify that the view returns the expected data records and fields.

## See also

[How to: Create a View Based on a Query](how-to-create-a-view-based-on-a-query.md)

[How to: Create Queries by using the AOT](how-to-create-queries-by-using-the-aot.md)

[Defining Field Groups](defining-field-groups.md)

[View Overview](view-overview.md)

[View Properties](https://msdn.microsoft.com/en-us/library/aa869223\(v=ax.60\))

[Walkthrough: Creating a Form by Using the AOT](walkthrough-creating-a-form-by-using-the-aot.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

