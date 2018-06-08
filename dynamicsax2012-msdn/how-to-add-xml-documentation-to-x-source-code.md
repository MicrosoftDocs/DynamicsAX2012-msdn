---
title: 'How to: Add XML Documentation to X++ Source Code'
TOCTitle: 'How to: Add XML Documentation to X++ Source Code'
ms:assetid: fcb77e44-180c-4857-a0f0-6b332e1f9665
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc643018(v=AX.60)
ms:contentKeyID: 35254201
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add XML Documentation to X++ Source Code 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can create XML documentation files from XML documentation that is written in X++ code. This topic explains how to insert the XML documentation in X++ code.

## Inserting XML Documentation

XML documentation in X++ code is preceded by three slashes rather than two slashes, to distinguish it from typical code comments. It must be located at the very start of the code. The following procedure explains how to add XML documentation to source code.

### To insert an XML documentation header into X++ application source code

1.  In the AOT, double-click a class declaration or method.

2.  Right-click in the code editor, point to **Scripts**, point to **documentation**, and then click **HeaderTemplate**. Alternatively, with your cursor positioned on an empty line above the code, type ///.

3.  Write documentation between the XML tags.

## See also

[XML Documentation Overview](xml-documentation-overview.md)

[XML Documentation Tags](xml-documentation-tags.md)

[How to: Generate XML Documentation Files](how-to-generate-xml-documentation-files.md)

[Walkthrough: Creating XML Documentation in Microsoft Dynamics AX](walkthrough-creating-xml-documentation-in-microsoft-dynamics-ax.md)

[Best Practices: XML Documentation](best-practices-xml-documentation.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

