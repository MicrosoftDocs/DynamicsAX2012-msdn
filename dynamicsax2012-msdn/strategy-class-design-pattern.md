---
title: Strategy Class Design Pattern
TOCTitle: Strategy
ms:assetid: 04c3e9d4-646f-4da1-9b7a-e702ba057325
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa500295(v=AX.60)
ms:contentKeyID: 35240262
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Strategy Class Design Pattern [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Strategy pattern is for doing different things in a similar manner. For example, you have similar switch statements or if statements in your code.

The following code example illustrates similar switch statements:
```X++  
    …
        // First operation
        switch (_direction)
        {
            case up:
                 ...
            case down:
                 ...
        }
        ...
        ...
    }
        ...
        ...
    
        // Second operation
        switch (_direction)
        {
            case up:
                 ...
            case down:
                 ...
        }
```
The following illustrates an example where you split up your code in a class hierarchy:

![Class hierarchy for a strategy pattern](images/Aa500295.ClassModelExample1(en-us,AX.60).gif "Class hierarchy for a strategy pattern")

 

The following code example illustrates using a [construct](best-practices-for-static-construct-methods.md) object and a direction object at the start of your code. Then work on the correct direction object in an abstract way after.
```X++  
    Direction direction = Direction::construct(_direction);
         ...
        direction.firstOperation();
        direction.firstOperation();
         ...
        direction.firstOperation();
         ...
         ...
        direction.secondOperation();
         ...
```
The correct process will occur as the direction object is instantiated to the correct situation.

## See also

[Microsoft Dynamics AX Class Design Patterns](microsoft-dynamics-ax-class-design-patterns.md)

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

