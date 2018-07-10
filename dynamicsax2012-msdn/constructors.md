---
title: Constructors
TOCTitle: Constructors
ms:assetid: 9ea3b20a-0dd5-4fd8-ad64-bdb3019dd543
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa847755(v=AX.60)
ms:contentKeyID: 35248261
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Constructors 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To create an instance of a class (an object), you have to instantiate it. The default constructor is the new method:

// Declares a variable to refer to a Point object

Point myPoint;

;

// Allocates an instance of a Point object

myPoint = new Point();

It is a best practice to make the new method protected, and instead, use a static construct method, or static new method as the public constructor for the class. If no initialization is required, use a static construct method, otherwise use a static new method. For more information, see [Best Practices for Constructors](best-practices-for-constructors.md).

## Creating Other Objects from a Constructor

A class constructor can instantiate other objects, in addition to creating an instance of the class. The following code illustrates one such situation by declaring a Rectangle class that uses two Point objects to define its bounds.

   ```X++

    class Rectangle
    {
        Point lowerLeft;
        Point upperRight;
    }
     
    new(real _topLeftX, real _topLeftY, real _bottomRightX, real _bottomRightY)
    {
        lowerLeft  = new Point(_topLeftX, _topLeftY);
        upperRight = new Point(_bottomRightX, _bottomRightY);
    }
  ```


## Accessing Members in a Object

X++ does not allow you to access the variables of an object by referring to the names of the variables, qualified with the name of the object:

myPoint.x = 10.0; //Not possible

myPoint.y = 25.7; //Not possible

The only way to access the member variables in a class is through accessor methods. For information about accessor methods, see [Accessor Methods](accessor-methods.md).

## See also

[Destructors](destructors.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

