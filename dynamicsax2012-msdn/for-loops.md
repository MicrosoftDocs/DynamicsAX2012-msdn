---
title: For Loops
TOCTitle: For Loops
ms:assetid: 4b8e2394-4b04-4d88-b8f7-dbb0685e6376
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa605438(v=AX.60)
ms:contentKeyID: 35243289
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# For Loops 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The for loop is very similar to the [while loop](while-loops.md), but has the following additions:

  - The initial value to a control variable can be assigned.

  - There is a statement for incrementing or decrementing the variable.

These additions make it especially useful for traversing lists, containers, and arrays because they have a fixed number of elements. You can also apply a statement to each element and increment your way through the elements, setting the condition to test for the last element.

## Syntax

The body of the for loop may be executed zero or more times according to the results of the condition test. Placeholders are enclosed in parentheses.

    for ( Initialization ; Test ; Increment ) 
    {
        Statement 
    }

## Example

Print all items in a fixed array called ra with 100 reals.

    int i; // Control variable.
    ;
    for (i=1; i<=100; i+=1)
    {
        print ra[i];
    }

## Comparison to while Loop

The previous example can also be written using a while loop.

    int i; // Control variable.
    ;
    i = 1;
    while (i <= 100)
    {
        print ra[i];
        i++;
    }

In general, there is a direct correspondence between for and while loops as shown in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>for loop</p></th>
<th><p>while loop</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>for (Init; Test; Incr)</p></td>
<td><p>{</p></td>
</tr>
<tr class="odd">
<td><p>{</p></td>
<td><p>Init;</p></td>
</tr>
<tr class="even">
<td><p>Body</p></td>
<td><p>while (Test)</p></td>
</tr>
<tr class="odd">
<td><p>}</p></td>
<td><p>{</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Body;</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Incr;</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>}</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>}</p></td>
</tr>
</tbody>
</table>


The two constructions shown in the previous table are exactly the same unless the Body contains a continue statement. In a for loop, continue moves in front of the increment. In a while loop, continue jumps to after the increment.

## See also

[Loops](loops.md)

[Conditional Statements](conditional-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

