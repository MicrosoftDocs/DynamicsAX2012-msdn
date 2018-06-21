---
title: 'How to: Create a View Based on a Query'
TOCTitle: 'How to: Create a View Based on a Query'
ms:assetid: 21d01b34-fd2a-43f4-aeb6-58a2130cddc8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa558501(v=AX.60)
ms:contentKeyID: 35241558
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a View Based on a Query [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A Microsoft Dynamics AX view is a virtual table whose contents are defined by a query. For more information about how a view retrieves data, see [View Basics](view-basics.md).

Views are created in the Application Object Tree (AOT). Before you create a view, identify a query that retrieves the data records and fields that you want the view to return. For more information about how to create a query, see [How to: Create Queries by using the AOT](how-to-create-queries-by-using-the-aot.md).

### To create a view

1.  Press CRTL-D to open the AOT, expand the **Data Dictionary** node, right-click **Views**, and then click **New View**. A view is added to the list of views in the AOT.

2.  Expand the new view, right-click the view, and then click **Properties**. The properties window opens and displays the view properties. Set the value of the following properties.
    
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
    <td><p>Specify a name that uniquely identifies the view.</p></td>
    </tr>
    </tbody>
    </table>


3.  Press CTRL-D to open a second AOT window, expand the **Queries** node, and then drag a query onto the **Metadata** node of the view. Notice how the **Query** property of the view is populated with the name of that query. The query provides the data source information for the view.

4.  Close the AOT window that displays the queries.

5.  Right-click **Fields**, and then click **New View Field**. Notice that a field is added to the **Fields** list in the AOT.

6.  Click the field you created to display the field properties in the properties window. Set values for the following field properties.
    
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
    <td><p><strong>DataField</strong></p></td>
    <td><p>Specify a field from the data source. You must set a <strong>DataSource</strong> value before you try to specify a field.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>DataSource</strong></p></td>
    <td><p>Specify the data source where the field originates</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name that uniquely identifies the field in the view.</p></td>
    </tr>
    </tbody>
    </table>


7.  Repeat the previous step for each field you want the view to return.

8.  Expand **Field Groups**, right-click **AutoReport**, and then click **New Field**.

9.  In the properties window for the new field, specify a field name in the **DataField** property. Add any other fields that you want to include when the view data is printed. For more information about how to use field groups, see [Defining Field Groups](defining-field-groups.md).

10. Click the view to display the view properties in the properties window. Set values for the following properties.
    
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
    <td><p>Specify a field to display in the window caption for the view.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>TitleField2</strong></p></td>
    <td><p>Specify a field to display in the window caption for the view.</p></td>
    </tr>
    </tbody>
    </table>


11. Right-click the view in the AOT, and then click **Save**.

12. Close the properties window.

The view is complete and ready to use. To see the data that the view returns, right-click the view in the AOT, and then click **Open**. The **Table browser** window opens and displays the view data. Use the **Table browser** to verify that the view returns the expected data records and fields.

Once you create the view, you can use it as the data source for a form that displays the view fields. For more information about how to create a form, see [Walkthrough: Creating a Form by Using the AOT](walkthrough-creating-a-form-by-using-the-aot.md).

## See also

[View Properties](https://msdn.microsoft.com/en-us/library/aa869223\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

