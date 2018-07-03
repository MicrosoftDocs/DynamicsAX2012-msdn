---
title: 'How to: Use a Macro Value'
TOCTitle: 'How to: Use a Macro Value'
ms:assetid: dd712564-094a-436a-a5af-b40616bca46c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc197125(v=AX.60)
ms:contentKeyID: 35252082
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use a Macro Value 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can define a macro name to have a value. A macro value is a sequence of characters. A macro value is not a string (or str) in the formal sense of a data type.

You assign a value to a macro by appending the value enclosed in parentheses at the end of a \#define directive.

You can use the macro symbol where you want the value to occur in the X++ code. A macro symbol is the name of the macro with the \# character added as a prefix.

## Prerequisites

For this topic, you must understand the information in [How to: Use \#define and \#if to Test a Macro](how-to-use-sharpdefine-and-sharpif-to-test-a-macro.md).

## Syntax for Using a Macro Value

The following code sample shows a macro symbol \#MyMacro. The symbol is replaced by the value of the macro.

```X++
    static void MacroWithIntValueJob(Args _args)
    {
        int iTest = 8;
        ;
        #define.MyMacro(32)
    
        // This next #define, which has no value for the macro name,
        // would not disrupt the value 32 set by the previous #define.
        //#define.MyMacro
    
        // This next #define, which has a different value than 32,
        // would overwrite the value 32 set by the previous #define.
        //#define.MyMacro(444)
    
        iTest = #MyMacro;
        info(int2str(iTest));
    
    /**********  Actual output
    Message (04:33:49 pm)
    32
    **********/
    }
```

## See also

[Macros in X++](macros-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

