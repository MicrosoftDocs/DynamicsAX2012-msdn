---
title: 'How to: Add Controls to the Filter Pane'
TOCTitle: 'How to: Add Controls to the Filter Pane'
ms:assetid: daf1d829-f2c3-49dd-b1f9-31e2e53f2657
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc577231(v=AX.60)
ms:contentKeyID: 35252072
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add Controls to the Filter Pane [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A list page includes a default filter pane that enables you to search the records in the data grid. By default, you can search based on one of the columns displayed in the data grid. To create a filter that is based on multiple values in the data source query, you have to add controls for those fields to the filter pane. For example, the following illustration shows two controls that were added to the filter pane of the Collections list page.

Filter pane from the Collections list page

  
![Filter pane with additional form controls](images/Cc577231.Client_FilterWithControls(en-us,AX.60).png "Filter pane with additional form controls")

The values in the controls are used to filter the records that appear in the list. To add controls to the filter pane, follow these steps.

### To add a control to the filter pane

1.  In the AOT, expand **Forms**, expand the list page form, expand **Designs**, and then expand **Design**. Click the **Filter** group control and set the **Visible** property to **Yes**.

2.  Right-click the **Filter** group control, click **New Control**, and then click the type of control you want to add. For example, click **ComboBox** to add a control that enables you to select a value from a list.

3.  If the filter pane contains other controls, use the ALT+UP ARROW or ALT+DOWN ARROW to change the position of the control that you added.

4.  Right-click the control, and then click **Properties**. If you want the control to include a list of values that you can click, add an extended data type (EDT) or enumeration to the control properties.
    
    To add an EDT or enumeration, use the **Properties** window to specify the value for one of the following properties.
    
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
    <td><p><strong>EnumType</strong></p></td>
    <td><p>Click the name of the enumeration.</p>
    <p>Use <strong>EnumType</strong> when you want to open a list of enumeration values from the control.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ExtendedDataType</strong></p></td>
    <td><p>Click the name of the EDT.</p>
    <p>Use <strong>ExtendedDataType</strong> when you want to open a list of EDT supplied values from the control.</p></td>
    </tr>
    </tbody>
    </table>
    

    > [!IMPORTANT]
    > <P>The use of an EDT or enumeration is optional and does not apply to all kinds of controls.</P>



5.  To filter the data source query, you connect the value of the control to the value in a data field of the list page data source. To associate the control with a data field, populate the following properties of the filter control that you added.
    
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
    <td><p><strong>FilterDataSource</strong></p></td>
    <td><p>Click the data source that includes the data field you want to associate with the filter.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>FilterField</strong></p></td>
    <td><p>Click the data field that includes the values that you want to use to filter the query.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>FilterExpression</strong></p></td>
    <td><p>Typically, you use the default value.</p>
    <p>However, you can enter an expression that includes additional filter values. You use the same expression syntax that you use with a query range expression. For information about query range expressions, see <a href="using-expressions-in-query-ranges.md">Using Expressions in Query Ranges</a>.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Label</strong></p></td>
    <td><p>Select a label that describes the values that are used to filter the list.</p></td>
    </tr>
    </tbody>
    </table>


6.  Right-click the list page form, and then click **Save**.

## See also

[Form Control Properties](form-control-properties.md)

[Query Elements in the AOT](query-elements-in-the-aot.md)

[How to: Create Queries by using the AOT](how-to-create-queries-by-using-the-aot.md)

[List Page Overview](list-page-overview.md)

[Overview of Form Control Types](overview-of-form-control-types.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

