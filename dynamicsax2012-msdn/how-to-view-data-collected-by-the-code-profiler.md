---
title: 'How to: View Data Collected by the Code Profiler'
TOCTitle: 'How to: View Data Collected by the Code Profiler'
ms:assetid: 44dba221-3680-434f-a7b6-f29a46b54fe5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa637896(v=AX.60)
ms:contentKeyID: 35242962
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: View Data Collected by the Code Profiler 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To view the data that is collected by the code profiler:

1.  Click **Profiler runs**.

2.  Select the data set that you want to view.

3.  Click the **Statistics** tab to view a summary of the information for the code profile.

4.  Click one of the following four buttons to view more detailed data:
    
    **Call tree** – Shows you a hierarchy of method calls
    
    **Profile lines** – Shows a list of all lines of code that are executed, making it easy to find which lines of code took the longest to execute.
    
    **Traverse** – Shows a sorted list of the time that was spent in all methods, combined with the sum of the time spent in sub calls, plus the sum of the time spent in the method, depending on the origin of the call.
    
    **Totals** – Allows you to select summaries of the time spent in lines, methods, and objects.

The **Call tree**, **Profile lines**, and **Traverse** forms show raw data. Aggregated data is available in the **Totals** options.

For more information about the statistics and the more detailed data, press F1 on the appropriate form in Microsoft Dynamics AX.

## See also

[MorphX Development Tools](morphx-development-tools.md)

[How to: Use the Code Profiler](how-to-use-the-code-profiler.md)

[Using the Code Profiler from X++](using-the-code-profiler-from-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

