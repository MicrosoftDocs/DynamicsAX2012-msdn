---
title: Booleans
TOCTitle: Booleans
ms:assetid: 8c1a66c5-dfdd-452c-ad2f-bdb08ad53655
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa659760(v=AX.60)
ms:contentKeyID: 35246387
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Booleans [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The boolean data type contains a value that evaluates to either true or false. You can use the X++ reserved literals true and false where ever a Boolean expression is expected.

Boolean expressions are also named logical expressions.

## Boolean Values are Represented as Integers

In X++ the internal representation of a boolean is an integer. You can assign any integer value to a variable declared of type boolean. The integer value 0 (zero) evaluates to false, and all others evaluate to true.

The X++ literal false is the integer value 0, and true is 1.

The following table lists several expressions and indicates whether they evaluate to true or false.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Expression</p></th>
<th><p>Boolean value</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>44</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>true</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>(false == 0)</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>(true == 1)</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>(true == 8)</p></td>
<td><p>False</p></td>
</tr>
<tr class="odd">
<td><p>false</p></td>
<td><p>False</p></td>
</tr>
<tr class="even">
<td><p>0</p></td>
<td><p>False</p></td>
</tr>
</tbody>
</table>


## Declaring Booleans

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Boolean declaration</p></td>
<td><p>=</p></td>
<td><p>boolean variable { , variable } ;</p></td>
</tr>
<tr class="even">
<td><p>variable</p></td>
<td><p>=</p></td>
<td><p>identifier [ option ]</p></td>
</tr>
<tr class="odd">
<td><p>option</p></td>
<td><p>=</p></td>
<td><p><a href="arrays.md">Arrayoptions</a> | initialization</p></td>
</tr>
</tbody>
</table>

```X++  
    // Simple declaration of a boolean variable, b
    boolean b; 
     
    // Multiple declaration
    boolean b1,b2;
     
    // Boolean variable is initialized to true 
    boolean b3 = true; 
     
    // Declares a dynamic array of Booleans
    boolean b4[]; 
```
## Automatic Conversions

Because the internal representation of a boolean is an integer, boolean values are automatically converted into integers and reals.

## Using Booleans in Expressions

You usually use Booleans in conditional statements, or as parts or results of logical expressions. The following example shows both.
```X++  
    void main()
    {
        //Declares a boolean called exprValue
        boolean exprValue; 
     
        //Assigns ExprValue the truth value of (7*6 == 42)
        exprValue = (7*6 == 42);
        ;
     
        if (exprValue)
        { 
            print "OK";
        } 
    }
```
Here, the variable exprValue contains the value true, because 7\*6 is equal to 42; so, the expression is true. The conditional statement is true; the word "OK" is displayed on the screen.

## Overview of Booleans

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Keyword</p></td>
<td><p>boolean</p></td>
</tr>
<tr class="even">
<td><p>Size of data type</p></td>
<td><p>Byte</p></td>
</tr>
<tr class="odd">
<td><p>Scope of data type</p></td>
<td><p>false (0) and true (1)</p></td>
</tr>
<tr class="even">
<td><p>Default value</p></td>
<td><p>false</p></td>
</tr>
<tr class="odd">
<td><p>Implicit conversions</p></td>
<td><p>Automatically converted to int, date, and real</p></td>
</tr>
<tr class="even">
<td><p>Explicit conversions</p></td>
<td><p>none</p></td>
</tr>
</tbody>
</table>


## See also

[Data Types in X++](data-types-in-x.md)

[Variables](variables.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

