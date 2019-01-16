---
title: Overriding a Method
TOCTitle: Overriding a Method
ms:assetid: e419ac50-de17-4184-8a41-650191395591
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa880278(v=AX.60)
ms:contentKeyID: 35253180
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Overriding a Method 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The methods in a class are inherited by any class that extends it. You can alter the functionality of an inherited method by creating a method in the subclass with the same name and parameters as in the superclass. This is called overriding the method. For example:

// Superclass: Attribute

public class Attribute

{

    int objectVariable;


    void methodAtt()

    {

        // Some statements

    }

}



// Subclass: ColorAttribute

public class ColorAttribute extends Attribute

{

    int addedObjectVariable;


    void methodAtt()

    {

        // Some statements

    }

}

ColorAttribute is a subclass of Attribute and therefore inherits the method methodAttr. However, because ColorAttribute defines a method with the same name and the same number of arguments, the method in the superclass is overridden.

## Preventing Method Overriding

Static methods cannot be overridden because they exist per class. To protect other sensitive methods, or core methods, from being overridden, use the final modifier. In the example below, methodAtt is declared as final, and so it cannot be overridden in any class that extends Attribute.

public class Attribute

{

    int objectVariable;

}

final void methodAtt()

{

    //Some statements

}


> [!NOTE]
> <P>You should not specify new or finalize methods as final.</P>



For more information about inheritance in X++, see [Creating a Subclass](creating-a-subclass.md).

## Overriding vs. Overloading

Overloading is where there is more than one method with the same name, but the methods have different signatures (return type or parameter lists or both).

Overriding is where the superclass's implementation of a method is altered by the subclass's implementation of the method, but the signatures of both methods are the same.

X++ supports overriding, but it does not support overloading.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

