---
title: 'X++, C# Comparison: Loops'
TOCTitle: 'X++, C# Comparison: Loops'
ms:assetid: f8ac4fe9-f664-4ef2-9c57-0acb1720eaf1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967439(v=AX.60)
ms:contentKeyID: 35253758
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# X++, C\# Comparison: Loops 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic compares the loop features between X++ and C\#.

## X++ to C\# Comparisons

### ![Cc967439.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967439.collapse_all(en-us,AX.60).gif")Similarities

The following features are the same in X++ and C\#:

  - Declarations for variables of the [int](integers.md) primitive data type. Declarations for other primitive types are almost the same, but the types might have different names.

  - [while](while-loops.md) statement for loops.

  - [break statement](break-statements.md) to exit a loop.

  - [continue statement](continue-statements.md) to jump up to the top of a loop.

  - \<= (less than or equal) comparison operator.

### ![Cc967439.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967439.collapse_all(en-us,AX.60).gif")Differences

The following table lists X++ features that are different in C\#.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Features</p></th>
<th><p>X++</p></th>
<th><p>C#</p></th>
<th><p>Discussion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>The for statement.</p></td>
<td><p>The <a href="for-loops.md">for</a> statement is available for loops.</p></td>
<td><p>The C# for statement is slightly different from for in X++.</p></td>
<td><p>In C# you can declare the counter integer in the for statement. But in X++ the counter must declared outside the for statement.</p></td>
</tr>
<tr class="even">
<td><p>++ increment operator.</p></td>
<td><p>An ++ increment operator is available in X++. But an int variable that is decorated with ++ can only be used as a statement, not as an expression. For example, the following lines of X++ code would not compile:</p>
<p>int age=42; print age++;</p>
<p>However, the following lines of X++ code would compile:</p>
<p>int age=42; age++; print age;</p></td>
<td><p>The C# ++ operator is more flexible than in X++.</p></td>
<td><p>The following lines of code are the same in both languages:</p>
<ul>
<li><p>++ myInteger;</p></li>
<li><p>myInteger++;</p></li>
</ul>
<p>But the following lines of code have a different effect from each other, and are valid only in C#:</p>
<ul>
<li><p>yourInt = ++myInt;</p></li>
<li><p>yourInt = myInt++;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>modulo operator.</p></td>
<td><p>In X++ the modulo operator is <a href="arithmetic-operators.md">mod</a>.</p></td>
<td><p>In C# the modulo operator is %.</p></td>
<td><p>The symbols for the modulo operator are different, but their behavior is the same in both languages.</p></td>
</tr>
<tr class="even">
<td><p>Temporarily suspend a console program that has already begun.</p></td>
<td><p>The pause statement.</p></td>
<td><p>In C#, a command line program can be paused by the following line of code:</p>
<ul>
<li><p>Console.In.Read();</p></li>
</ul></td>
<td><p>In X++ you continue by clicking an <strong>OK</strong> button on a modal dialog box. In C# you continue by pressing any keyboard on the keyboard.</p></td>
</tr>
<tr class="odd">
<td><p>Display a message.</p></td>
<td><p>In X++, the print statement displays a message in the <strong>Print</strong> window.</p></td>
<td><p>In C# a message can be displayed on the console by the following line of code:</p>
<ul>
<li><p>Console.WriteLine();</p></li>
</ul></td>
<td><p>The X++ print function is used only when you test. An X++ program that uses print almost always uses the pause statement somewhere later in the code.</p>
<p>For production X++ code, use the <a href="https://msdn.microsoft.com/en-us/library/gg836019(v=ax.60)">Global::info Method</a> instead of print. The strfmt function is often used together with info. There is no reason to use pause after info.</p></td>
</tr>
<tr class="even">
<td><p>Make a sound.</p></td>
<td><p>The <a href="https://msdn.microsoft.com/en-us/library/aa633614(v=ax.60)">beep function</a> makes a sound that you can hear.</p></td>
<td><p>In C# a sound that you can hear is issued by the following line of code:</p>
<ul>
<li><p>Console.Beep();</p></li>
</ul></td>
<td><p>The statements each produce a short tone.</p></td>
</tr>
</tbody>
</table>


## Print and Global::info

The X++ code samples in this topic use the print function to display results. In X++ you can use the print statement can display any primitive data type without having to call functions that convert it to a string first. This makes print useful in quick test situations. Generally the Global::info method is used more often than print. The info method can only display strings. Therefore the [strfmt function](https://msdn.microsoft.com/en-us/library/aa589727\(v=ax.60\)) is often used together with info.

A limitation of print is that you cannot copy the contents of the Print window to the clipboard (such as with Ctrl+C). Global::info writes to the Infolog window which does support copy to the clipboard.

## Example 1: The while Loop

The while keyword supports looping in both X++ and C\#.

### ![Cc967439.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967439.collapse_all(en-us,AX.60).gif")X++ Sample of while
```X++  
    static void JobRs002a_LoopsWhile(Args _args)
    {
        int nLoops = 1;
        while (nLoops <= 88)
        {
            print nLoops;
            pause;
            // The X++ modulo operator is mod.
            if ((nLoops mod 4) == 0)
            {
                break;
            }
            ++ nLoops;
        }
        beep(); // Function.
        pause; // X++ keyword.
    }
```
#### ![Cc967439.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967439.collapse_all(en-us,AX.60).gif")Output

The output in the X++ Print window is as follows:

<pre IsFakePre="true" xmlns="http://www.w3.org/1999/xhtml">1
2
3
4</pre>


### ![Cc967439.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967439.collapse_all(en-us,AX.60).gif")C\# Sample of while

``` csharp
using System;
public class Pgm_CSharp
{
    static void Main( string[] args )
    {
        new Pgm_CSharp().Rs002a_CSharp_ControlOFlowWhile();
    }
    void Rs002a_CSharp_ControlOFlowWhile()
    {
        int nLoops = 1;
        while (nLoops <= 88)
        {
            Console.Out.WriteLine( nLoops.ToString() );
            Console.Out.WriteLine( "(Press any key to resume.)" );
            // Paused until user presses a key.
            Console.In.Read();

            if ((nLoops % 4) == 0) break;
            ++ nLoops;
        }
        Console.Beep();
        Console.In.Read();
    }
}
```

#### ![Cc967439.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967439.collapse_all(en-us,AX.60).gif")Output

The console output from the C\# program is as follows:

<pre IsFakePre="true" xmlns="http://www.w3.org/1999/xhtml">[C:\MyDirectory\]
&gt;&gt; Rosetta_CSharp_1.exe
1
(Press any key to resume.)

2
(Press any key to resume.)
3
(Press any key to resume.)

4
(Press any key to resume.)</pre>


## Example 2: The for Loop

The for keyword supports looping in both X++ and C\#.

### ![Cc967439.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967439.collapse_all(en-us,AX.60).gif")X++ Sample of for

In X++ the counter variable cannot be declared as part of the for statement.
```X++  
    static void JobRs002a_LoopsWhileFor(Args _args)
    {
        int ii; // The counter.
        for (ii=1; ii < 5; ii++)
        {
            print ii;
            pause;
            // You must click the OK button to proceed
            // beyond a pause statement.
    
            // ii is always less than 99.
            if (ii < 99)
            {
                continue;
            }
            print "This message never appears.";
        }
        pause; // X++ keyword.
    }
```
#### ![Cc967439.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967439.collapse_all(en-us,AX.60).gif")Output

The output in the X++ Print window is as follows:

<pre IsFakePre="true" xmlns="http://www.w3.org/1999/xhtml">1
2
3
4</pre>


### ![Cc967439.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967439.collapse_all(en-us,AX.60).gif")C\# Sample of for

``` csharp
using System;
public class Pgm_CSharp
{
    static void Main( string[] args )
    {
        new Pgm_CSharp().Rs002a_CSharp_ControlOFlowFor();
    }

    void Rs002a_CSharp_ControlOFlowFor()
    {
        int nLoops = 1,
            ii;

        for (ii = 1; ii < 5; ii++)
        {
            Console.Out.WriteLine(ii.ToString());
            Console.Out.WriteLine("(Press any key to resume.)");
            Console.In.Read();

            if (ii < 99)
            {
                continue;
            }
            Console.Out.WriteLine("This message never appears.");
        }
        Console.Out.WriteLine("(Press any key to resume.)");
        Console.In.Read();
    }
}
```

#### ![Cc967439.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967439.collapse_all(en-us,AX.60).gif")Output

The console output from the C\# program is as follows:

<pre IsFakePre="true" xmlns="http://www.w3.org/1999/xhtml">1
(Press any key to resume.)

2
(Press any key to resume.)
3
(Press any key to resume.)

4
(Press any key to resume.)
(Press any key to resume.)</pre>


## See also

[X++, C\# Comparisons](x-csharp-comparisons.md)

[Loops](loops.md)

[Do...while Loops](do-while-loops.md)

[Operators](operators.md)

[X++ Keywords](x-keywords.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

