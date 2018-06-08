---
title: 'How to: Add a Control with a Lookup Form'
TOCTitle: 'How to: Add a Control with a Lookup Form'
ms:assetid: 2e365e4b-842a-44eb-b0fa-6fa4c8c1e0fe
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa592952(v=AX.60)
ms:contentKeyID: 35241958
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a Control with a Lookup Form 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To add a lookup form, you first add a control that is bound to a field that contains the ID of a record in a related table. The lookup form opens when you click the lookup button (![Lookup button](images/Aa597861.LOOKUP(en-us,AX.60).gif "Lookup button")) and lists records from the related table.

The standard lookup form is added when you bind the control to a field that contains a foreign key from a table relation. The foreign key field contains the ID of the record from the related table. For information about how to create a table relation, see [How to: Add a Relation to a Table](how-to-add-a-relation-to-a-table.md).

The following steps add a control that is bound to a foreign key field in the form data source table. The control includes a lookup form that enables you to select a record from the related table.

### To Add a Control with a Lookup Form

1.  In the AOT, expand **Forms**, and then expand the form where you want to add a control with a lookup form.

2.  Expand **Data Sources**, expand the table that contains the field, right-click **Fields**, and then click **Open New Window**. The **Fields** list opens in a new window.

3.  In the AOT that shows the form, expand **Designs**, and then click **Design**.

4.  Drag the field you want to bind to the control from the **Fields** list to the **Design** node of the form. A control is added to the **Design** node.

5.  Right-click the control, and then click **Properties**. To determine the type of control that was added, view the **Type** property.
    
    If **Type** is **ReferenceGroup**, verify that the following properties have been populated.
    
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
    <td><p>Verify that the name uniquely identifies the control.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>DataSource</strong></p></td>
    <td><p>Verify that the property specifies the table in the form data source that contains the field you want bound to the control.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Label</strong></p></td>
    <td><p>If you want to specify the label for the control, select the label you want to appear on the form.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ReferenceField</strong></p></td>
    <td><p>Verify that the property specifies the field in the <strong>DataSource</strong> table that contains the surrogate foreign key value.</p></td>
    </tr>
    </tbody>
    </table>
    
    If **Type** is a **StringEdit** or another type of control, verify that the following properties have been populated.
    
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
    <td><p>Verify that the name uniquely identifies the control.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>DataField</strong></p></td>
    <td><p>Verify that the property specifies the field in the <strong>DataSource</strong> table that contains the foreign key value.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>DataSource</strong></p></td>
    <td><p>Verify that the property specifies the table in the form data source that contains the field you want bound to the control.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Label</strong></p></td>
    <td><p>If you want to specify the label for the control, select the label you want to appear on the form.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>LookupButton</strong></p></td>
    <td><p>Verify that the value of the property is set to <strong>Auto</strong>.</p></td>
    </tr>
    </tbody>
    </table>


6.  Right-click the form, and then click **Save**.

## See also

[Lookup Forms Overview](lookup-forms-overview.md)

[How to: Add a Run-Time Lookup Form](how-to-add-a-run-time-lookup-form.md)

[How to: Add a Lookup Form to a Control](how-to-add-a-lookup-form-to-a-control.md)

[Best Practices for Lookup Forms](best-practices-for-lookup-forms.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

