---
title: Collection Classes in Microsoft Dynamics AX
TOCTitle: Collection Classes in Microsoft Dynamics AX
ms:assetid: 61195575-76c6-43ee-a193-8f8a3148fc69
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa608508(v=AX.60)
ms:contentKeyID: 35244523
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Collection Classes in Microsoft Dynamics AX [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The X++ language syntax provides two compound types: arrays and containers. They are useful for aggregating values of simpler types. However, you cannot store objects in arrays or containers. The Microsoft Dynamics AX collection classes have been designed for storing objects. The classes are implemented in C++ to achieve the maximum performance (they are system classes).


> [!NOTE]
> <P>Collection classes were formerly called Foundation classes.</P>



## Collection Classes

The collection classes are shown in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Class</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg802677(v=ax.60)">Array</a></p></td>
<td><p>Similar to the X++ language array type except that it can hold values of any single type, including objects and records. Objects are accessed in a specific order.</p>
<p>For more information, see <a href="x-csharp-comparison-array-syntax.md">X++, C# Comparison: Array Syntax</a>.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg921795(v=ax.60)">List</a></p></td>
<td><p>Contains elements that are accessed sequentially.</p>
<p>Unlike the Array class, the List class provides an addStart method.</p>
<p>As with the Set class, the List class provides methods getEnumerator and getIterator. You can use an iterator to insert and delete items from a List object.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg911868(v=ax.60)">Map</a></p></td>
<td><p>Associates a key value with another value.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg957720(v=ax.60)">Set</a></p></td>
<td><p>Holds values of any single type. Values are not stored in the sequence they are added. Instead, the Set object stores them in a manner that optimizes performance for the in method.</p>
<p>When you add a value to a Set object which is already storing that same value, the add attempt is ignored by the Set object.</p>
<p>Unlike the Array class, the Set class provides the methods in and remove.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg926473(v=ax.60)">Struct</a></p></td>
<td><p>Can contain values of more than one type. Used to group information about a specific entity.</p></td>
</tr>
</tbody>
</table>


### ![Aa608508.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa608508.collapse_all(en-us,AX.60).gif")Types Stored in Collections

The constructor for each collection class, except Struct, takes in a parameter value that is an element of the Types system enum. The collection instance can store items of that type only.

The Types::AnyType enum element is a special case and it cannot be used to construct a usable collection object, such as a Set object.

The null value cannot be stored as an element in a Set object. And null cannot be a key in a Map object.

### ![Aa608508.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa608508.collapse_all(en-us,AX.60).gif")Do Not Change Elements During Iteration

You can iterate through an X++ collection object with an iterator or enumerator. Here are typical examples of how you can obtain an iterator:

  - new MapIterator(myMap)

  - myMap.getEnumerator()

For Set objects, if any elements are added or removed after an iterator is created, the iterator instance can no longer be used to read from or step through the collection.

For Map objects, element removals invalidate the iterator just as for Set objects. However in Microsoft Dynamics AX 2012, a MapIterator object remains valid even after a call to the Map.insert method. This is true whether the key is new, or whether the key already exists and only the value is actually being updated in the Map element. X++ code that calls Map.insert and relies on the iterator object remaining valid might fail if run as .NET Framework CIL.

For more information, browse to the [MSDN blogs](http://blogs.msdn.com/) and search for the X++ blog post titled **Changes to the Collection Classes in Dynamics AX 2012**, or try this direct link to the [X++ Blog](http://blogs.msdn.com/b/x/).

### ![Aa608508.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa608508.collapse_all(en-us,AX.60).gif")Extend a Collection Class

You can use the collection classes to form more complex classes. For example, a stack might easily be implemented by using a list where the elements are always added to the start of the list. The newest element then occupies the top of the stack.

You can also extend the collection classes. For example, you might extend the List class to create a list of customer records where the operations could be made type safe. The derived collection class would accept only customer records, not just any record.

## See also

[Composite Data Types](composite-data-types.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

