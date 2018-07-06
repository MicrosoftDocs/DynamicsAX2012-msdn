---
title: Containers
TOCTitle: Containers
ms:assetid: d8acecc2-36ab-4b51-adcb-3a5c7d111091
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa874816(v=AX.60)
ms:contentKeyID: 35252069
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Containers 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In X++, container is one of the primitive types, or value types. container is not a class. A container contains an ordered sequence of primitive values or other containers.

A container can be stored in the database. container is one of the column types that you can select when you use the Application Object Tree (AOT) to add a column to a table.

A container slightly resembles an array, or collections such as the List or Stack classes. However, you can never change the size or content of a container after the container is created. X++ statements that appear to modify a container are internally building a new container and copying values as necessary. Even an assignment of a container to another container variable creates a new copy of the container. All of this has performance implications.

In the X++ functions that provide access to a container (such as conPeek), the container is 1 based not 0 based. Indexing is 1 based for arrays, and for everything else in X++.

## Syntax

This section describes the X++ syntax you must use to handle a container.

### ![Aa874816.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874816.collapse_all(en-us,AX.60).gif")Operators

The following table shows the X++ operators that can be applied to the container type.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Operator</p></th>
<th><p>Example</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>=</p></td>
<td><p>myContainer2 = [2, &quot;apple&quot;];</p>
<p></p>
<p>myContainer33 = [33, &quot;grape&quot;];</p>
<p></p>
<p>myContainer2 = myContainer33;</p></td>
<td><p>The example initializes myContainer2 and myContainer33.</p>
<p>Next, it makes a copy of myContainer33, and assigns the copy to myContainer2.</p>
<p>The container that myContainer2 had been holding is no longer available (and cannot be recovered).</p></td>
</tr>
<tr class="even">
<td><p>+=</p></td>
<td><p>myContainer33 += [34, &quot;banana&quot;];</p></td>
<td><p>Builds a new container and assigns it to myContainer33. The new container is populated by appending the assigned elements to those in the original myContainer33.</p>
<p>The original myContainer33 is no longer available.</p></td>
</tr>
</tbody>
</table>


### ![Aa874816.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874816.collapse_all(en-us,AX.60).gif")Statements

The following table displays the syntax of statements that handle a container.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Action</p></th>
<th><p>Example</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Declare a container</p></td>
<td><p>container cr3;</p></td>
</tr>
<tr class="even">
<td><p>Assign a literal container to a container variable</p></td>
<td><p>cr3 = [22, &quot;blue&quot;];</p></td>
</tr>
<tr class="odd">
<td><p>Declare and assign a container</p></td>
<td><p>container cr2 = [1, &quot;blue&quot;, true];</p></td>
</tr>
<tr class="even">
<td><p>Mimic container modification (implicitly creates a copy)</p></td>
<td><p>cr3 += [16, strMyColorString];</p>
<p>cr3 = conIns(cr3, 1, 3.14);</p>
<p>cr3 = conPoke(cr3, 2, &quot;violet&quot;);</p></td>
</tr>
<tr class="odd">
<td><p>Assignment of a container (implicitly creates a copy)</p></td>
<td><p>cr2 = cr3;</p></td>
</tr>
<tr class="even">
<td><p>Read a value from the container</p></td>
<td><p>myStr = conPeek(cr2, 1);</p></td>
</tr>
<tr class="odd">
<td><p>One statement that does multiple assignments from a container</p></td>
<td><p>str myStr;</p>
<p>int myInt;</p>
<p>container cr4 = [&quot;Hello&quot;, 22, 20\07\1988];</p>
<p>;</p>
<p>[myStr, myInt] = cr4; // &quot;Hello&quot;, 22</p></td>
</tr>
</tbody>
</table>


### ![Aa874816.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874816.collapse_all(en-us,AX.60).gif")Functions

There are several intrinsic X++ functions for handling a container, such as conIns and conPeek. For more information about the intrinsic X++ functions for handling a container, see [Functions for Manipulating Container Content](functions-for-manipulating-container-content.md).

The [Global Class](https://msdn.microsoft.com/en-us/library/gg836018\(v=ax.60\)) has static methods for handling containers. Among those methods are the following:

  - con2ArraySource

  - con2Buf

  - con2List

  - con2Str

  - containerFromXmlNode

  - conView

  - str2Con

## Container is a Value Type, not a Reference Type

Any class is a reference type. But container is a value type. Variables declared as value types are never null. Even the X++ function conNull returns a container. A variable declared as a container is automatically initialized to an empty container (a container that contains no values).

There are two code samples in the following table. In only the List class sample do variable2 and variable33 refer to the same thing (the same List object). In the container sample, the two variables hold different containers.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>container</p></th>
<th><p>List class</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>
```X++
static void JobC(Args _args)
{
    container variable2
        ,variable33;
    ;
    variable2 += [98];
    variable33 = variable2;
    variable2 += [97];
}
```
</td>
<td>
```X++
static void JobL(Args _args)
{
    List variable2
        ,variable33;
    ;
    variable2 = new List
        (Type::Integer);
    variable2.addEnd(98);
    variable33 = variable2;
    variable2.addEnd(97);
}
```
</td>
</tr>
</tbody>
</table>


## Containers are Immutable

Some X++ statements with containers might appear like they modify a container, but inside the system this never occurs. Instead, the data from the original container is combined with data from the command to build a new container.

You create a new container every time that you call any of the following functions:

  - conDel

  - conIns

  - conPoke

The following statements all create a new container:

  - myContainer = \[1\];

  - myContainer += \[2\];

  - myContainer4 = myContainer5;

## Automatic Type Conversions by Anytype

The X++ function conPeek returns an anytype type. The flexibility of anytype makes container a good way to store values of different types together. This makes it easier to read the values from a container when you do not know what type each value is. An anytype can be assigned to any X++ value type, as long as the value can be converted.

The automatic conversion by anytype also applies to the special syntax for making multiple assignments from a container in one statement. This is shown in the following code example, which assigns a str to an int, and an int to a str.
```X++  
    static void JobContainerMultiAssignmentUsesAnytype(Args _args)
    {
        container con2;
        int int4;
        str str7;
    
        con2 = ["11", 222];
        [int4, str7] = con2;
        info(strfmt("int4==11==(%1), str7==222==(%2)"
            , int4, str7));
    }
    /***  Pasted from output:
    Message (10:36:22 am)
    int4==11==(11), str7==222==(222)
    ***/
```
Your code is easier to read when it avoids implicit data type conversions. Assign values from a container to the same data type that was used to put the value into the container.

You must not assign a container to an anytype, because the system is unable to determine the correct conversions in some cases. In these cases, unexpected behavior or errors might occur.

## Performance of Containers

A container is best suited for processes that do not involve excessive modification to the size or contents of the container. When a container undergoes excessive additions of data, overall system performance can be decreased by the need to repeatedly copy container data and allocate new space.

### ![Aa874816.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874816.collapse_all(en-us,AX.60).gif")+= is Faster Than conIns

When you want to build a new container by appending new data, you can use either the += operator or the conIns function. The += operator is the faster alternative. Use the conIns function only when you want to add new data before the last index of the original data.

## Comparing container to other Options

The container type slightly resembles other constructs, such as arrays and collection classes like List and Stack. The next sections compare and contrast container with these other options.

### ![Aa874816.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874816.collapse_all(en-us,AX.60).gif")Differences Between container and List

An instance of the List class is mutable. A List object first allocates more space than its data consumes. As data is added the space is filled. This is more efficient than allocating more space every time that an element is added. Updating a List performs faster than similar operations on a container.

When you construct a List object, you determine the one type of data that the List object can store. This restriction is less flexible than for a container. However, you can choose to store objects in a List, whereas a container can only store value types.


> [!NOTE]
> <P>For more information about X++ data types, see <A href="data-types-in-x.md">Data Types in X++</A>.</P>



### ![Aa874816.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874816.collapse_all(en-us,AX.60).gif")Differences Between container and an Array

An array can hold only items of its declared type.

You can allocate memory space for an array and fill that space with values later, such as in a loop. This is efficient and performs well.

## Summary

A container is helpful when you must pass a variety of value types between the client and server tiers.

A container is a poor choice when you intend to repeatedly add to a list in a loop.

## See also

[Arrays](arrays.md)

[Array Class](https://msdn.microsoft.com/en-us/library/gg802677\(v=ax.60\))

[List Class](https://msdn.microsoft.com/en-us/library/gg921795\(v=ax.60\))

[Stack Class](https://msdn.microsoft.com/en-us/library/gg911264\(v=ax.60\))

[Struct Class](https://msdn.microsoft.com/en-us/library/gg926473\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

