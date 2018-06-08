---
title: Best Practices for Local Functions
TOCTitle: Local Functions
ms:assetid: e743b32a-543a-4d61-9ce3-0aa472705e15
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa881716(v=AX.60)
ms:contentKeyID: 35253223
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Local Functions 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Use private class methods instead of local functions (local methods) wherever possible. Local functions cannot be overridden, overlayered, or reused.

Local functions follow all other standards for methods—name, style, layout, and so on. However, local functions cannot be used from outside the method where they are defined.

Local function declarations should be indented to the same level as the types in the variable declarations. Like other declarations, they should be at the top of the code block and separated from other code by a semicolon (;) on a blank line. An example follows.

    protected void setValueQty()
    {
        InventTransPosting  inventTransPosting;
        InventSum           inventSum;
        InventDim           inventDim;
    
        void addPhysical()
        {
            if (inventTransPosting.isPosted)
                ...
        }
        ; // Semicolon at the end of the declarations
          // ... More code
    }

## See also

[Best Practices for Methods](best-practices-for-methods.md)

[Best Practices for Parameters](best-practices-for-parameters.md)

[Best Practices for Table Methods](best-practices-for-table-methods.md)

[Best Practices for Method Modifiers](best-practices-for-method-modifiers.md)

[Naming Conventions: Methods](naming-conventions-methods.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

