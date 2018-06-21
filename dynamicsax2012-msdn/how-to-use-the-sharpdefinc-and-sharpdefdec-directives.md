---
title: 'How to: Use the #defInc and #defDec Directives'
TOCTitle: 'How to: Use the #defInc and #defDec Directives'
ms:assetid: be4f9fa7-c80c-4bef-8a4b-199ec5345af5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc197118(v=AX.60)
ms:contentKeyID: 35250054
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use the \#defInc and \#defDec Directives [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The \#defInc and \#defDec directives apply only to macros that have a value that can be converted to the formal int type. A value can only contain numerals. The only non-numeric character allowed is a leading negative sign (-).

\#defInc and \#defDec are the only directives that interpret the value of a macro.

The integer value is treated as an X++ int, not as an int64.

## Prerequisites

For this topic, you must understand the information in [How to: Test a Macro Value](how-to-test-a-macro-value.md).

## Code Sample Using \#defInc and \#defDec

In the following code sample, the initial value of the macro CounterMacroA is a string that can be converted into an integer. The sample shows how the \#defInc and \#defDec directives can be used for this macro name.

    static void SimpleDefINCJob(Args _args)
    {
        ;
        #define.CounterMacroA(1)
    
        #defInc.CounterMacroA
    
        info("mg11: # CounterMacroA == " + int2str(#CounterMacroA));
    
        #if.CounterMacroA(2)
            info("mg12: # if confirms CounterMacroA == 2");
        #endif
    
        #defDec.CounterMacroA
    
        info("mg23: # CounterMacroA == " + int2str(#CounterMacroA));
    
        #if.CounterMacroA(1)
            info("mg24: # if confirms CounterMacroA == 1");
        #endif
    
    /**************  Actual Infolog output
    Message (12:47:57 pm)
    mg11: # CounterMacroA == 2
    mg12: # if confirms CounterMacroA == 2
    mg23: # CounterMacroA == 1
    mg24: # if confirms CounterMacroA == 1
    **************/
    }

## Treatment of Special Values

It is recommended that the \#defInc and \#defDec directives only be used for macros that have an integer value. The precompiler follows special rules for \#defInc when the macro value is not an integer, or when the value is unusual or extreme.

### ![Cc197118.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197118.collapse_all(en-us,AX.60).gif")Values that are Converted to Zero

The following table lists the values that \#defInc converts to zero (0) and then increments. When a value is converted to 0 by \#defInc, the original value cannot be recovered, not even by \#defDec.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Macro value</p></th>
<th><p>Behavior</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>(+55)</p></td>
<td><p>The positive sign (+) prefix makes the precompiler treat this as a non-numeric string. The precompiler treats all non-numeric strings as 0 when it handles a #defInc (or #defDec) directive.</p></td>
</tr>
<tr class="even">
<td><p>(&quot;3&quot;)</p></td>
<td><p>Integers enclosed in quotation marks are treated as 0. The quotation marks are discarded, and these changes persist.</p></td>
</tr>
<tr class="odd">
<td><p>( )</p></td>
<td><p>A string of spaces is treated as 0, and then incremented.</p></td>
</tr>
<tr class="even">
<td><p>()</p></td>
<td><p>A zero-length string is treated as 0, and then incremented, when the value is enclosed in parentheses, as in #define.MyMac().</p></td>
</tr>
<tr class="odd">
<td><p>(Random string.)</p></td>
<td><p>Any non-numeric string of characters is treated as 0, and then incremented.</p></td>
</tr>
<tr class="even">
<td><p>(0x12)</p></td>
<td><p>Hexadecimal numbers are treated as non-numeric strings. Therefore they are converted to 0, and then incremented.</p></td>
</tr>
</tbody>
</table>


### ![Cc197118.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197118.collapse_all(en-us,AX.60).gif")Other Special Values

The following table explains how other special values are treated by \#defInc.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Macro value</p></th>
<th><p>Behavior</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>(-44)</p></td>
<td><p>Negative numbers are acceptable, including integers without the negative sign (-).</p></td>
</tr>
<tr class="even">
<td><p>(2147483647)</p></td>
<td><p>The maximum positive int value is changed to the minimum negative int value by #defInc.</p></td>
</tr>
<tr class="odd">
<td><p>(999888777666555)</p></td>
<td><p>Any large number, beyond the capacity of int and int64. This is treated as the maximum positive int value.</p></td>
</tr>
<tr class="even">
<td><p>(5.8)</p></td>
<td><p>Real numbers are truncated by #defDec (and #defInc). Subsequent symbol substitution shows that the truncation persists.</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>When no value and no parentheses are provided for the directive #define.MyValuelessMacro, the precompiler rejects use of the directive #defInc.MyValuelessMacro.</p></td>
</tr>
</tbody>
</table>


## Important Scoping of \#defInc

For macro names that are used by the \#defInc directive, it is important that the \#define directive that creates the macro not reside in a class declaration. The behavior of \#defInc in these cases is unpredictable. Instead, such macros should be defined in only a method or job.

## See also

[Macros in X++](macros-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

