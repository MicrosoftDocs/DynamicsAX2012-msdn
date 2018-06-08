---
title: Comparison of if and switch Statements
TOCTitle: Comparison of if and switch Statements
ms:assetid: 92d80b86-e006-4ab2-a8d5-086273b4d2ee
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa842207(v=AX.60)
ms:contentKeyID: 35247499
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Comparison of if and switch Statements 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

With X++ there are situations where the [switch statement](switch-statements.md) can be a good alternative to the [if statement](if-and-if-else-statements.md).

## Example 1

When you need your X++ code to branch based on one of several values of a single variable, a switch statement can be a less verbose alternative to the if statement. The following table contains an example of each statement.




<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>if statement</p></th>
<th><p>switch statement</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>static void ConditionalJob1i(Args _args)
{
    int account = 1000;
    if (account == 200)
    {
        print &quot;a&quot;;
    }
    else if (account == 500)
    {
        print &quot;b&quot;;
    }
    else if (account == 1000)
    {
        print &quot;c&quot;;
    }
    else if (account == 2000)
    {
        print &quot;d&quot;;
    }
    else
    {
        print &quot;e&quot;;
    }
    pause;
}</code></pre></td>
<td><pre><code>static void ConditionalJob1s(Args _args)
{
    int account = 1000;
    switch (account)
    {
        case 200:
            print &quot;a&quot;;
            break;
        case 500:
            print &quot;b&quot;;
            break;
        case 1000:
            print &quot;c&quot;;
            break;
        case 2000:
            print &quot;d&quot;;
            break;
        default:
            print &quot;e&quot;;
            break;
    }
    pause;
}</code></pre></td>
</tr>
</tbody>
</table>


## Example 2

When your X++ code must branch based on groups of values for a variable, the switch statement can be a less verbose alternative to the if statement. The following table contains an example of each statement.




<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>if statement</p></th>
<th><p>switch statement</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>static void ConditionalJob2i(Args _args)
{
    int firstNumber = 210;
    int numDivTen = firstNumber / 10;
    if ((numDivTen == 10) ||
        (numDivTen == 12) ||
        (numDivTen == 14)
       )
    {
        print &quot;f&quot;;
    }
    else
    {
        if ((numDivTen == 13) ||
            (numDivTen == 17) ||
            (numDivTen == 21) ||
            (numDivTen == 500)
           )
        {
            print &quot;g&quot;;
        }
        else
        {
            print &quot;h&quot;;
        }
    }
    pause;
}</code></pre></td>
<td><pre><code>static void ConditionalJob2s(Args _args)
{
    int firstNumber = 210;
    switch (firstNumber / 10)
    {
        case 10,12,14:
            print &quot;f&quot;;
            break;
        case 13,17,21,500:
            print &quot;g&quot;;
            break;
        default:
            print &quot;h&quot;;
            break;
    }
    pause;
}</code></pre></td>
</tr>
</tbody>
</table>


### ![Aa842207.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa842207.collapse_all(en-us,AX.60).gif")break Statement

If you do not use the break statement, the program flow in the switch statement continues to the next case. The two code segments in the following table have the same behavior.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>break omitted</p></th>
<th><p>Values are comma-delimited</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>case 13:
case 17:
case 21:
case 500:
    print &quot;g&quot;;
    break;</code></pre></td>
<td><pre><code>case 13,17,21,500:
    print &quot;g&quot;;
    break;</code></pre></td>
</tr>
</tbody>
</table>


## See also

[Conditional Statements](conditional-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

