---
title: 'How to: Add a Control to a Form'
TOCTitle: 'How to: Add a Control to a Form'
ms:assetid: 988e5e3f-d137-4546-9118-89a15ee2fbf0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa844912(v=AX.60)
ms:contentKeyID: 35247968
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a Control to a Form 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To show data on a form, you add controls to the form. To add a control, you use one of the following techniques:

  - You drag a field or a field group from the data source of the form to the **Design** node of the form.

  - You right-click the **Design** node of the form and add a control from the list of available controls.

  - You copy an existing control from one form to another form or to another location in the same form.

The procedure you use to add form control depends on whether you want to add a bound control, an unbound control, or a calculated control. For more information about the different kinds of controls, see [Bound Controls, Unbound Controls, and Calculated Controls](bound-controls-unbound-controls-and-calculated-controls.md).


> [!NOTE]
> <P>When you add a control to a form, the size of the form adjusts automatically.</P>



The following sections show how to add a bound, unbound, or calculated control to a form.

## To Add a Bound Control

1.  Expand the **Data Sources** node of the form.

2.  Expand the **Fields** node for one of the data sources.

3.  Click a field in the field list. To move more than one field, click each field you want to appear on the form.

4.  Drag the selected field from the field list to the **Design** node of the form. A control is added to the form. The control is bound to the field from the **Data Sources** node. The type of control is determined by the data type of the field. In addition, properties of the control are set to default values that are based on the data type of the field.
    

    > [!NOTE]
    > <P>To use a field group from a table in the data source, drag the complete field group instead of individual fields from your data source.</P>



## To Add an Unbound Control

1.  Expand the **Designs** node of the form.

2.  Right-click the **Design** node, click **New Control**, and then click the type of control you want to add.

3.  View the property sheet for the control and set values for the properties of the control. As a minimum, set the Name and Label properties.
    

    > [!NOTE]
    > <P>You can change an unbound control to a bound control by setting the DataSource and DataField properties of the control. However, you should add a bound control to a form by dragging the field to the <STRONG>Design</STRONG> node whenever possible. The control receives default property values that are inherited from the field.</P>



## To Add a Calculated Control

1.  Create a method that calculates the value to be displayed in the control. You should add the method to the table instead of the form. If you add the method to the table, you can reuse the code in other forms.
    
    For example, you add the following subtotalSum method to a table named MyTable. The method calculates the sum of the SubTotal\_A and SubTotal\_B fields. Notice how the method includes the [display](using-the-display-method-modifier.md) modifier that enables you to show the result of the computation.
    ```X++  
        display int subtotalSum(MyTable t)
        {
            return t.SubTotal_A + t.Subtotal_B;
        }
    ```
2.  Right-click the **Design** node of the form, click **New Control**, and then click the type of control you want to add. For example, you might click IntEdit or RealEdit to add a control that can display a sum.

3.  View the property sheet for the control. Set the **DataSource** property to the name of the table. Set the **DataMethod** property to the name of the method that calculates the field value. For example, you set **DataMethod** to **subtotalSum** to have the control show the value the method returns.

## See also

[Overview of Form Control Types](overview-of-form-control-types.md)

[Form Control Properties](form-control-properties.md)

[Methods on Form Controls](methods-on-form-controls.md)

[How to: Add ActiveX Controls to Forms](how-to-add-activex-controls-to-forms.md)

[How to: Add a .NET Control to a Form](how-to-add-a-net-control-to-a-form.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

