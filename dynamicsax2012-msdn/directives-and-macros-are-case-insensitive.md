---
title: Directives and Macros are Case-Insensitive
TOCTitle: Directives and Macros are Case-Insensitive
ms:assetid: d6b1f063-7d01-41f7-b2ed-06e7c326bf99
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc197122(v=AX.60)
ms:contentKeyID: 35252058
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Directives and Macros are Case-Insensitive [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The X++ precompiler directives, the macro names that they define, and the \#if directive value tests are all case-insensitive. However, it is considered among the [Macros Best Practices](macros-best-practices.md) to begin macro names with an uppercase letter.

## Prerequisites

For this topic, you must understand the information in [How to: Test a Macro Value](how-to-test-a-macro-value.md).

## Code Sample

The following X++ code sample shows mismatches in casing. The output shows that the precompiler is case-insensitive.
```X++  
    static void CaseInsensitiveDirectiveMacroJob(Args _args)
    {
        ;
        //-----------  #localmacro  --------
        #LOcalMAcro.YOurLM
            info("From YOurLM localmacro.");
        #ENdMAcro
        #yoURLM // Mismatched casing of the macro name symbol.
    
        //-----------  #define  --------
        #deFine.MyMaCRO("TheVaLUE")
        // Mismatched casings, in macro name, and in parentheses.
        #iF.mYmacro("ThEvaLUE")
            info("The # if test for value is case-insensitive for the value.");
        #eNdif
    
    /************  Actual Infolog output
    Message (09:38:53 am)
    From YOurLM localmacro.
    The # if test for value is case-insensitive for the value.
    ************/
    }
```
## See also

[Macros in X++](macros-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

