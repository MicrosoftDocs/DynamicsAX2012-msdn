---
title: Using the edit Method Modifier
TOCTitle: Using the edit Method Modifier
ms:assetid: 438f8d41-4f65-4784-9e2c-6c5ec2b10b1d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa637541(v=AX.60)
ms:contentKeyID: 35242955
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Using the edit Method Modifier [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The edit method modifier is used to indicate that a method’s return value is to be displayed on a form, and users can edit that value. If you don't want users to edit the value, use a display method.

Use the edit method modifier on the following:

  - Table methods

  - Form methods

  - Form data source methods

Write your edit methods on a table. You can use the same code in several forms.

edit methods are called each time the form is redrawn. They should not contain complex and time-consuming calculations.


> [!NOTE]
> <P>edit methods can result in unintended information disclosure. For more information, see <A href="security-on-display-and-edit-methods.md">Security on Display and Edit Methods</A>.</P>
> <P>edit methods are not activated if they are on a hidden tabbed page.</P>



## Create an edit Method

Create an edit method on a form or table.

1.  Place the edit keyword immediately in front of the method’s return type.

2.  Create a Boolean parameter called Set. It is used to determine whether the user has entered anything into the control.

3.  Create a second parameter to hold the values that the user has entered into the control.

4.  If the edit method is on a form data source, create a third parameter for the data source. Place this parameter after the Set parameter.

Following is an example of an edit method on a table.

edit FreeTxt txtDefault(boolean Set, FreeTxt Txt)

Following is an example of an edit method on a form data source.

edit Amount settle(boolean set, CustTrans \_CustTrans, Amount U)

edit methods must have a return type. The return value is typically a calculated value (for example, a sum). For an example, see [How to: Add a Control to a Form](how-to-add-a-control-to-a-form.md).

## Use an edit Method on a Form or a Report

To use an edit method on a form, the control and the return type of the method must have identical types. For example, if you have a RealEdit control on your form, the edit method you are using must return a value of type real.

Add the edit method to a form control.

1.  Set the DataSource property for the control to the data source that contains the method.
    
    If you do not set the DataSource property, the system assumes that the method has been defined on the form.

2.  Set the DataMethod property to the name of the method.

You might also want to set the ExtendedDataType or ArrayIndex properties:

  - If the ExtendedDataType property is set, formatting, Help text, and so on are inherited from the type specified here.

  - If the edit method returns an array, set ArrayIndex to 0 to indicate that all array elements are to be shown in the control. If, for example, you set it to 2, only array element number two is shown.

## See also

[Using the display Method Modifier](using-the-display-method-modifier.md)

[Security on Display and Edit Methods](security-on-display-and-edit-methods.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

