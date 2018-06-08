---
title: Best Practices for init Methods
TOCTitle: init Methods
ms:assetid: 980ae675-b6c7-48d6-9270-534991ed23c7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa844670(v=AX.60)
ms:contentKeyID: 35247860
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for init Methods 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

If you need to carry out any special initialization tasks after class instantiation and after the setting of class variables by using accessor methods, such logic should be placed in a private method called init.

init methods should be protected, and should have a void return type, or else a Boolean return type if initialization can go wrong, so that an error can be thrown.

If you rely on the user of the class to do one of the following, then you should implement static new... methods, so the mandatory initialization information can be supplied as specific parameters on these methods:

  - Call some specific methods to initialize some member variables, after the user has new'ed the object, to completely initialize the object.

  - Supply the parameters that are actually needed to your new method, having a lot of default parameters

If the new method has some extra initialization logic that is always executed, you should put that in the init method.

## See also

[Best Practices for Accessor Methods](best-practices-for-accessor-methods.md)

[Best Practices for new and static new... Methods](best-practices-for-new-and-static-new-methods.md)

[Best Practices for Constructors](best-practices-for-constructors.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

