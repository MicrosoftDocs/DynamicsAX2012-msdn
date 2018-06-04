---
title: 'X++, C# Comparison: Precompiler Directives'
TOCTitle: 'X++, C# Comparison: Precompiler Directives'
ms:assetid: 0b2e4e2d-aca5-4ccb-9cfd-cd8d693fdddf
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dd252587(v=AX.60)
ms:contentKeyID: 35240365
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++, C\# Comparison: Precompiler Directives 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

X++ and C\# share some keywords for their precompiler directive syntax, but the meanings are not always the same.

## X++ to C\# Comparisons

The following sections describe the similarities and differences between the precompiler directives used in X++ and C\#.

### ![Dd252587.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dd252587.collapse_all(en-us,AX.60).gif")Similarities

The X++ and C\# compilers recognize many of the same keywords. In most cases, the keywords mean the same for both language compilers.

### ![Dd252587.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dd252587.collapse_all(en-us,AX.60).gif")Differences

A fundamental difference between the precompiler directives in X++ versus C\# is the \#define keyword that both language precompilers recognize. Unlike C\#, in X++ the \#define directive requires a dot in its syntax. In X++, parentheses can be used to give the defined symbol a value. These differences are shown in the following examples:

  - In X++: \#define.InitialYear(2003)

  - In C\#: \#define InitialYear

A minor difference is that in C\# there can be spaces and tab characters between the \# character and the directive keyword, such as \# define Testing.

## Comparison Tables

The following tables compare the details of precompiler directives between X++ and C\#.

### ![Dd252587.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dd252587.collapse_all(en-us,AX.60).gif")Identical Keywords

The following table lists precompiler directives that are similar in X++ and C\#.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Keyword</p></th>
<th><p>X++</p></th>
<th><p>C#</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>#define</p></td>
<td><p>In X++, a precompiler variable name can be defined, and a value can be given to that variable.</p></td>
<td><p>In C#, a precompiler variable name can be defined, but no value can be given to that variable. Also, any #define in C# must occur at the top of the file, and cannot occur after any code such as a using statement or a class declaration.</p></td>
<td><p>The C# compiler can input a command line parameter of /define to define a precompiler variable name without defining the variable in any C# code file. The X++ compiler has no counterpart to /define.</p></td>
</tr>
<tr class="even">
<td><p>#if</p></td>
<td><p>In X++, #if can determine whether a precompiler variable exists, and whether the variable has a given value.</p></td>
<td><p>In C#, #if can only determine whether a precompiler variable exists. It cannot test for any value because no value can be assigned.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>#endif</p></td>
<td><p>In X++, #endif marks the end of an #if block. It also ends an #ifnot block.</p></td>
<td><p>In C#, #endif marks the end of an #if block, regardless of whether the block includes a #else.</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


### ![Dd252587.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dd252587.collapse_all(en-us,AX.60).gif")Different Keywords with the Same Processing Result

The following table lists precompiler directives that are named differently in X++ and C\#, but that give the same results when processed.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++</p></th>
<th><p>C#</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>#ifnot</p></td>
<td><p>#if</p>
<p>#else</p></td>
<td><p>There is no #else directive in X++, but the #ifnot provides similar functionality. In X++, #ifnot can determine whether a precompiler variable exists, and whether the variable does not have a specific given value.</p>
<p>In C#, #if can determine whether a precompiler variable exists when the ‘!’ symbol is prefixed to the variable name.</p></td>
</tr>
<tr class="even">
<td><p>//BP Deviation documented</p></td>
<td><p>#pragma warning</p></td>
<td><p>These X++ and C# entries are not equivalent, but there is a partial similarity. Both suppress compiler warning messages.</p></td>
</tr>
<tr class="odd">
<td><p>#macrolib</p></td>
<td><p>.HPP file in C++</p></td>
<td><p>There is a partial similarity between the X++ directive #macrolib versus an .HPP file in C++. Both can contain several #define statements.</p></td>
</tr>
</tbody>
</table>


### ![Dd252587.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dd252587.collapse_all(en-us,AX.60).gif")Precompiler Directives Exclusive to X++

The following table lists X++ precompiler directives that have no direct counterpart in C\#.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>#linenumber</p></td>
<td><p>The #linenumber directive is for obtaining the line number, so that it can be output to the <strong>Infolog</strong>.</p>
<p>The C# directive #line is different because its purpose is for setting the line number.</p></td>
</tr>
<tr class="even">
<td><p>#defdec</p>
<p>#definc</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>#globaldefine</p></td>
<td><p>In X++, there is a small difference between #globaldefine versus #define. The difference is that #globaldefine never overwrites a current nonnull value that was assigned to a precompiler variable by #define.</p>
<p>C# has nothing similar to this difference, because in C#, a precompiler variable name cannot be given a value.</p></td>
</tr>
<tr class="even">
<td><p>#localmacro</p>
<p>#macro</p></td>
<td><p>In X++, #localmacro enables you to assign a multiline value to a precompiler variable. #macro is a synonym, but #localmacro is recommended.</p>
<p>In C#, the #define directive has part of this functionality, but it cannot assign a value to a precompiler variable.</p></td>
</tr>
<tr class="odd">
<td><p>#globalmacro</p></td>
<td><p>In X++, #globalmacro is almost the same as the preferred #localmacro.</p></td>
</tr>
</tbody>
</table>


## See also

[X++, C\# Comparisons](x-csharp-comparisons.md)

[Macros in X++](macros-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

