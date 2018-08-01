---
title: Creating a Subclass
TOCTitle: Creating a Subclass
ms:assetid: 377a85c0-702f-49b4-a49a-b340ac090bb4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa636326(v=AX.60)
ms:contentKeyID: 35242044
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Creating a Subclass [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Subclasses are classes that extend (inherit from) other classes. In X++, a new class can only extend one other class; multiple inheritance is not supported. If you extend a class, it inherits all the methods and variables in the parent class (the superclass).

Subclasses enable you to reuse existing code for a more specific purpose, saving time on design, development, and testing. To customize the behavior of the superclass, override the methods in your subclass.

For terminology, a superclass is often called a base class, and a subclass is often called a derived class.

For more information about overriding a method, see [Overriding a Method](overriding-a-method.md).

## Example

The following example creates a class called Point and extends it to create a new class called ThreePoint.
```X++  
    class Point
    {
        // Instance fields.
        real x; 
        real y; 
        ;
     
        // Constructor to initialize fields x and y.
        new(real _x, real _y)
        { 
            x = _x;
            y = _y;
        }
    }
     
    class ThreePoint extends Point
    {
        // Additional instance fields z. Fields x and y are inherited.
        real z; 
        ;
    
        // Constructor is overridden to initialize z.
        new(real _x, real _y, real _z)
        {
            // Initialize the fields.
            super(_x, _y); 
            z = _z;
        }
    }
```
## Preventing Class Extension

You can prevent classes from being extended by using the final modifier:

public final class Attribute   
 {   
     int objectField;   
 }

## See also

[Table Inheritance Overview](table-inheritance-overview.md)

[Classes in X++](classes-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

