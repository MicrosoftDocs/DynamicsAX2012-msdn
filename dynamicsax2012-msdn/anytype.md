---
title: Anytype
TOCTitle: Anytype
ms:assetid: aa1a8f04-d33b-4d53-90e1-9d366fa91b1a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa853001(v=AX.60)
ms:contentKeyID: 35249537
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Anytype [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The anytype data type is a placeholder for any data type. Variables of type should only be used as arguments and return values.

If anytype is used as a variable, you must assign a value to it before it can be used or you will get a run-time error. After you have assigned a value to it, you cannot convert it to another data type.

## Range

The range of an anytype variable depends on the value first assigned to it. For example, if an integer is assigned, the range of the variable will then be \[-2.147.483.647 ; 2.147.483.647\].

## Declaring anytype Variables

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>anytype declaration</p></td>
<td><p>=</p></td>
<td><p>anytype Variable { , Variable } ;</p></td>
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


## Automatic Conversions

The anytype data types can be automatically converted to dates, enums, integers, reals, strings, guids, int64s, extended data types (records), classes, and containers by assigning a value to the type. For example:
```X++  
    anytype a;
    ;
    a = "text";  // Assigns a string literal
```
However, after you have converted the anytype data type, you cannot then change it to another data type.

## Using anytype Variables

You can use anytype variables in expressions. You can also use them in the same way that you can use the data type that you convert them to. For example, if you assign an integer, you can then apply relational and arithmetic operators to the variable.

However, anytype is usually used as arguments and return types. For example:
```X++  
    public static str range(anytype _from, anytype _to)
    {
        return queryValue(_from) + '..' + queryValue(_to);
    }
```
and
```X++  
    void put(int position, anytype data)
    {
        record = conpoke(record, position, data);
    }
```
## Overview of anytype Variables

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Keyword</p></td>
<td><p>anytype</p></td>
</tr>
<tr class="even">
<td><p>Size</p></td>
<td><p>Depends on conversion type</p></td>
</tr>
<tr class="odd">
<td><p>Scope of data type</p></td>
<td><p>Depends on conversion type</p></td>
</tr>
<tr class="even">
<td><p>Default value</p></td>
<td><p>Depends on conversion type</p></td>
</tr>
<tr class="odd">
<td><p>Implicit conversions</p></td>
<td><p>Automatically converted to dates, enums, integers, reals, strings, extended data types (records), classes, and containers</p></td>
</tr>
<tr class="even">
<td><p>Explicit conversions</p></td>
<td><p>any2date, any2enum, any2int, any2real, any2str</p></td>
</tr>
</tbody>
</table>


## See also

[Data Types in X++](data-types-in-x.md)

[Variables](variables.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

