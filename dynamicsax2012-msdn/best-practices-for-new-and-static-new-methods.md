---
title: Best Practices for new and static new... Methods
TOCTitle: new and static new... Methods
ms:assetid: 3dc36d87-2835-4412-a435-732d4d1ccc1b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa594035(v=AX.60)
ms:contentKeyID: 35242937
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for new and static new... Methods 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The new method is the default constructor for a class. The new method should be protected. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon") Do not use it to instantiate the class. Use a construct or a static new… method instead.

It is recommended that you do not have parameters on the new method—use static new… methods instead.

X++ does not support method-name overloading. You must create your own individually named static new… methods with different parameter profiles. This enables you to construct a class in more than one way. Similarly, instead of creating default parameters in a new method, create a different static new… method for each possible parameter profile.

If you have created the new method on a subclass, call super() to carry out any necessary initialization that might be implemented in the superclass. The call to super() should be the first statement in the method.

## static new… Methods

Create one or more static new… methods to instantiate your class.

These new methods have the following characteristics:

  - Are public

  - Are static

  - Have a name prefixed with "new"

  - Are named according to the parameter(s) they take, or logically

  - Usually take only nondefault parameters

  - Always return a valid object of the class's type (instantiated as well as initialized), or throw an error

  - Use a [construct method](best-practices-for-static-construct-methods.md) to create an instance of the class

  - Use [accessor methods](best-practices-for-accessor-methods.md) to set the class variables

The static new… methods have a body that contains the following structure.
```X++  
    MyClass myClass;
    ;
    
    // The construct method is used to create an instance of the class.
    myClass = MyClass::construct(...); 
      
    // Use accessor methods to set the class variables.
    myClass.parmOneValue(...);
    myClass.parmAnotherValue(...);
      
    if (!myClass.init())
    {
        throw error("Label text explaining why object was not created");
    }
    return myClass;
```
## See also

[Best Practices for Constructors](best-practices-for-constructors.md)

[Best Practices for init Methods](best-practices-for-init-methods.md)

[Best Practices for Accessor Methods](best-practices-for-accessor-methods.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

