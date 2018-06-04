---
title: 'X++, C# Comparison: Collections'
TOCTitle: 'X++, C# Comparison: Collections'
ms:assetid: f024bf98-baf3-4891-9d0a-d00ef403bc22
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967436(v=AX.60)
ms:contentKeyID: 35253316
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++, C\# Comparison: Collections 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX provides the X++ List collection class. The .NET Framework that is used in C\# has a similar class named System.Collections.Generic.List.

## Comparing the Use of the List Classes

The following table compares methods on the X++ List class to the methods on System.Collections.Generic.List from the .NET Framework and C\#.

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
<th><p>Discussion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Declaration of collection</p></td>
<td><p>List myList;</p></td>
<td><p>List&lt;string&gt; myList;</p></td>
<td><p>The X++ declaration does not include the type of elements to be stored.</p></td>
</tr>
<tr class="even">
<td><p>Declaration of iterator</p></td>
<td><ul>
<li><p>ListIterator iter;</p></li>
<li><p>ListEnumerator enumer;</p></li>
</ul></td>
<td><p>IEnumerator&lt;string&gt; iter;</p></td>
<td><p>In X++ the ListIterator object has methods that can insert and delete items from the List. The X++ ListEnumerator cannot modify the contents of the List.</p>
<p>In X++ the ListEnumerator object is always created on the same tier as the List. This is not always true for ListIterator.</p></td>
</tr>
<tr class="odd">
<td><p>Obtaining an iterator</p></td>
<td><ul>
<li><p>new ListIterator (myList)</p></li>
<li><p>myList.getEnumerator()</p></li>
</ul></td>
<td><p>myList.GetEnumerator()</p></td>
<td><p>In both X++ and C#, the List object has a getter method for an associated enumerator.</p></td>
</tr>
<tr class="even">
<td><p>Constructor</p></td>
<td><p>new List(Types::String)</p></td>
<td><p>new List&lt;string&gt;()</p></td>
<td><p>Information about the type of objects to be stored inside the List classes is given to the constructor in both X++ and C#.</p></td>
</tr>
<tr class="odd">
<td><p>Updating data</p></td>
<td><ul>
<li><p>Enumerator – the enumerator becomes invalid if any items in the List are added or removed.</p></li>
<li><p>Iterator – the iterator has methods that insert and delete items from the List. The iterator remains valid.</p></li>
</ul></td>
<td><p>Enumerator – the enumerator becomes invalid if any items in the List are added or removed.</p></td>
<td><p>Enumerators become invalid after items are added or deleted from the List, in both X++ and C#.</p></td>
</tr>
<tr class="even">
<td><p>Updating data</p></td>
<td><p>In X++ the List class has methods for adding items at the start or end of the list.</p></td>
<td><p>In C# the List class has methods for adding members at any position in the list. It also has methods for removing items from any position.</p></td>
<td><p>In X++ items can be removed from the List only by an iterator.</p></td>
</tr>
</tbody>
</table>


## Example 1: Declaration of a List

The following table displays code examples in X++ and C\# that declare List collections.

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
<td><p>List listStrings ,list2 ,listMerged;</p>
<p></p>
<p>ListIterator literator;</p></td>
<td><p>using System;</p>
<p>using SysCollGen = System.Collections.Generic;</p>
<p></p>
<p>SysCollGen.List&lt;string&gt; listStrings ,list2 ,listMerged;</p>
<p></p>
<p>SysCollGen.IEnumerator&lt;string&gt; literator;</p></td>
</tr>
</tbody>
</table>


## Example 2: Construction of a List

In both languages, the type of items that the collection stores must be specified at the time of construction. For class types, X++ can get no more specific than whether the type is a class (Types::Class). Code examples are in the following table.

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
<td><p>listStrings = new List( Types::String );</p></td>
<td><p>listStrings = new SysCollGen.List&lt;string&gt;();</p></td>
</tr>
</tbody>
</table>


## Example 3: Add Items to a List

In both X++ and C\#, the collection provides a method for appending an item to the end of the collection, and for inserting an item the start.

In C\# the collection provides a method for inserting at any point in the collection based on an index value. In X++ a collection iterator can insert an item at its current position.

Code examples are in the following table.

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
<td><p>listStrings.addEnd (&quot;String_BB.&quot;);</p>
<p></p>
<p>listStrings.addStart (&quot;String_AA.&quot;);</p></td>
<td><p>listStrings.Add (&quot;String_BB.&quot;);</p>
<p></p>
<p>listStrings.Insert (0 ,&quot;String_AA.&quot;);</p></td>
</tr>
<tr class="even">
<td><p>// Iterator performs a midpoint</p>
<p>// insert at current position.</p>
<p>listIterator.insert (&quot;dog&quot;);</p></td>
<td><p>// Index 7 determines the insertion point.</p>
<p>listStrings.Insert (7 ,&quot;dog&quot;);</p></td>
</tr>
</tbody>
</table>


## Example 4: Iterate Through a List

Both X++ and C\# have iterator classes that you can use to step through the items in a collection. Code examples are in the following table.

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
<td><p>literator = new ListIterator</p>
<p>(listStrings);</p>
<p>// Now the iterator points at the first item.</p></td>
<td><p>literator = listStrings</p>
<p>.GetEnumerator();</p>
<p>// Now enumerator points before</p>
<p>// the first item, not at</p>
<p>// the first item.</p></td>
</tr>
<tr class="even">
<td><p>// The more method answers whether</p>
<p>// the iterator currently points</p>
<p>// at an item.</p>
<p>while (literator.more())</p>
<p>{</p>
<p>info(any2str</p>
<p>(literator.value()));</p>
<p>literator.next();</p>
<p>}</p></td>
<td><p>// The MoveNext method both</p>
<p>// advances the item pointer, and</p>
<p>// answers whether the pointer is</p>
<p>// pointing at an item.</p>
<p>while (literator.MoveNext())</p>
<p>{</p>
<p>Console.WriteLine (literator.Current);</p>
<p>}</p></td>
</tr>
</tbody>
</table>


## Example 4b: foreach in C\#

In C\# the foreach keyword is often used to simplify the task of iterating through a list. The following code example behaves the same as the previous C\# example.

foreach (string currentString in listStrings)

{

Console.WriteLine(currentString);

}

## Example 5: Delete the Second Item

The following table contains code examples that delete the second item from the collection. In X++ this requires an iterator. In C\# the collection itself provides the method for removing an item.

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
<td><p>literator.begin();</p>
<p>literator.next();</p>
<p>literator.delete();</p></td>
<td><p>listStrings.RemoveAt(1);</p></td>
</tr>
</tbody>
</table>


## Example 6: Combine Two Collections

The following table contains code examples that combine the contents of two collections into one.

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
<td><p>listStrings = List::merge</p>
<p>(listStrings ,listStr3);</p>
<p>// Or use the .appendList method:</p>
<p>listStrings.appendList (listStr3);</p></td>
<td><p>listStrings.InsertRange</p>
<p>(listStrings.Count ,listStr3);</p></td>
</tr>
</tbody>
</table>


## See also

[X++, C\# Comparisons](x-csharp-comparisons.md)

[Arrays](arrays.md)

[Containers](containers.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

