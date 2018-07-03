---
title: Reals
TOCTitle: Reals
ms:assetid: e07c04d3-0a57-4e69-99dd-ca7480b77797
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa878630(v=AX.60)
ms:contentKeyID: 35252090
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Reals 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Real variables can hold decimal values in addition to holding integers. For example, you might use a real to represent a currency amount. Internally, a real is stored as a Binary Coded Decimal (BCD encoding). The BCD encoding makes it possible to make exact representations of values that are multiples of 0.1.

## Range and Precision

The range of reals is -(10)127 to (10)127 with a precision of 16 significant digits.

## Declaring Reals

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>real declaration</p></td>
<td><p>=</p></td>
<td><p>real Variable { , Variable } ;</p></td>
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

```X++  
    // Simple declaration of a real variable, r
    real r;
     
    // Multiple declaration of two real variables
    real r1, r2;
     
    // A real variable is initialized to the approximate value of pi
    real r3 = 3.1415;
     
    // Declaration of a dynamic array of reals
    real r4[];
```
## Decimal Literals

You can use decimal literals anywhere where a real is expected. A decimal literal is the decimal written directly in the code, for instance 2.123876. The range of reals is shown above, and all reals in this range can be used as literals in X++.

## Exponential Notation

Real literals can also be written using exponential notation. Examples are:
```X++
    real r;
    ;
    r = 1.000e3;
    r = 1.2345e+3;
    r = 1.2345e+03;
    r = 1234.5e40;
    r = 1.0e; // Means 1.0E1
```
## Automatic Conversions

X++ performs automatic conversion of reals to Booleans, enums, and integers in expressions, depending on the result of the expression.

If the result is an integer or the operator is an integer-operator, reals are converted into integers. If the result is a Boolean, reals are converted to Booleans, and so on. For example:
```X++
    void main()
    {
        //Declares a variable of type integer with the name exprValue
        int exprValue;
     
        //Declares a real variable with the name area
        real area = 3.141528;
        ;
        exprValue = Area/3;
    }
```
The expression Area/3 is a real expression because division is a real operator, and the result is 1.047176. This result is automatically converted (actually truncated) to an integer with the value 1, because exprValue is an integer.

### ![Aa878630.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa878630.collapse_all(en-us,AX.60).gif")Conversion to .NET System.Decimal

Direct assignments between X++ real and .NET Framework System.Decimal convert the value correctly without the need to call any conversion function. This is demonstrated in the following code example.
```X++  
    static public void Main(Args _args)
    {
        real real9;
        System.Decimal sysdec1;
        
        // Direct assignments supported between these types.
        sysdec1 = 2.3456;
        real9 = sysdec1;
        
        info(strFmt("strFmt says real9 == %1", real9));
    }
    /***
    Message (05:48:43 pm)
    strFmt says real9 == 2.35
    ***/
```
## Using Reals in Expressions

Reals can be used in all expressions and with both relational operators and arithmetic operators as shown in the following example:
```X++  
    void myMethod() 
    {
        // Two real variables are declared and initialized
        real i = 2.5, j = 2.5;
        ; 
     
        // j is assigned the result of j * i, so j=6.25
        j = j * i; 
     
        if (j > (i * 2)) // If j > 5 
        {
            print "Great"; // "Great" is printed
        }
        else 
        {
            print "Oops"; // else "Oops" is printed
        }
    }
```
## Overview of Reals

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Keyword</p></td>
<td><p>real</p></td>
</tr>
<tr class="even">
<td><p>Size of data type</p></td>
<td><p>BCD-encoding: 64 bit</p></td>
</tr>
<tr class="odd">
<td><p>Scope of data type</p></td>
<td><p>] -(10)127 ; (10)127 [, with a precision of 16 significant digits</p></td>
</tr>
<tr class="even">
<td><p>Default value</p></td>
<td><p>0.00</p></td>
</tr>
<tr class="odd">
<td><p>Implicit conversions</p></td>
<td><p>Automatically converted to boolean, enum, and int</p></td>
</tr>
<tr class="even">
<td><p>Explicit conversions</p></td>
<td><p>str2num, num2str</p></td>
</tr>
</tbody>
</table>


## See also

[Data Types in X++](data-types-in-x.md)

[Variables](variables.md)

[str2Num Function](https://msdn.microsoft.com/en-us/library/aa591754\(v=ax.60\))

[num2Str Function](https://msdn.microsoft.com/en-us/library/aa866120\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

