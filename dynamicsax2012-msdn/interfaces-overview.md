---
title: Interfaces Overview
TOCTitle: Interfaces Overview
ms:assetid: fbe8e7ae-1593-49cd-a32f-ed6b6bcfd8d0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa892319(v=AX.60)
ms:contentKeyID: 35254197
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Interfaces Overview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In X++ an interface is a specification for a set of public instance methods. To create an interface, you begin by using the AOT to create a class. You edit the code of its classDeclaration node to replace the keyword class with the keyword interface. Then you add methods to the interface just as you would for a class, except no code is allowed inside the method bodies.

The purpose of interfaces is to define and enforce similarities between unrelated classes without having to artificially derive one class from the other.

**Implements and extends**   
You can add the implements keyword on a class declaration, and this requires the class to declare the methods that are specified by the interface. A class declaration can implement multiple interfaces by listing them after the single occurrence of the implements keyword, with commas separating the interface names.

An interface can extend another interface by using the extends keyword. An interface cannot extend more than one interface.

**Public**   
All interfaces are public regardless of whether you explicitly write the keyword public in front of the keyword interface in the classDeclaration. The methods on an interface are also public, and again the explicit inclusion of the keyword public is optional.

All interface methods that a class implements must be declared with the explicit keyword public in the class. Also, a class that implements an interface must also be declared with public.

## Related Code Examples

This section shows the code for an imaginary Automobile class that implements two interfaces. The classDeclaration code for the class is shown, as is the classDeclaration for one of the interfaces. Also, the code for the getSpeed method is shown for the class and the interface.

### ![Aa892319.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa892319.collapse_all(en-us,AX.60).gif")IDrivable Interface

First is the classDeclaration for the interface IDrivable.

![X++ interface classDeclaration](images/Aa892319.IFace-AX6-IDrivable-d1(en-us,AX.60).png "X++ interface classDeclaration")

**classDeclaration for interface IDrivable**

  
Next is the specification that the interface IDrivable has for the getSpeed method.

![IDrivable specification of the getSpeed method](images/Aa892319.IFace-AX6-IDrivable-getSpeed-dgs1(en-us,AX.60).png "IDrivable specification of the getSpeed method")

**getSpeed method specification on IDrivable**

### ![Aa892319.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa892319.collapse_all(en-us,AX.60).gif")Automobile Class

Now we examine the code in the Automobile class that implements the IDrivable interface.

![X++ code for Automobile classDeclaration](images/Aa892319.IFace-AX6-Automobile-Class-a1(en-us,AX.60).png "X++ code for Automobile classDeclaration")

**classDeclaration for Automobile, include the implements keyword**

  
Finally we examine the full implementation of the getSpeed method on the Automobile class. The method contains X++ in its body between the {}.

![X++ getSpeed method with code body](images/Aa892319.IFace-AX6-Automobile-getSpeed-ags1(en-us,AX.60).png "X++ getSpeed method with code body")

**getSpeed method implementation**

## 'is' Keyword Works for Interfaces

The following code example demonstrates that the keyword is does work for a class that implements an interface.
```X++
    static public void Main(Args _args)   // X++
    {
        IDrivable yourIDrivable;
        Automobile myAutomobile;
        str sTemp = "'is' keyword does Not work for interfaces.";
            
        myAutomobile = new Automobile();
        
        if (myAutomobile is IDrivable)
        {
            yourIDrivable = myAutomobile;
            yourIDrivable.setSpeed(42);
            sTemp = int2str(yourIDrivable.getSpeed());
        }
        
        Global::info(sTemp);
        return;
    }
    /***  Output to Infolog:
    Message (06:46:33 pm)
    42
    ***/
```
The keyword is also works for a class that extends another class.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

