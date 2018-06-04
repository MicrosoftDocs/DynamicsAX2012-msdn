---
title: Integers
TOCTitle: Integers
ms:assetid: a7ab2d52-b962-47cc-8d29-d6401b8b9241
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa851966(v=AX.60)
ms:contentKeyID: 35248478
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Integers 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Integers are numbers without decimals. X++ has two integer types:

  - int, which is 32 bits wide

  - int64, which is 64 bits wide

Integers are used especially as control variables in repetitive statements or as indexes in arrays.

## Range and Precision

The range of an int is: \[-2,147,483,647 : 2,147,483,647\].

The range of an int64 is: \[-9,223,372,036,854,775,808 : 9,223,372,036,854,775,808\]

## Declaring Integers

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>integer declaration</p></td>
<td><p>=</p></td>
<td><p>int | int64 Variable { , Variable } ;</p></td>
</tr>
<tr class="even">
<td><p>variable</p></td>
<td><p>=</p></td>
<td><p>identifier [ option ]</p></td>
</tr>
<tr class="odd">
<td><p>option</p></td>
<td><p>=</p></td>
<td><p><a href="arrays.md">arrayoptions</a> | <a href="declaration-of-variables.md">initialization</a></p></td>
</tr>
</tbody>
</table>


    // Declaration of an integer variable, i
    int i;
    // Declaration of two int64 variables
    int64 i1, i2;
    // An integer variable is initialized to the value 100
    int i3 = 100;
    // Declaration of a dynamic array of integers
    int i4[];


> [!WARNING]
> <P>If you try to assign the largest integer plus 1 to an int64, you will get the wrong result. This is because it is interpreted as a 32-bit number, and therefore the number is wrapped round and stored as -2,147,483,647 instead. To prevent this, add a "u" to the end of the number, for example: int64 i = 0x8000 0000u (0x8000 0000 is 2,147,483,648).</P>



## Integer Literals

You can use integer literals anywhere an integer-expression is expected. An integer literal is the integer written directly in the code—for instance, 32768. The range for integers is shown previously, and all integers in this range can be used as literals in X++.

## Automatic Conversions

Integers are automatically converted into boolean, enum, and real.

## Using Integers in Expressions

Integers can be used in all expressions, and relational operators and arithmetic operators can be applied. For example:

    void element() 
    {
        // Two integer variables are declared and initialized
        int i = 1, j = 2;
        ;
     
        // j is assigned the result of j + ((i + i) DIV 2)
        j +=(i + i) div 2;
     
        // This results in: j=3
        if (j>2)
        { 
            print "J is greater than 2";
        }
        else 
        {
            print "J is NOT greater than 2";
        }
    }

## Overview of Integers

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Keywords</p></td>
<td><p>int, int64</p></td>
</tr>
<tr class="even">
<td><p>Size</p></td>
<td><p>32 bits or 64 bits</p></td>
</tr>
<tr class="odd">
<td><p>Scope of data type</p></td>
<td><p>[-2,147,483,648 : 2,147,483,647] or</p>
<p>[-9,223,372,036,854,775,808 : 9,223,372,036,854,775,808]</p></td>
</tr>
<tr class="even">
<td><p>Default value</p></td>
<td><p>0</p></td>
</tr>
<tr class="odd">
<td><p>Implicit conversions</p></td>
<td><p>Automatically converted to real, boolean, and enum</p></td>
</tr>
<tr class="even">
<td><p>Explicit conversions</p></td>
<td><p>str2int, int2str, str2int64, int642str</p></td>
</tr>
</tbody>
</table>


## See also

[Data Types in X++](data-types-in-x.md)

[Variables](variables.md)

[str2Int Function](https://msdn.microsoft.com/en-us/library/aa845181\(v=ax.60\))

[int2Str Function](https://msdn.microsoft.com/en-us/library/aa851371\(v=ax.60\))

[str2Int64 Function](https://msdn.microsoft.com/en-us/library/aa882138\(v=ax.60\))

[int642Str Function](https://msdn.microsoft.com/en-us/library/aa619939\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

