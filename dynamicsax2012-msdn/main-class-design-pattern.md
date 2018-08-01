---
title: Main Class Design Pattern
TOCTitle: Main
ms:assetid: cb369ea7-2c72-4c45-a7af-6a0f443f003d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa868593(v=AX.60)
ms:contentKeyID: 35251400
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Main Class Design Pattern [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Use the main class design pattern whenever a class is called from a menu item.

Do not call the main method explicitly from the code; call it implicitly it from a menu item.

The following list describes how to implement the main class design pattern:

  - Instantiate the class by calling the static construct method.

  - Call the prompt method to create a dialog box.

  - If the user clicks **OK** in the dialog box, call the run method.

Most classes that have a main method are candidates to be implemented by the [RunBase framework](runbase-framework.md).


> [!TIP]
> <P>A code editor script can be used to create the main method. In code editor, press Alt + M to open the editor scripts menu, and then select <STRONG>template</STRONG> &gt; <STRONG>method</STRONG> &gt; <STRONG>main</STRONG>.</P>



## See also

[Best Practices for Static Construct Methods](best-practices-for-static-construct-methods.md)

[Methods in X++](methods-in-x.md)

[RunBase Class](https://msdn.microsoft.com/en-us/library/gg822570\(v=ax.60\))

[How to: Access a Class from a Menu](how-to-access-a-class-from-a-menu.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

