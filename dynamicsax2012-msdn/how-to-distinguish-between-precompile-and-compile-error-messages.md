---
title: 'How to: Distinguish Between Precompile and Compile Error Messages'
TOCTitle: 'How to: Distinguish Between Precompile and Compile Error Messages'
ms:assetid: 05741f69-7989-4b43-887c-010a2b6f57a2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc197106(v=AX.60)
ms:contentKeyID: 35240290
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Distinguish Between Precompile and Compile Error Messages 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you are developing code that contains macros, you must understand whether an error message is generated during the precompile or the compile phase. The two key words to look for are:

  - **Lexical** – This indicates a precompile error.

  - **Syntax** – This indicates a compile error.

## Prerequisites

For this topic, you must understand the information in [How to: Use \#define and \#if to Test a Macro](how-to-use-sharpdefine-and-sharpif-to-test-a-macro.md).

## Code Examples

The following table shows X++ examples that illustrate lexical and syntax errors related to macro use.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Code</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>#define.MyMacro1(info(&quot;Hello&quot;);)</p></td>
<td><p>A <strong>Lexical</strong> error caused by the first closing parenthesis, which marks the end of the directive. Therefore the precompiler is confused by the last two characters ;).</p></td>
</tr>
<tr class="even">
<td><p>#define.MyMacro2(++++iTest;)</p>
<p>#MyMacro2</p></td>
<td><p>A <strong>Syntax</strong> error caused by using the non-existent ++++ operator. The X++ compiler encounters this operator after #MyMacro2 is replaced by the macro value.</p>
<p>The macro definition is correct even though its value is not accepted X++ syntax.</p></td>
</tr>
</tbody>
</table>


## See also

[Macros in X++](macros-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

