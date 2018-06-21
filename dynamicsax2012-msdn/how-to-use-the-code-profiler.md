---
title: 'How to: Use the Code Profiler'
TOCTitle: 'How to: Use the Code Profiler'
ms:assetid: 03180e5e-6b4f-4819-8827-3180fd5a7d55
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa499181(v=AX.60)
ms:contentKeyID: 35240203
ms.date: 05/18/2015
mtps_version: v=AX.60
f1_keywords:
- Forms.SysCodeProfilerStartStop
- MsDynAx060.Forms.SysCodeProfilerStartStop
- Menu_Items.Display.SysCodeProfilerStartStop
---

# How to: Use the Code Profiler [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

1.  Click **Tools** \> **Code profiler** to open the Code Profiler tool.

2.  Navigate to the functionality that you want to test. For example, navigate to the appropriate place in the **Navigation Pane**.
    
    To limit the results displayed, check the **Trace depth enabled** check box, and then type the number of levels that you want to be displayed in the results.

3.  Click **Start**.

4.  Use the functionality you want to test.

5.  When testing is complete, click **Stop**. The system now saves all logged data to the database. This might take quite some time because a database record is created for each executed line of code.

6.  Write a description of your code profile in the **Summary** dialog.
    
    Do not select the **Calculate line total** check box. If you need to calculate line totals later, use the **Profile runs** form.

7.  Click **OK**.
    
    The **Profiler runs** form opens. This enables you to view data collected by the profiler.
    

    > [!NOTE]
    > <P>You can also use the code profiler from a <A href="using-the-code-profiler-from-x.md">programmatic interface</A>.</P>



## See also

[Code Profiler](code-profiler.md)

[How to: View Data Collected by the Code Profiler](how-to-view-data-collected-by-the-code-profiler.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

