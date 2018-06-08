---
title: Change Company Design Pattern
TOCTitle: Change Company Design Pattern
ms:assetid: ba6e5263-279d-4525-90ae-5750461dee35
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa860755(v=AX.60)
ms:contentKeyID: 35249904
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Change Company Design Pattern 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A change to the design pattern of a large company is often the result of it being split into several legal entities. The Microsoft Dynamics AX development environment supports this by using the changeCompany function in X++.

The changeCompany statement is used to alter the database settings to another (separate) company. The syntax of the statement is:

changeCompany ( Expression ) Statement

Expression is a string that defines which company is to be used. The statement is executed on the new company. The following example shows how to use this statement.

    static void main()
    {
        CustTable custTable;
        ;
     
        // Assume that you are running in company 'aaa'.
        changeCompany('bbb') // Default company is now 'bbb'.
        {
            custTable = null;
            while select custTable
            {
                // custTable is now selected in company 'bbb'.
            }
        }
        // Default company is again set back to 'aaa'.
     
        changeCompany('ccc') // Default company is now 'ccc'.
        {
        
            // Clear custTable to let the select work
            // on the new default company.
            custTable = null;
        
     
            while select custTable
            {
                // custTable is now selected in company 'ccc'.
            }
        }
        // Default company is again 'aaa'.
    }

## changeCompany Interactions with crossCompany

The changeCompany keyword is useful in scenarios where the crossCompany keyword is used. For more information, see [Cross-Company Data Modification Using X++](cross-company-data-modification-using-x.md).

## See also

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

