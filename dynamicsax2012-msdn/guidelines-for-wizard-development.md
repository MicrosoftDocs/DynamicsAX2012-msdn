---
title: Guidelines for Wizard Development
TOCTitle: Guidelines for Wizard Development
ms:assetid: abe0a775-c98d-41f1-8a3a-c353151abe7a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa853845(v=AX.60)
ms:contentKeyID: 35249677
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Guidelines for Wizard Development 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you create a new wizard in Microsoft Dynamics AX, use the following guidelines:

  - Model your wizard after those in Microsoft Windows.

  - Include a statement of purpose the on first page of the wizard.

  - Include a graphic on the left side of the first page.
    
    This helps establish a reference point (or theme). For example, a conceptual rendering, a snapshot of the area of the display that will be affected, or a preview of the result.
    
    You can continue to include a graphic on the interior pages for consistency. If space is critical, use the entire width of the window to display instructional text and controls that require user input.

  - Minimize the number of pages that require the display of a secondary window, which can be confusing.

  - Display a wizard window so that the user can recognize it as the primary point of input. For example, if you display a wizard from a control that the user chooses in a secondary window, you may need to position the wizard window so that it partially obscures that secondary window.

  - Avoid designing wizards that require users to navigate elsewhere to complete a task.

  - Make it visually clear that the user interface elements in a graphic illustration on a wizard page are not interactive. Do so by varying elements from their normal sizes or rendering them more abstractly.

  - Include default values or settings for controls whenever possible.

  - Do not advance pages automatically. Wizards are designed for the user to decide when settings are such that they can advance.

  - Make it obvious to users what to do after they have completed the wizard. Do so in the text on the last page of the wizard.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

