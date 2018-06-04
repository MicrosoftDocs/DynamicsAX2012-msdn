---
title: 'X++ Standards: Constants'
TOCTitle: 'X++ Standards: Constants'
ms:assetid: 969c5681-7ba8-424f-9d8c-a5a57eb4c697
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa843942(v=AX.60)
ms:contentKeyID: 35247643
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++ Standards: Constants 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Follow the best practices rules about using constants. These are designed to make it easier to maintain X++ code.

## Constants

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Rule</p></th>
<th><p>Error level</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Do not use hard-coded constants (except 0, 1, 100).</p></td>
<td><p>Warning</p></td>
</tr>
<tr class="even">
<td><p>Define constants in a method, class declaration, or if necessary globally in a macro. Reuse existing constants.</p>
<p>Consider alternative ways of getting the constant:</p>
<ul>
<li><p><a href="intrinsic-functions.md">Intrinsic Functions</a></p></li>
<li><p>maxInt, minInt, funcName, maxDate system functions</p></li>
<li><p>Global macros</p></li>
</ul></td>
<td><p>None</p></td>
</tr>
</tbody>
</table>


## User Interface Text

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Rule</p></th>
<th><p>Error level</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>User interface text must be in double quotes, and you must always use a label (also in double quotes).</p></td>
<td><p>Error</p></td>
</tr>
<tr class="even">
<td><p>User interface labels must be complete sentences. Do not build sentences using more than one label, or other constants or variables under program control (do not use concatenation).</p>
<p>Example:</p>
<p>Description description = &quot;@SYS12345&quot;</p>
<p>Use strFmt to format user interface text.</p></td>
<td><p>None</p></td>
</tr>
</tbody>
</table>


## System-oriented Text

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Rule</p></th>
<th><p>Error level</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>System-oriented text constants must be in single quotes.</p></td>
<td><p>None</p></td>
</tr>
<tr class="even">
<td><p>Do not hard-code text.</p></td>
<td><p>Warning</p></td>
</tr>
<tr class="odd">
<td><p><span id="rx82uidquoteslab"></span>Do not use labels. You will get a warning if a label is used inside single quotes.<br />
Example:</p>
<pre><code>#define.Filename(&#39;myFile.txt&#39;)
Filename filename = #Filename;</code></pre></td>
<td><p>Warning</p></td>
</tr>
</tbody>
</table>


## Numeric Constants

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Rule</p></th>
<th><p>Error level</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Always review the direct use of numeric constants, except for 0 meaning null, 1 meaning increment, and 100 when calculating percents and currencies.</p></td>
<td><p>None</p></td>
</tr>
<tr class="even">
<td><p>Certain numeric constants are predefined, such as the number of days per week, and the number of hours per day. For example, see the TimeConstants and SysBitPos macros in the Application Object Tree (AOT).</p></td>
<td><p>None</p></td>
</tr>
</tbody>
</table>


## See also

[X++ Coding Standards](x-coding-standards.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

