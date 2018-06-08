---
title: Using the Code Profiler from X++
TOCTitle: Using the Code Profiler from X++
ms:assetid: c0c2cc92-ef1d-4691-bfd6-b837d2a8359f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa863679(v=AX.60)
ms:contentKeyID: 35250079
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Using the Code Profiler from X++ 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

As an alternative to the [graphical user interface](how-to-use-the-code-profiler.md), you can control the code profiler directly from your X++ code. For this purpose there are two macros:

  - \#Profilebegin()

  - \#ProfileEnd

These two macros have to be in the same level in a method.

Following is a simple job that shows the use of the macros:

    static void codeProfilerTest() 
    { 
        int   i, j; 
        ;   
        #profileBegin("test")   
        
        for(i=1;   i<=10; i++) 
        {   
            j+=   i*i; 
        }   
        
        info(strfmt("%1",j));   
        #profileEnd   
    } 

You will then have to find the collected data under **Tools** \> **Code profiler** \> **Profiler runs**, and process the data yourself by selecting **Totals** \> **Calculate sum**.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

