---
title: 'How to: Use Parameters with Macros'
TOCTitle: 'How to: Use Parameters with Macros'
ms:assetid: 7f2272a5-6c18-489d-a4b7-fc500294a745
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc197116(v=AX.60)
ms:contentKeyID: 35246130
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use Parameters with Macros [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can define macro values to include parameter symbols. The first parameter symbol is %1, the second is %2, and so on. You pass values for the parameters when you reference the macro symbol name for expansion.

## Prerequisites

For this topic, you must understand the information in [How to: Use a Macro Value](how-to-use-a-macro-value.md).

## Rules About Parameters

Macro parameter values are character sequences of no formal type, and they are comma delimited. There is no way to pass in a comma as part of a parameter value.

The number of parameters passed can be less than, greater than, or equal to the number of parameters that the macro value is designed to receive. The system tolerates mismatches in the number of parameters passed. If fewer parameters are passed than the macro expects, each omitted parameter is treated as a zero-length sequence of characters.

## Passing Parameters to a Macro

In the following code sample, MyMacro is defined to have a value that contains parameters. Macro substitution symbols are given with parameter values in parentheses.

```X++
    static void MacroParameterSubstitutionJob(Args _args)
    {
        ;
        #define.MyMacro("One == [%1] ,  Two == [%2]")
    
        // Make parameter substitutions:
        info("AA: " + #MyMacro(Apple));
        info("BB: " + #MyMacro(Apple,Banana));
        info("CC: " + #MyMacro(Apple, Banana, cranberry));
        info("DD: " + #MyMacro(,Apple,Banana));
        info("EE: " + #MyMacro());
        info("FF: " + #MyMacro);
    
    /************  Actual Infolog output
    Message (03:22:07 pm)
    AA: One == [Apple] ,  Two == []
    BB: One == [Apple] ,  Two == [Banana]
    CC: One == [Apple] ,  Two == [ Banana]
    DD: One == [] ,  Two == [Apple]
    EE: One == [] ,  Two == []
    FF: One == [] ,  Two == []
    ************/
    }
```

## See also

[Macros in X++](macros-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

