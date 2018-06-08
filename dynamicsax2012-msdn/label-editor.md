---
title: Label Editor
TOCTitle: Label Editor
ms:assetid: 9d9d2443-5dd6-4913-aab3-53545ed084eb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa617477(v=AX.60)
ms:contentKeyID: 35248254
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Label Editor 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Use the Label Editor to find, edit, and create labels for all user interface elements. To open the label editor:

  - Click **Tools** \> **Label** \> **Label editor**.

Labels can be single words, phrases, or sentences; sentence fragments should not be used because they cannot easily be translated. Labels can be up to 2000 characters long. For additional guidelines about how to create labels, see [Best Practices for Labels](best-practices-for-labels.md) and [HelpText Guidelines](helptext-guidelines.md).

## Tabs

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Tab</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Label</strong></p></td>
<td><p>Search for labels by using the criteria specified on the <strong>Setup</strong> tab. You must search for labels before inserting or editing them, and before creating a new label.</p></td>
</tr>
<tr class="even">
<td><p><strong>Setup</strong></p></td>
<td><p>Select a label file to use on the <strong>Label</strong> tab.</p></td>
</tr>
</tbody>
</table>


## Buttons


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Button</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>New</strong></p></td>
<td><p>Create a new label in the label file.</p></td>
</tr>
<tr class="even">
<td><p><strong>Delete</strong></p></td>
<td><p>Delete a label from the label file.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Used by</strong></p></td>
<td><p>Display the objects that use the label. Use this to select the correct label if there is more than one label with the same text string.</p></td>
</tr>
<tr class="even">
<td><p><strong>Label log</strong></p></td>
<td><p>Display the history of changes to label files in the current installation.</p></td>
</tr>
<tr class="odd">
<td><p>Search icon</p></td>
<td><p>Search for occurrences of the text string in the <strong>Find what</strong> field. Search strings are case insensitive. The following table describes valid search strings.</p>
<div class="caption">
</div>
<div class="tableSection">
<div class="mtps-table">
<div class="mtps-row">
Search string character Description
</div>
<div class="mtps-row">
\ Specifies a specific character. For example, type\$\$ will only return type$$.
</div>
<div class="mtps-row">
&lt; or ^ Matches the start of a line. For example, &lt;type returns type this and type that, but not A type that.
</div>
<div class="mtps-row">
&gt; or $ Matches the end of a line. For example, type&gt; returns Must have a type, but not Incorrect type used.
</div>
<div class="mtps-row">
? or . Matches a single character. For example, type?abc returns typeXabc, but not typeXXabc.
</div>
<div class="mtps-row">
:a Matches any alphabetical character. For example, typ:a returns type, but not typ8 or typ%.
</div>
<div class="mtps-row">
:d Matches any numeric character. For example, typ:d returns typ8, but not type or typ%.
</div>
<div class="mtps-row">
:n Matches any alphanumeric character. For example, typ:n returns type and typ8 but not typ%.
</div>
<div class="mtps-row">
* Matches of any part of the expression when used at the end of a search string. For example, ty* returns t, ty, and type.
</div>
<div class="mtps-row">
+ Matches expressions that contain the search string, when used at the end of a search string. For example, ty+ returns ty, typ, and type, but not t or y.
</div>
<div class="mtps-row">
- Matches part or all of the search expression. The matches always contain the first search character, and zero to one additional characters in sequence from the start of the search string. For example, ty- returns t, and ty, but not y.
</div>
<div class="mtps-row">
[] Matches any one character in the search string, but does not match any combinations of characters in the string. For example, [type] will return t and y, but not ty. Additionally, you can combine other search criteria. For example, [^type] will return any letter, but not t, y, p, or e.
</div>
<div class="mtps-row">
' or &quot; Matches labels containing the exact phrase within the quotes. For example, &quot;Type this only&quot; will return labels such as Use should type this only if needed or Type this only if required, but not Only type this.
</div>
<div class="mtps-row">
Label ID Matches labels containing the specified label ID. For example, @SYS1234* will return all labels starting with @SYS1234, such as @SYS12341, @SYS12342, and @SYS12343.
</div>
</div>
</div></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>Standard version control buttons will be available if version control is enabled.</P>



## Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Field</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>LabelId</strong></p></td>
<td><p>Unique label identification, for example @SYS12345.</p></td>
</tr>
<tr class="even">
<td><p><strong>Language</strong></p></td>
<td><p>Language of current label. You can only search for a label in one language.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Label</strong></p></td>
<td><p>Label text shown in the user interface.</p></td>
</tr>
<tr class="even">
<td><p><strong>Description</strong></p></td>
<td><p>Comment about a label that may be helpful to translators or to developers who are wondering whether they should reuse the label. Use a description to distinguish between labels with the same text string.</p></td>
</tr>
</tbody>
</table>


## See also

[How to: Create and Use Labels](how-to-create-and-use-labels.md)

[How to: Find a Label](how-to-find-a-label.md)

[How to: Create a Label File](how-to-create-a-label-file.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

