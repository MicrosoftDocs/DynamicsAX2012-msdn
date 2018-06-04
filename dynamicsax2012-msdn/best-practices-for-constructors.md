---
title: Best Practices for Constructors
TOCTitle: Constructors
ms:assetid: aca99f9b-8746-4df4-8c3c-82bda5924782
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa854210(v=AX.60)
ms:contentKeyID: 35249720
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Constructors 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Following is information about how to create a clean inheritance model and minimize problems when code is upgraded:

  - Each class must have a single public construction method unless the class is abstract. If no initialization is required, use a static construct method. Otherwise, use a static new… method (the default constructor (new method) for the class should be protected).

  - Each class should have at least one [static construct method](best-practices-for-static-construct-methods.md) method. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

  - Each class should have at least one [static new… method](best-practices-for-new-and-static-new-methods.md).

  - Each class should have a [new method](best-practices-for-new-and-static-new-methods.md) (the default constructor). This method should be protected. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

  - Create [accessor methods](best-practices-for-accessor-methods.md) to get and set class variables.

  - Create [init methods](best-practices-for-init-methods.md) to carry out any specialized initialization tasks that should be carried out after instantiation.

## See also

[Best Practices for Class Declarations](best-practices-for-class-declarations.md)

[Best Practice for Destructors (finalize)](best-practice-for-destructors-finalize.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

