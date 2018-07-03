---
title: Best Practices for Static Construct Methods
TOCTitle: static construct Methods
ms:assetid: 435c1b20-ea29-4d2b-b6db-eb2e5cf1841c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa637432(v=AX.60)
ms:contentKeyID: 35242954
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Static Construct Methods 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You should create a static construct method for each class. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon") The method should return an instance of the class.

The construct method must be:

  - static

  - named "construct"

In most cases the construct method should be public. If the class is instantiated using a newParameter method, then declare the construct method as private. The method should return an instance of the class and contain no other code. construct methods should not have any parameters, or else should have the same parameters as the default new constructor (it is recommended that you do not have parameters on new). ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

If your class declaration contains parameters, use a static new method as the constructor and use the construct method within the static new method to create an instance of the class.

For partners and customizers, this is the point to add construction functionality for new subclasses (in higher layers), without mixing code with the construct method in the original layer.


> [!TIP]
> <P>You can use a code editor script to create the construct method for you. In the code editor, press Alt + M to open the editor scripts menu, and then select <STRONG>template</STRONG> &gt; <STRONG>method</STRONG> &gt; <STRONG>construct</STRONG>.</P>



## Example

```X++
  static CustPaymManFileOpen construct()
    {
        return new CustPaymManFileOpen();
    }
```

## See also

[Best Practices for new and static new... Methods](best-practices-for-new-and-static-new-methods.md)

[Best Practices for Constructors](best-practices-for-constructors.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

