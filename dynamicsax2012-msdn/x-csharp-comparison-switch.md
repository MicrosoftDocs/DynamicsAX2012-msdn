---
title: 'X++, C# Comparison: Switch'
TOCTitle: 'X++, C# Comparison: Switch'
ms:assetid: 78074b1b-470d-4467-adfa-2373d421da09
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967402(v=AX.60)
ms:contentKeyID: 35246006
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# X++, C\# Comparison: Switch 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic compares the switch statement in X++ and C\#.

## X++ to C\# Comparisons

In both X++ and C\#, the switch statement involves the keywords case, break, and default.

The following table lists the differences in the switch statement between X++ and C\#.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Feature</p></th>
<th><p>X++</p></th>
<th><p>C#</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>break; at the end of each case block</p></td>
<td><p>In X++, when any case block matches the expression value on the switch clause, all other case and default blocks are executed until a break; statement is reached.</p>
<p>No break; statement is ever required in an X++ switch statement, but break; statements are important in almost all practical situations.</p></td>
<td><p>In C#, a break; statement is always needed after the statements in a case or default block.</p>
<p>If a case clause has no statements between itself and the next case clause, a break; statement is not required between the two case clauses.</p></td>
<td><p>We recommend against omitting the break; statement after any case block, because it can confuse the next programmer who edits the code.</p></td>
</tr>
<tr class="even">
<td><p>break; at the end of the default block</p></td>
<td><p>In X++ there is no effect of adding a break; statement at the end of the default block.</p></td>
<td><p>In C# the compiler requires a break; statement at the end of the default block.</p></td>
<td><p>For more information, see <a href="switch-statements.md">Switch Statements</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Only constant values on a case block</p></td>
<td><p>In X++ you can specify either a literal value or a variable on a case block. For example, you can write case myInteger:.</p></td>
<td><p>In C# you must specify exactly one literal value on each case block, and no variables are allowed.</p></td>
<td><p>No comments.</p></td>
</tr>
<tr class="even">
<td><p>Multiple values on one case block</p></td>
<td><p>In X++ you can specify multiple values on each case block. The values must be separated by a comma. For example, you can write case 4,5,myInteger:.</p></td>
<td><p>In C# you must specify exactly one value on each case block.</p></td>
<td><p>In X++ it is better to write multiple values on one case block than to omit the break; statement at the end of one or more case blocks.</p></td>
</tr>
</tbody>
</table>


## Code Examples for switch

The following sections show comparable switch statements in X++ and C\#.

### ![Cc967402.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967402.collapse_all(en-us,AX.60).gif")X++ switch Example

The X++ switch example shows the following:

  - case iTemp: and case (93-90): to show that case expressions are not limited to constants, as they are in C\#.

  - //break; to show that break; statements are not required in X++, although they are almost always desirable.

  - case 2, (93-90), 5: to show that multiple expressions can be listed on on case clause in X++.

<!-- end list -->
  ```X++  
    static void GXppSwitchJob21(Args _args)  // X++ job in AOT > Jobs.
    {
      int iEnum = 3;
      int iTemp = 6;
      
      switch (iEnum)
      {
        case 1:
        case iTemp:  // 6
          info(strFmt("iEnum is one of these values: 1,6: %1", iEnum));
          break;
    
        case 2, (93-90), str2Int("5"):  // Equivalent to three 'case' clauses stacked, valid in X++.
        //case 2:
        //case (93-90):  // Value after each 'case' can be a constant, variable, or expression; in X++.
        //case str2Int("5"):
          info(strFmt("iEnum is one of these values: 2,3,5: %1", iEnum));
          //break;  // Not required in X++, but usually wanted.
    
        case 4:
          info(strFmt("iEnum is one of these values: 4: %1", iEnum));
          break;
    
        default:
          info(strFmt("iEnum is an unforeseen value: %1", iEnum));
          break;
      
        // None of these 'break' occurrences in this example are required for X++ compiler.
      }
      return;
    }
    /*** Copied from the Infolog:
    Message (02:32:08 pm)
    iEnum is one of these values: 2,3,5: 3
    iEnum is one of these values: 4: 3
    ***/
  ```
### ![Cc967402.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967402.collapse_all(en-us,AX.60).gif")C\# switch Example

The C\# switch example shows the following:

  - case 1: has a comment explaining that only constant expressions can be given on a case clause.

  - break; statements occur after the last statement in each case block that has statements, as is required by C\#.

<!-- end list -->

``` csharp
using System;  // C#

namespace CSharpSwitch2
{
  class Program
  {
    static void Main(string[] args)  // C#
    {
      int iEnum = 3;

      switch (iEnum)
      {
        case 1:  // Value after each 'case' must be a constant.
        case 6:
          Console.WriteLine("iEnum is one of these values: 1,6: " + iEnum.ToString());
          break;

        //case 2,3,5:  // In C# this syntax is invalid, and multiple 'case' clauses are needed.
        case 2:
        case 3:
        case 5:
          Console.WriteLine("iEnum is one of these values: 2,3,5: " + iEnum.ToString());
          break;

        case 4:
          Console.WriteLine("iEnum is one of these values: 4: " + iEnum.ToString());
          break;

        default:
          Console.WriteLine("iEnum is an unforeseen value: " + iEnum.ToString());
          break;

        // All 'break' occurrences in this example are required for C# compiler.
      }
      return;
    }
  }
}
/*** Output copied from the console:
>> CSharpSwitch2.exe
iEnum is one of these values: 2,3,5: 3
>>
***/
```

## See also

[X++, C\# Comparisons](x-csharp-comparisons.md)

[Switch Statements](switch-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

