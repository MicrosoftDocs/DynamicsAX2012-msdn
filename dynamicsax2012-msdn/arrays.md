---
title: Arrays
TOCTitle: Arrays
ms:assetid: 69c2751b-418f-4683-bd31-f59652412545
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa653716(v=AX.60)
ms:contentKeyID: 35244783
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Arrays 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An array is a collection of variables that are all of the same type. The elements of an array are accessed with simple integer indexes. For example:

int myArray\[10\]; // Fixed-length array with 10 integers

myArray\[4\] = 1; // Accessing the 4th element in the array

You use a separate statement to initialize each element in an array.


> [!NOTE]
> <P>When you use a <A href="containers.md">Container</A> data type or an <A href="https://msdn.microsoft.com/en-us/library/gg802677(v=ax.60)">Array</A> object to create a collection, you can initialize multiple elements by using a single statement.</P>



There are three kinds of arrays:

  - Dynamic

  - Fixed-length

  - Partly on disk

X++ only supports one-dimensional arrays. It is possible, however, to mimic the behavior of [multiple array indices](multiple-array-indexes.md).


> [!NOTE]
> <P>Variables in objects and tables can be declared as arrays (this is used in address lines in the standard application).</P>
> <P>An <A href="collection-classes-in-microsoft-dynamics-ax.md">Array collection class</A> enables you to store objects in an array.</P>



## Declaring Arrays

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Array declaration</p></td>
<td><p>=</p></td>
<td><p>datatype Variable { , Variable } ;</p></td>
</tr>
<tr class="even">
<td><p>Variable</p></td>
<td><p>=</p></td>
<td><p>Identifier arrayoptions</p></td>
</tr>
<tr class="odd">
<td><p>Arrayoptions</p></td>
<td><p>=</p></td>
<td><p>[ [ Length ] [, Memory ] ]</p></td>
</tr>
</tbody>
</table>


If a Length is specified, the array is a fixed-length array with Length elements. Otherwise, it is a dynamic array.

If Memory is specified, it is a partly on disk array.

    static void Job1(Args _args)
    {
        // A dynamic array of integers
        int i[]; 
     
        // A fixed-length real array with 100 elements
        real r[100]; 
     
        // A dynamic array of dates with only 10 elements in memory
        date d[,10]; 
     
        // A fixed length array of NoYes variables with
        // 100 elements and 10 in memory
        NoYes ny[100,10];
        
        print "Done.";
        pause;
    }

## Array Indices

Array indexes begin at 1. The first item in the array is called \[1\], the second \[2\], and so on.

The syntax for accessing an array element is:

ArrayItemReference = ArrayVariable \[ Index \]

where ArrayVariable is the identifier of the array, and Index is the number of the array element. Index can be an integer expression.

For example, a\[9\] accesses item number 9 in array a.

In X++, item zero\[0\] is used to clear the array\! Assigning a value to index 0 in an array resets all elements in the array to the default value. For example,

intArray\[0\] = 0; //Resets all elements in intArray

## Dynamic Arrays

A dynamic array is declared with an empty array option (that is, only square brackets):

//Dynamic array of integers

int intArray\[\];

// Dynamic array of variables of type Datatype

Datatype arrayVariable\[\];

## Fixed-length Arrays

A fixed-length array can hold the number of items that is specified in the declaration. Fixed-length arrays are declared like dynamic arrays but with a length option in the square brackets:

boolean boolArray\[100\]; //Fixed-length array of booleans with 100 items

## Partly On Disk Arrays

Partly on disk arrays are declared either as dynamic or fixed-length arrays with an extra option that declares how many items should be held in memory. The other items are stored on disk and automatically loaded when referenced.

//Dynamic integer array with only 100 elements in memory.   
 int arrayVariable \[ ,100\];

//Fixed-length string array with 1000 elements, and only 200 in memory.   
 str arrayVariable \[1000,200\]

## See also

[Composite Data Types](composite-data-types.md)

[Multiple Array Indexes](multiple-array-indexes.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

