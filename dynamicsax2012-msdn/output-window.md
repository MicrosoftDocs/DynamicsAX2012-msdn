---
title: Output Window
TOCTitle: Output Window
ms:assetid: 0b0b4b12-392b-42b9-819b-9cf39b3174e4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa569643(v=AX.60)
ms:contentKeyID: 35239276
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Output Window 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The **Output** window in the Microsoft Dynamics AX debugger has separate views that display text written to the window from X++ code and kernel code. These views organize the information that is sent to the **Output** window. The **Output** window has the following views:

  - **Debug** – Shows information from calls to the Debug class.

  - **Infolog** – Shows text that is sent to the Infolog from either kernel code or X++ code.

  - **Database** – Shows trace text that is sent to the **Output** window from the kernel. To have information sent to this view, you must first enable the **Database trace** in Microsoft Dynamics AX.
    
    To enable the **Database trace**:
    
    1.  Click **Tools** \> **Options**.
    
    2.  Click **Development**.
    
    3.  Select the **Database trace** check box.

<!-- end list -->

  - **Client/Server** – Shows trace text that is sent to the **Output** window from the kernel. To have information sent to this view, you must first enable the **Client/server trace** in Microsoft Dynamics AX.
    
    To enable the **Client/server trace**:
    
    1.  Click **Tools** \> **Options**.
    
    2.  Click **Development**.
    
    3.  Select the **Client/server trace** check box.

<!-- end list -->

  - **ActiveX** – Shows trace text that is sent to the **Output** window from the kernel. To have information sent to this view, you must first enable the **ActiveX trace** in Microsoft Dynamics AX.
    
    To enable the **ActiveX trace**:
    
    1.  Click **Tools** \> **Options**.
    
    2.  Click the **Development** tab.
    
    3.  Select the **ActiveX trace** check box.

The Debug class has the following methods that write content to the views of the **Output** window:

  - Debug::printDebug — Starts the debugger and displays output text on the **Debug** view of the **Output** window.

  - Debug::printTab — Prints text to the view that is specified in the arguments given in the method call.

## See also

[Microsoft Dynamics AX Debugger](microsoft-dynamics-ax-debugger.md)

[Debugger Windows](debugger-windows.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

