---
title: 'Naming Conventions: Use of Uppercase and Lowercase'
TOCTitle: Use of Uppercase and Lowercase
ms:assetid: d3ce2624-ee03-4e35-a333-7492ec7ea97f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa872604(v=AX.60)
ms:contentKeyID: 35251981
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Naming Conventions: Use of Uppercase and Lowercase 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Application objects names are mixed case. The first letter of the application object is uppercase. The first letter of each internal word is uppercase. For example, AddressFormatHeading, SalesAmount. Application objects include tables, maps, extended data types, base enums, table collections, macros, classes, forms, reports, queries, menus, and menu items.

Methods, system functions, and variables have mixed-case names with a lowercase first letter. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon") The first letter of each internal word is capitalized. For example, classDeclaration, createProject.

Primitive types have lowercase names. For example, str, date, int, real, void, boolean. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

true, false, and null are all lowercase.

[Reserved words](x-keywords.md) in the X++ language all begin with a lowercase letter. For example, if, while, for, select, ttsCommit.


> [!TIP]
> <P>Use the function <STRONG>Add-Ins</STRONG> &gt; <STRONG>Source code title case update</STRONG> to "wash" your code to have correct case.</P>
> <P>If you use version control within Microsoft Dynamics AX and the <STRONG>RunTitleCaseUpdate</STRONG> option has been set to Yes, errors in the capitalization of the first letter of names are automatically corrected when you check the object in. The <STRONG>RunTitleCaseUpdate</STRONG> option is typically set by an administrator. It is available on the <STRONG>General</STRONG> tab of the <STRONG>Version Control Configuration</STRONG> form, which can be opened from <STRONG>Tools</STRONG> &gt; <STRONG>Development tools</STRONG> &gt; <STRONG>Version control</STRONG> &gt; <STRONG>Setup</STRONG> &gt; <STRONG>System settings</STRONG>.</P>


  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

