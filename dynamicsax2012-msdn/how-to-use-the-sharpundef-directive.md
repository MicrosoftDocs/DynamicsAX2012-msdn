---
title: 'How to: Use the #undef Directive'
TOCTitle: 'How to: Use the #undef Directive'
ms:assetid: d233340b-6fbd-41ba-9131-7b729e052458
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc197121(v=AX.60)
ms:contentKeyID: 35251890
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use the \#undef Directive 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the \#undef directive to remove a macro definition that exists from a previous \#define. After a macro name has been created by \#define and then removed by \#undef, the macro can be created again by another \#define.

\#undef has no effect on macros that are created by the \#localmacro directive.

## Prerequisites

For this topic, you must understand the information in [How to: Use \#define and \#if to Test a Macro](how-to-use-sharpdefine-and-sharpif-to-test-a-macro.md).

## Using \#undef

In the following code sample, the macro MyMacro is undefined by using the \#undef directive. The \#undef occurs between the two \#if tests for its existence. The output shows only the first \#if test was true.

    static void UndefMacroJob(Args _args)
    {
        ;
        #define.MyMacro
    
        #if.MyMacro
            info("Macro is defined (1)");
        #endif
    
        #undef.MyMacro // Removes the macro.
    
        #if.MyMacro
            info("Macro is defined (2)");
        #endif
    
    /************* Actual output
    Message (10:19:15 am)
    Macro is defined (1)
    *************/
    }

## See also

[Macros in X++](macros-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

