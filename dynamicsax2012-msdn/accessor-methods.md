---
title: Accessor Methods
TOCTitle: Accessor Methods
ms:assetid: 271f2fa3-d95e-4726-8f61-1f704bbb727a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa621076(v=AX.60)
ms:contentKeyID: 35241690
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Accessor Methods [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

If an object uses another object to do some work on its behalf, the first object sends a message to the second object. In response, the second object invokes the selected method.

This programming technique is one of the best ways to create models and simulations of complex real-world systems. The following example defines a Point class so that it uses accessor methods to access the variables x and y.

```X++
    class Point
    {
        // Instance variables
        real x; 
        real y;
        
        //Constructor to initialize to a specific or default value
        void new(real _x=10, real _y=10) 
        {
            x = _x;
            y = _y;
        }
     
        //Accessor method
        void setX(real _x) 
        {
            x = _x;
        }
     
        //Accessor method
        void setY(real _y) 
        {
            y = _y;
        }
     
        //Accessor method
        real getX() 
        {
            return x;
        }
     
        //Accessor method
        real getY() 
        {
            return y;
        }
    }
```

These method declarations illustrate how the Point class provides access to its variables from the outside world. Other objects can manipulate the instance variables of Point objects by using the accessor methods:

```X++
//Declare a variable to refer to a Point object
    Point myPoint; 
     
    //Create a Point object
    myPoint = new Point(); 
    //Set the x variable using the accessor method
    myPoint.setX(10.0); 
    //Set the y variable by means of the accessor method
    myPoint.setY(25.7); 
```

By hiding details of the internal implementation of a class, X++ allows the programmer to change the implementation of the class in the future without breaking any code that uses that class.


> [!NOTE]
> <P>The X++ callstack depth is limited to 100.</P>



## See also

[Methods in X++](methods-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

