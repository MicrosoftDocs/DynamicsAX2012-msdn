---
title: 'X++ Standards: Comments'
TOCTitle: 'X++ Standards: Comments'
ms:assetid: 9c0ec3e4-cffe-43f8-b863-edfcbf068f83
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa846550(v=AX.60)
ms:contentKeyID: 35248206
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++ Standards: Comments [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Use // for both single and multiline (block) comments. There should be a space between the "//" and the start of the comment.

Comments should be in US-English and start with an uppercase letter (unless the first word is a lowercase name).

Put comments on a separate line before the code they are describing. The only exception to this is when you are describing parameters. In this case, put one parameter per line, with the comment describing it to the right of the parameter.

When creating a multiline comment, do not write on the first or the last line of the comment (as shown in the following example).

For example:

// Single line comment

\<code\>

//

// Comment on multiple lines.

// Do not add text to 1st or last line of comment.

//

\<code\>

Comments should not include:

  - Dates

  - Names

  - Aliases

  - Version or layer references

  - Bug numbers – unless it is a workaround, or unless the code could appear inappropriate if you didn't know that it was for a bug fix.

  - Politically or culturally sensitive phrases


> [!NOTE]
> <P>If you put a comment at the start of the method to describe its purpose and use, you can use block comments (/* */).</P>



## Remove Commented-out Code from the Application

The Best Practice is that we don't ship a product with commented-out code, so any commented-out code should be removed.


> [!TIP]
> <P>To find comments in the source (both // .. and /* .. */), use the <STRONG>Find</STRONG> dialog to search for methods containing the text (regular expression): /[/\*]</P>



## See also

[X++ Coding Standards](x-coding-standards.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

