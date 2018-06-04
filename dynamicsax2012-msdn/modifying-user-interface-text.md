---
title: Modifying User Interface Text
TOCTitle: Modifying User Interface Text
ms:assetid: 8dca2d41-f950-4212-a2d2-bd0097d5ccee
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa678556(v=AX.60)
ms:contentKeyID: 35246448
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Modifying User Interface Text 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The recommended way to modify text that appears in the user interface is to modify property values on the extended data types or base enums in the application.

When customizing the text, you can create new labels. However, to ensure consistent terminology in the user interface, you should always reuse standard labels, if possible. Never create duplicates.

The strategy is that SYS labels in Microsoft Dynamics AX are never deleted. This means that you can assume that the SYS labels that you use in your application will be available even after a Microsoft Dynamics AX installation is upgraded.

If a customer requests major terminology changes, the fastest solution may be to make the modifications directly in the label file. However, this strategy is not recommended, because all the modifications will be lost when a new label file is installed; for example, when you install a service pack. Microsoft Dynamics AX does not provide any tools that can assist you in maintaining the modifications that you have made manually in the label file.

## See also

[Best Practices for Labels](best-practices-for-labels.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

