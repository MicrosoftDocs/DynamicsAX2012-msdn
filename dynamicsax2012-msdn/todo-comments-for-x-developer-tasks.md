---
title: TODO Comments for X++ Developer Tasks
TOCTitle: TODO Comments for X++ Developer Tasks
ms:assetid: 03afe7dd-dae6-4722-a034-274d4249ba14
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg843451(v=AX.60)
ms:contentKeyID: 35240243
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# TODO Comments for X++ Developer Tasks [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Microsoft Dynamics AX X++ language compiler recognizes the string TODO when it occurs at the start of a comment. The TODO string prompts the X++ compiler to report the rest of the comment text on the **Tasks** tab, which is located in the **Compiler output** window of the client. The **Tasks** tab also reports the line number in the code where the TODO comment can be found.

## Rules for Using TODO

The rules for using TODO in comments are as follows:

  - The TODO string can appear in either the // or the /\* \*/ style of comment.

  - The TODO string must be the very first non-white space string in the comment. White space is considered to be a carriage return, a line feed, a tab, or a space.

  - No white space is required between the start of the comment and the TODO.

  - The TODO string is case insensitive. However, the convention is to write TODO in all uppercase letters, instead of ToDo or another variation.

  - The TODO string can have any characters appended to it, but the convention is to either append a colon, or for a white space to follow.

  - The rest of the comment after the TODO string is reported as the task description. If the comment is longer than 200 characters, it might display truncated in the **Tasks** tab.

  - The TODO task description can be spread over multiple lines when the /\* \*/ comment style is used.

## Examples

The following table shows examples of using TODO in the // or the /\* \*/ style of comment.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>// TODO</p></th>
<th><p>/* TODO */</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>public boolean isLate()</p>
<p>{</p>
<p>// TODO: Finish this stub.</p>
<p>return true;</p>
<p>}</p></td>
<td><p>public boolean isLate()</p>
<p>{</p>
<p>/* TODO</p>
<p>Finish this stub.</p>
<p>*/</p>
<p>return true;</p>
<p>}</p></td>
</tr>
</tbody>
</table>


## See also

[Statements and Loops](statements-and-loops.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

