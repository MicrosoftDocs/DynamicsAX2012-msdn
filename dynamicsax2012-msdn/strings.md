---
title: Strings
TOCTitle: Strings
ms:assetid: f5d27752-1a4d-4de3-9ffa-228f3532ccd1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa889472(v=AX.60)
ms:contentKeyID: 35253577
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Strings [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Strings are sequences of characters that are used as texts, help lines, addresses, telephone numbers, and so on. To declare a string in X++, use the str keyword.

A string can hold an indefinite number of characters. If you know the absolute maximum of characters a string will hold, you can specify this in the variable declaration and force a truncation to the maximum length of the string.

## Range and Precision

Strings are unlimited in length unless a length is specified in the declaration.

## Declaring Strings

The declaration of strings is described in the following table.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>String declaration</p></td>
<td><p>=</p></td>
<td><p>str [Typeoptions] Variable { , Variable } ;</p></td>
</tr>
<tr class="even">
<td><p>Typeoptions</p></td>
<td><p>=</p></td>
<td><p>[maxlength]</p>

> [!caution]  
> <P>X++ that is compiled into .NET Framework common intermediate language (CIL) code ignores the [maxlength] specification. For information about how to detect cases where strings are truncated due to a [maxlength] specification during run time, read about the logstrtrunc option in <a href="https://msdn.microsoft.com/en-us/library/aa569653(v=ax.60)">Client configuration commands</a>.</P>

</td>
</tr>
<tr class="odd">
<td><p>Variable</p></td>
<td><p>=</p></td>
<td><p>Identifier [option]</p></td>
</tr>
<tr class="even">
<td><p>Option</p></td>
<td><p>=</p></td>
<td><p><a href="arrays.md">Arrayoptions</a> | <a href="declaration-of-variables.md">initialization</a></p></td>
</tr>
</tbody>
</table>


The Typeoptions specify an optional maximum length and a comparison scheme.

```X++  
 
//Dynamic string of unlimited length
str indefiniteString;

//String with a maximum of 64 characters, initialized to "A"
str 64 maxLengthString = "A";

//Array of 100 strings
str 30 hundredStrings[100];
```

## String Literals

String literals are characters that are enclosed in quotation marks (" ") and can be used where string expressions are expected. Here are some examples:

  - "Nothing"

  - "A"

  - "yiruyshfkjsadhfkasfhksafhask"

  - "Press any key now."

If you want the string to span more than one line, you need to precede it with an "@" character. For example:

str s = @"This is a very long string that may not fit onto a single line and so may span more than one line";

## Automatic Conversion

There is no automatic conversion of strings.

## Using Strings in Expressions

You can use strings in logical expressions, such as comparisons. You can also concatenate strings by using the + operator, as follows:
```X++  
    void myMethod()
    {
        // Two strings are declared and initialized
        str a="Hello", b="World";
        ;
     
        // The concatenation of a, " " and b is printed in a window.
        print a+" "+b;
        pause;
    }
```
## Overview of Strings

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Keyword</p></td>
<td><p>str</p></td>
</tr>
<tr class="even">
<td><p>Size of data type</p></td>
<td><p>Dynamic or fixed length</p></td>
</tr>
<tr class="odd">
<td><p>Scope of data type</p></td>
<td><p>Unlimited</p></td>
</tr>
<tr class="even">
<td><p>Default value</p></td>
<td><p>&quot;&quot; (empty)</p></td>
</tr>
<tr class="odd">
<td><p>Implicit conversions</p></td>
<td><p>None</p></td>
</tr>
<tr class="even">
<td><p>Explicit conversions</p></td>
<td><p>str2int, str2int64, int2str, str2num, num2str, str2date, date2str</p></td>
</tr>
</tbody>
</table>


## See also

[Data Types in X++](data-types-in-x.md)

[Variables](variables.md)

[str2Int Function](https://msdn.microsoft.com/en-us/library/aa845181\(v=ax.60\))

[str2Int64 Function](https://msdn.microsoft.com/en-us/library/aa882138\(v=ax.60\))

[int2Str Function](https://msdn.microsoft.com/en-us/library/aa851371\(v=ax.60\))

[str2Num Function](https://msdn.microsoft.com/en-us/library/aa591754\(v=ax.60\))

[num2Str Function](https://msdn.microsoft.com/en-us/library/aa866120\(v=ax.60\))

[str2Date Function](https://msdn.microsoft.com/en-us/library/aa554244\(v=ax.60\))

[date2Str Function](https://msdn.microsoft.com/en-us/library/aa857241\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

