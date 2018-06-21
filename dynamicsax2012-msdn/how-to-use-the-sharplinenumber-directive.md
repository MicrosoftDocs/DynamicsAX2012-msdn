---
title: 'How to: Use the #linenumber Directive'
TOCTitle: 'How to: Use the #linenumber Directive'
ms:assetid: c9010215-09a2-4ba1-aeea-f336cd9d00ce
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc197120(v=AX.60)
ms:contentKeyID: 35251205
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use the \#linenumber Directive [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the \#linenumber directive during your development and debugging of code. It is replaced by the physical line number in the code file.

## Prerequisites

For this topic, you must understand the information in [How to: Use a Macro Value](how-to-use-a-macro-value.md).

## Code Sample for \#linenumber

The following X++ code sample shows the behavior of the \#linenumber directive.

    static void LinenumberPhysicalJob(Args _args)
    {
        ;
        #define.Debug(light)
    
        #if.Debug
            info("Physical Line 8: # linenumber == "
                + int2Str(#linenumber));
        #endif
    
    /******************  Actual Infolog output
    Message (08:55:26 pm)
    Physical Line 8: # linenumber == 8
    ******************/
    }

## See also

[Macros in X++](macros-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

