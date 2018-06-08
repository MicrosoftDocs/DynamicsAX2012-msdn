---
title: TimeOfDay
TOCTitle: TimeOfDay
ms:assetid: 7569bbb9-9153-4174-90c0-e0c84440ac1c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa674480(v=AX.60)
ms:contentKeyID: 35245965
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# TimeOfDay 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The timeOfDay or time data type is an integer value representing the number of seconds that have elapsed since midnight.

## Range

The range of a timeOfDay data type is in the closed interval \[0; 86400\]. Values above 86400 (23:59:59) cannot be interpreted.

## Declaring timeOfDay Variables

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>TimeOfDay declaration</p></td>
<td><p>=</p></td>
<td><p>timeOfDay Variable { , Variable } ;</p></td>
</tr>
<tr class="even">
<td><p>variable</p></td>
<td><p>=</p></td>
<td><p>identifier [ option ]</p></td>
</tr>
<tr class="odd">
<td><p>option</p></td>
<td><p>=</p></td>
<td><p><a href="arrays.md">Arrayoptions</a> | <a href="declaration-of-variables.md">initialization</a></p></td>
</tr>
</tbody>
</table>


    //Declaration of a time variable, time1
    timeOfDay time1;
     
    //Declaration and initialization of a time variable to 00:21:35
    timeOfDay time2 = 1295;

## Time Literals

timeOfDay variables can be used as literals in the same way as integers are used as literals.

## Automatic Conversions

The same automatic conversions that are available for integers are also available for timeOfDay variables (Booleans, enums, and reals).

## Using Times in Expressions

Any operations that can be performed with integers can also be performed with timeOfDay variables.

## Overview of timeOfDay

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Keyword</p></td>
<td><p>timeOfDay</p></td>
</tr>
<tr class="even">
<td><p>Size</p></td>
<td><p>32 bits</p></td>
</tr>
<tr class="odd">
<td><p>Scope of data type</p></td>
<td><p>[0; 86400]</p></td>
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
<td><p>str2time, time2str</p></td>
</tr>
</tbody>
</table>


## See also

[Data Types in X++](data-types-in-x.md)

[Variables](variables.md)

[str2Time Function](https://msdn.microsoft.com/en-us/library/aa642744\(v=ax.60\))

[time2Str Function](https://msdn.microsoft.com/en-us/library/aa596607\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

