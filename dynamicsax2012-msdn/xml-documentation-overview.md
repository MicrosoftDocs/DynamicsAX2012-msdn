---
title: XML Documentation Overview
TOCTitle: XML Documentation Overview
ms:assetid: abea2ddc-55d9-41bd-ac91-ae4b906c9e5d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc572956(v=AX.60)
ms:contentKeyID: 35249685
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# XML Documentation Overview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can document classes, class methods, and table methods in X++ source code by using XML documentation. You can generate an XML file from this XML documentation.

XML documentation is API level information for consumers of the code. In the code, XML documentation is preceded by three slashes rather than two slashes to distinguish it from typical code comments. Code comments, or double-slash comments, are used to describe the code to people when they read the code. XML documentation is more structured and can be extracted into an XML file.

You can add XML documentation to source code by inserting a header template. A header template is a group of XML tags that precede X++ code in the code editor. For more information about adding XML documentation to source code, see [How to: Add XML Documentation to X++ Source Code](how-to-add-xml-documentation-to-x-source-code.md). When you insert a header template, a \<summary\> tag and a \<remarks\> tag are always included. If XML documentation is added, you should provide a summary. Remarks are optional. If you choose to exclude remarks, delete the \<remarks\> tags. Additional tags will be added based on the syntax of the code. For example, if the code has three parameters, three sets of \<param\> tags will be inserted with values that correspond to the parameters listed in the syntax. If the code has a return type, a set of \<returns\> tags will be inserted. You can add additional XML tags manually. For more information about XML tags, see [XML Documentation Tags](xml-documentation-tags.md) and [Best Practices: XML Documentation](best-practices-xml-documentation.md).

## XML Documentation File

After XML documentation is written in X++ source code, you can extract it to an XML documentation file. You can extract XML documentation from a project or from the entire application. For more information about how to extract XML documentation, see [How to: Generate XML Documentation Files](how-to-generate-xml-documentation-files.md).

## XML Reflection File

The reflection file is an XML file that contains code elements and their attributes. It is created by using reflection information from the AOT. You can create a reflection file for a project or for the entire application. For more information about how to create reflection files, see [How to: Generate XML Documentation Files](how-to-generate-xml-documentation-files.md).

## See also

[XML Documentation](xml-documentation.md)

[XML Documentation Tags](xml-documentation-tags.md)

[How to: Add XML Documentation to X++ Source Code](how-to-add-xml-documentation-to-x-source-code.md)

[Walkthrough: Creating XML Documentation in Microsoft Dynamics AX](walkthrough-creating-xml-documentation-in-microsoft-dynamics-ax.md)

[Best Practices: XML Documentation](best-practices-xml-documentation.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

