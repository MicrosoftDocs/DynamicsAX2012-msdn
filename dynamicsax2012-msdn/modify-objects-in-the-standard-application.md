---
title: Modify Objects in the Standard Application
TOCTitle: Modify Objects in the Standard Application
ms:assetid: 48aa3503-e88b-478f-827f-ebdc7cead160
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa595378(v=AX.60)
ms:contentKeyID: 35243136
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Modify Objects in the Standard Application [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you modify application objects in the Microsoft Dynamics AX standard application, implement the modifications by using one of the following techniques:

  - Modify an existing application object

  - Create a new application object that replaces the original application object

If the modification is small, such as adding a few new buttons or some new fields to a form, make the modifications in the original form. This creates a copy of the form in a new layer.

If there are many modifications or a total redesign of the form, it is often better to create a new form as a copy of a standard form. You must set the menu item to point to the new object. However, the upgrade wizard does not notify you when the original form changes, which is a disadvantage.

When adding new functionality to an application object, a general strategy is to add a new method, and then call it from the application object. This helps minimize the task of porting the modifications when an upgrade is performed. If the new functionality was implemented directly in one of the existing methods, it would be more time-consuming to port the functionality.

## Add Comments

Add a comment whenever a modification is made to code in an application object in the standard application as shown in the following example.

void methodName()

{

// Standard X++ code.

// \<Your Module Name\> Begin.

this.myNewMethod();

// \<Your Module Name\> End.

// Standard X++ code.

}

Both the beginning and the end of the new code are marked by the comments. The comments include the name of your custom module.

## Overlayering and Overriding Classes

The following figure shows the difference between overlayering and extending.

![Difference between overlayering and extending](images/Aa595378.image006(en-us,AX.60).gif "Difference between overlayering and extending")

**Difference between overlayering and extending**

The following information corresponds to the numbers in the previous figure:

1 – Create a new layer if all modules are to use the modified functionality.

2 – Create a subclass to be used instead of the base class only if your new module needs the modified functionality.

If the base class has been constructed by using the [ClassFactory Class](https://msdn.microsoft.com/en-us/library/gg835446\(v=ax.60\)) class, it can have more than one explicit constructor. Instead of creating a new subclass, extend the class and overlayer only the explicit constructor(s) in the base class as shown in the following figure.

![Extending a class based on ClassFactory](images/Aa595378.image008(en-us,AX.60).gif "Extending a class based on ClassFactory")

**Extending a class created by using the ClassFactory class**

The following information corresponds to the numbers in the previous figure:

1 - The explicit constructor in the base class is modified (overlayered) to create an object of the ExtendedMyClass type.

2 - The methods in the extended class can refer to the base functionality by using super().

By using this technique, overlayer only one method (the explicit constructor in the base class). While you gain all the usual benefits of inheritance, you don't need to modify all the objects that refer to the base class.

## See also

[Designing a Microsoft Dynamics AX Application](designing-a-microsoft-dynamics-ax-application.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

