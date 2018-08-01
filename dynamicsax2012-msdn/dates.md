---
title: Dates
TOCTitle: Dates
ms:assetid: c3e40f87-50a3-4d7c-8226-104c3e9d3789
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa865135(v=AX.60)
ms:contentKeyID: 35251094
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Dates [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The date data type holds a complete date; that is, day, month, and year.

## Scope and Precision

The date data type can hold dates in the closed interval \[1\\1\\1900; 31\\12\\2154\], that is: between January 1, 1900, and December 31, 2154.

## Declaring Dates

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Date declaration</p></td>
<td><p>=</p></td>
<td><p>date Variable { , Variable } ;</p></td>
</tr>
<tr class="even">
<td><p>Variable</p></td>
<td><p>=</p></td>
<td><p>Identifier [ option ]</p></td>
</tr>
<tr class="odd">
<td><p>Option</p></td>
<td><p>=</p></td>
<td><p><a href="arrays.md">arrayoptions</a> | initialization</p></td>
</tr>
</tbody>
</table>


```X++
    //Simple declaration of a date variable, d
    date d; 
    //Multiple declaration of two date variables
    date d1, d2;
    //A date variable, d3, is initialized to the 21st of November 1998
    date d3 = 21\11\1998;
    //Declaration of a dynamic array of dates
    date d4[]; 
```

## Date Literals

Dates can be written as literals in X++ by using the syntax:

```X++
Date literal = day \ month \ year
```

You must use four digits for the year.

## Automatic Conversion

Dates are not automatically converted into other types, but you can use integer values in the computation of dates. For example:

```X++
void myMethod()
    {
        int anInteger;
        date aDate;
        ;
        // Sets the date variable adate to January 1, 1998
        aDate = 1\1\1998;
    
        // Sets the integer variable anInteger to 30.
        anInteger = 30;
    
        // Sets aDate to aDate + 30; that is the 31st of January 1998
        aDate = aDate + anInteger;
    }
```

## Using Dates in Expressions

You can use dates in additions and subtractions when you are using the date as the principal type; that is, if you are subtracting from or adding to a date, like this:

date = date - integer or date = date + integer

You can also subtract two dates, and you can use dates in relational expressions.

## Overview of Dates

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Keyword</p></td>
<td><p>date</p></td>
</tr>
<tr class="even">
<td><p>Size of data type</p></td>
<td><p>32 bits</p></td>
</tr>
<tr class="odd">
<td><p>Scope of data type</p></td>
<td><p>[1\1\1900; 31\12\2154]</p></td>
</tr>
<tr class="even">
<td><p>Default value</p></td>
<td><p>The default is the minimum value of 1\1\1900. The minimum value is treated as null by X++ SQL statements.</p></td>
</tr>
<tr class="odd">
<td><p>Implicit conversions</p></td>
<td><p>None</p></td>
</tr>
<tr class="even">
<td><p>Explicit conversions</p></td>
<td><p>str2date, date2str, date2num, int2date</p></td>
</tr>
</tbody>
</table>


## See also

[Data Types in X++](data-types-in-x.md)

[Variables](variables.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

