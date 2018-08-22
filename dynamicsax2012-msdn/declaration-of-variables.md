---
title: Declaration of Variables
TOCTitle: Declaration of Variables
ms:assetid: 13ede7fb-b279-4003-adc1-cfcfdccefcf9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa598112(v=AX.60)
ms:contentKeyID: 35240598
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Declaration of Variables 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

All variables must be declared before they can be used. X++ does not allow variable declarations to be mixed with other X++ statements; variables must be declared before X++ statements.

The syntax for the declaration of each variable type is described in the help topics for the [Primitive Data Types](primitive-data-types.md) and [Composite Data Types](composite-data-types.md).

When a variable is declared, memory is also allocated and the variable is initialized to the default value. The only exception to this is for objects, where you need to manually allocate memory by using the new method. For more information, see [Classes as Data Types](classes-as-data-types.md).

## Declaration With Initialization

At times you might want a variable to have a value other than the default as soon as the variable is declared. X++ allows you to initialize variables in the declaration by adding an assignment statement:

// Assigns value of pi to 12 significant digits

Real pi = 3.14159265359;

Another syntax is needed to initialize objects because they are initialized by invoking the new method on the class:

// Simple call to the new method in the Access class

Access accessObject = new Access();

## Multiple Declarations

X++ allows you to declare more than one variable in the same declaration statement. For example:

// Declares 2 integers, i and j

Int i,j;

// Declares array with 100 integers with 5 in memory and b as integer with value 1

Int a\[100,5\], b=1;

## Summary

The possible variable declarations in X++ are shown by using EBNF (Extended Backus Naur Form) grammar, in the following table:

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Declaration</p></td>
<td><p>=</p></td>
<td><p>Datatype Variable { , Variable } ;</p></td>
</tr>
<tr class="even">
<td><p>Datatype</p></td>
<td><p>=</p></td>
<td><p>boolean | int | real | date | str | container | typeidentifier</p></td>
</tr>
<tr class="odd">
<td><p>Variable</p></td>
<td><p>=</p></td>
<td><p>[ Typeoptions ] Identifier [ Option ]</p></td>
</tr>
<tr class="even">
<td><p>Typeoptions</p></td>
<td><p>=</p></td>
<td><p>[ Length ] [ left | right ]</p></td>
</tr>
<tr class="odd">
<td><p>Option</p></td>
<td><p>=</p></td>
<td><p>Arrayoption | Initialization</p></td>
</tr>
<tr class="even">
<td><p>Arrayoption</p></td>
<td><p>=</p></td>
<td><p>[ Length , Memory ]</p></td>
</tr>
<tr class="odd">
<td><p>Initialization</p></td>
<td><p>=</p></td>
<td><p><a href="expressions-syntax.md">expression</a></p></td>
</tr>
</tbody>
</table>


typeIdentifier can be a class, an extended data type, a table, a map, or an enumeration, which has been declared elsewhere. All of these are declared in the Application Object Tree.

Typeoptions are only valid for variables of type string.

Length is an integer (or expression) that specifies the maximum length of the string or array. If it is omitted, the string or array is dynamic.

Memory is an integer (or expression) that specifies how many array items should be held in memory. If it omitted, all items are held in memory.

## See also

[Composite Data Types](composite-data-types.md)

[Primitive Data Types](primitive-data-types.md)

[Variable Names](variable-names.md)

[Variable Scopes](variable-scopes.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

