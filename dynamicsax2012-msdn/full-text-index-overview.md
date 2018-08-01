---
title: Full Text Index Overview
TOCTitle: Full Text Index Overview
ms:assetid: 02113fc1-5a01-4dd5-9a74-5a92ac2edcde
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg839860(v=AX.60)
ms:contentKeyID: 35240129
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Full Text Index Overview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A full text index contains location information about each significant word in a string field of a table. Some queries can use this information to run more efficiently and complete much sooner. These are queries that search for words that are embedded in the middle of string fields

A regular index on a long string field can help a query complete quickly only if the query searches for the word that is at the start of the string field. In X++ SQL this is done with the like keyword and the \* wildcard character, such as in the code phrase like "\*diamond\*".

## Related Topics

The following topics provide information about creating and using full text indexes.

  - [How to: Create a Full Text Index](how-to-create-a-full-text-index.md)

  - [How to: Use a Full Text Index](how-to-use-a-full-text-index.md)

## Features and Background Information of Full Text Search

The following table shows features and gives background details about full text indexes, and about the full text searches that use these indexes.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Features</p></th>
<th><p>Background Details</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft SQL Server keywords.</p></td>
<td><p>The full text index feature of Microsoft Dynamics AX relies on the underlying database management software to implement the feature. The keyword FreeText is sent to the underlying SQL Server database system.</p></td>
</tr>
<tr class="even">
<td><p>Space characters are treated as implicit Boolean OR operators.</p></td>
<td><p>There is a space character in the string parameter in call queryBRange4.value(&quot;diamond unfounded&quot;);. The space between diamond and unfounded is interpreted as a Boolean OR.</p></td>
</tr>
<tr class="odd">
<td><p>Stemming is supported.</p></td>
<td><p>The Microsoft Dynamics AX system relies on the underlying database management product for stemming functionality when you issue a query that uses a full text index. A stemmer generates a variety of inflectional forms of a word to increase the chance for a match.</p>
<p>Stemmers are specific to each language. For example, the stemmer for English cannot be used for German. In English, if the stemmer is given the word talk, it would generate similar words like talks, talked, and talking. For more information, see the documentation for your database management product, such as Oracle or Microsoft SQL Server.</p></td>
</tr>
<tr class="even">
<td><p>Word breaking is supported.</p></td>
<td><p>The Microsoft Dynamics AX system relies on the underlying database management product for word breaker functionality when you insert data into a field that is part of a full text index. In English, if a word breaker is given website, it would generate the words web and site.</p>
<p>For more information, see the documentation for your database management product, such as Oracle or Microsoft SQL Server.</p></td>
</tr>
<tr class="odd">
<td><p>No wildcards are available.</p></td>
<td><p>There are no wildcard characters available for full text search. The * and ? wildcards that are available with the X++ like keyword are not available for full text search.</p></td>
</tr>
<tr class="even">
<td><p><strong>TableGroup</strong> property.</p></td>
<td><p>A table can have a full text index only if the <strong>TableGroup</strong> property is set to <strong>Main</strong> or <strong>Group</strong> on the table.</p></td>
</tr>
<tr class="odd">
<td><p>Maximum of one full text index per table.</p></td>
<td><p>You can create a maximum of one full text index per table.</p></td>
</tr>
<tr class="even">
<td><p>Supported field types.</p></td>
<td><p>You can have multiple columns of type <strong>String</strong> in a single full text index. Also, the <strong>StringSize</strong> property of the string field can be set to a number or to <strong>(Memo)</strong>.</p></td>
</tr>
</tbody>
</table>


## See also

[Indexes and Keys](indexes-and-keys.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

