---
title: 'X++, C# Comparison: Collections of Keys with Values'
TOCTitle: 'X++, C# Comparison: Collections of Keys with Values'
ms:assetid: 977f7758-920a-410d-9dfa-011d568b48c2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967409(v=AX.60)
ms:contentKeyID: 35247779
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++, C\# Comparison: Collections of Keys with Values 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX provides the Map collection class. The Map collection holds pairs of values, the key value plus a data value. This resembles the .NET Framework class named System.Collections.Generic.Dictionary.

## X++ to C\# Comparisons

There are similarities and differences in how a key-value collection is implemented in X++ and C\#.

### ![Cc967409.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967409.collapse_all(en-us,AX.60).gif")Similarities

The following list describes similarities between X++ and C\# regarding their collections that store key-value pairs:

  - Both prevent duplicate keys.

  - Both use an enumerator (or iterator) to loop through the items.

  - Both key-value collection objects are constructed with designations of the types that are stored as key and value.

  - Both can store class objects, and are not limited to storing primitives like int.

### ![Cc967409.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967409.collapse_all(en-us,AX.60).gif")Differences

The following table describes differences between X++ and C\# regarding their collections classes that store key-value pairs:

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Feature</p></th>
<th><p>X++</p></th>
<th><p>C#</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Duplicate keys</p></td>
<td><p>In X++ the Map class prevents duplicate keys by implicitly treating your call to its insert method as an operation to update only the value associated with the key.</p></td>
<td><p>In C# the Dictionary class throws an exception when you try to add a duplicate key.</p></td>
<td><p>Duplicate keys are prevented in both languages, although by different techniques.</p></td>
</tr>
<tr class="even">
<td><p>Delete items</p></td>
<td><p>In X++ the delete method on an iterator object is used to remove an unwanted key-value pair from a Map.</p></td>
<td><p>In C# the Dictionary class has a remove method.</p></td>
<td><p>In both languages, an enumerator is made invalid if the collection item count is modified during the life of the enumerator.</p></td>
</tr>
</tbody>
</table>


## Example 1: Declaration of a Key-Value Collection

In both languages, the type of items that the key-value collection stores must be specified. In X++ the type is specified at time of construction. In C\# the type is specified at both the time of declaration and the time of construction. Code examples are in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++</p></th>
<th><p>C#</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Map mapKeyValue;</p>
<p></p>
<p>MapEnumerator enumer;</p>
<p></p>
<p>MapIterator mapIter;</p></td>
<td><p>SysCollGen.Dictionary</p>
<p>&lt;int,string&gt;</p>
<p>dictKeyValue;</p>
<p></p>
<p>SysCollGen.IEnumerator</p>
<p>&lt;SysCollGen.KeyValuePair</p>
<p>&lt;int,string&gt;&gt; enumer;</p>
<p></p>
<p>SysCollGen.KeyValuePair</p>
<p>&lt;int,string&gt;</p>
<p>kvpCurrentKeyValuePair;</p></td>
</tr>
</tbody>
</table>


## Example 2: Construction of the Collection

In both languages, the type of items that the key-value collection stores specified during construction. For class types, X++ can get no more specific than whether the type is a class (Types::Class). Code examples are in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++</p></th>
<th><p>C#</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>mapKeyValue =</p>
<p>new Map</p>
<p>(Types::Integer</p>
<p>,Types::String);</p></td>
<td><p>dictKeyValue = new</p>
<p>SysCollGen.Dictionary</p>
<p>&lt;int,string&gt;();</p></td>
</tr>
</tbody>
</table>


## Example 3: Add an Item to the Collection

There is almost no difference in how an item is added to a key-value collection, in X++ and C\#. Code examples are in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++</p></th>
<th><p>C#</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>mapKeyValue.insert</p>
<p>(xx ,int2str(xx)</p>
<p>+ &quot;_Value&quot;);</p></td>
<td><p>dictKeyValue.Add</p>
<p>(xx ,xx.ToString()</p>
<p>+ &quot;_Value&quot;);</p></td>
</tr>
</tbody>
</table>


## Example 4: Iterate Through a Key-Value Collection

Enumerators are used to loop through the key-value collections in both X++ and C\#. Code examples are in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++</p></th>
<th><p>C#</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>enumer = mapKeyValue.getEnumerator();</p>
<p>while (enumer.moveNext())</p>
<p>{</p>
<p>iCurrentKey = enumer.currentKey();</p>
<p>sCurrentValue = enumer.currentValue();</p>
<p>// Display key and value here.</p>
<p>}</p></td>
<td><p>enumer = dictKeyValue</p>
<p>.GetEnumerator();</p>
<p>while (enumer.MoveNext())</p>
<p>{</p>
<p>kvpCurrentKeyValuePair = enumer.Current;</p>
<p>// Display .Key and .Value properties</p>
<p>// of kvpCurrentKeyValuePair here.</p>
<p>}</p></td>
</tr>
</tbody>
</table>


## Example 5: Update the Value Associated with a Key

The syntax is very different between the two languages for an update of the value associated to a given key. Code examples for the key 102 are in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++</p></th>
<th><p>C#</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>mapKeyValue.insert</p>
<p>(102 ,&quot;.insert(), Re-inserted&quot;</p>
<p>+ &quot; key 102 with a different value.&quot;);</p></td>
<td><p>dictKeyValue[102] =</p>
<p>&quot;The semi-hidden .item property&quot;</p>
<p>+ &quot; in C#, Updated the value for key 102.&quot;;</p></td>
</tr>
</tbody>
</table>


## Example 6: Delete One Item

The syntax is very different between the two languages to delete one key-value pair from a collection, while iterating through the collection members. Code examples for the key 102 are in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++</p></th>
<th><p>C#</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>mapIter = new MapIterator</p>
<p>(mapKeyValue);</p>
<p>//mapIter.begin();</p>
<p>while (mapIter.more())</p>
<p>{</p>
<p>iCurrentKey = mapIter.key();</p>
<p>if (104 == iCurrentKey)</p>
<p>{</p>
<p>// mapKeyValue.remove would invalidate the iterator.</p>
<p>mapIter.delete();</p>
<p>break;</p>
<p>}</p>
<p>mapIter.next();</p>
<p>}</p></td>
<td><p>dictKeyValue</p>
<p>.Remove(104);</p></td>
</tr>
</tbody>
</table>


## See also

[X++, C\# Comparisons](x-csharp-comparisons.md)

[X++, C\# Comparison: Collections](x-csharp-comparison-collections.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

