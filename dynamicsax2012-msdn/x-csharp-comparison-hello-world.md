---
title: 'X++, C# Comparison: Hello World'
TOCTitle: 'X++, C# Comparison: Hello World'
ms:assetid: aca5a37a-8f57-4b5f-b888-a9a70604c156
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967415(v=AX.60)
ms:contentKeyID: 35249718
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# X++, C\# Comparison: Hello World 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic compares the simplest X++ program to its counterpart in C\#.

## X++ to C\# Comparisons

The following sections describe some basic similarities and differences between X++ and C\#.

### ![Cc967415.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967415.collapse_all(en-us,AX.60).gif")Similarities

The following X++ features are the same for C\#:

  - Single line (//) and multi-line (/\* \*/) [comments](comments.md).

  - \== (equal) operator for determining whether two values are equal.

  - \!= (not equal to) operator for determining whether two values are not equivalent.

  - \+ (plus sign) operator for string concatenation.

### ![Cc967415.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967415.collapse_all(en-us,AX.60).gif")Differences

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
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Declarations</p></td>
<td><p>All declarations must be at the start of the method, before any X++ statements.</p></td>
<td><p>Declarations can occur anywhere in the method.</p></td>
<td><p>Both languages permit multiple variables of the same type to be listed together in one declaration. Both languages allow you to assign an initial value in the declaration statement.</p></td>
</tr>
<tr class="even">
<td><p>if and else <a href="conditional-statements.md">conditional statements</a></p></td>
<td><p>The if statement accepts any type of expression that it can automatically convert to a Boolean. Common examples include an int for which 0 means false, or an object for which null means false.</p></td>
<td><p>The if statement requires a Boolean expression.</p></td>
<td><p>The syntax structure regarding curly braces and parentheses is exactly the same between X++ and C#.</p></td>
</tr>
<tr class="odd">
<td><p>Literal string</p></td>
<td><p>A literal string can be delimited by either of the following:</p>
<ul>
<li><p>A pair of double quotation mark (&quot;) characters.</p></li>
<li><p>A pair of single quotation mark (') characters.</p></li>
</ul></td>
<td><p>A literal string must be delimited by a pair of double quotation mark (&quot;) characters.</p></td>
<td><p>For X++, the double quotation mark characters are usually used to delimit strings. However, it is convenient delimit a string with single quotation mark characters when your string must contain a double quotation mark character.</p></td>
</tr>
<tr class="even">
<td><p>char type</p></td>
<td><p>There is no char or character type in X++. You can declare a str of length one, but it is still a string:</p>
<p>str 1 myString = &quot;a&quot;;</p></td>
<td><p>There is a char in C#. You cannot pass a char as the parameter to a method that inputs a string parameter, although you can first explicitly convert the char to a string.</p></td>
<td><p>For more information about X++ data types, see <a href="primitive-data-types.md">Primitive Data Types</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Output of messages</p></td>
<td><p>X++ delivers messages to the user in the Infolog window. Common methods include the following:</p>
<ul>
<li><p>The print statement:</p></li>
<li><p>static methods on the Global class:</p>
<ul>
<li><p>Global::info</p></li>
<li><p>Global::warning</p></li>
<li><p>Global::error</p></li>
</ul></li>
</ul></td>
<td><p>For a command line C# program, messages can be delivered to the console. Common methods include the following:</p>
<ul>
<li><p>Console.Out.WriteLine</p></li>
<li><p>Console.Error.WriteLine</p></li>
</ul></td>
<td><p>The print statement is not a function nor a method. Recommended use would be print mystring; rather than print(mystring);. A pause; statement is always useful shortly after a print statement. The print statement is convenient for testing because it automatically converts int and other primitive values to strings for display. For more information, see <a href="print-statements.md">Print Statements</a>.</p>
<p>The Global class has special recognition in the X++ compiler. The info method can be called without including the Global:: prefix.</p>
<p>For more information, see, <a href="https://msdn.microsoft.com/en-us/library/gg836019(v=ax.60)">Global::info Method</a>.</p></td>
</tr>
</tbody>
</table>


## X++ and C++ Samples

This section contains two simple code samples. One sample is written in X++, and the other is in C\#. Both samples achieve the same result.

The following X++ features are demonstrated:

  - // single line comment

  - /\* \*/ multi-line comment

  - if statement

  - \== operator

  - \!= operator

  - \+ operator to concatenate strings

  - Global::info for message output, with and without the Global:: prefix

  - Global::error for message output

  - The use of single and double quotation characters (' and ") as string delimiters.
    

    > [!NOTE]
    > <P>The best practice is to use double quotation marks for any string that might be displayed to the user.</P>



### ![Cc967415.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967415.collapse_all(en-us,AX.60).gif")X++ Sample

This X++ code sample is in the form of a job. There is a node titled **Jobs** in the Application Object Tree (AOT). This sample can be added under the **Jobs** node, and then the job can be run.

    static void JobRs001a_HelloWorld(Args _args)
    {
        if (1 == 1) 
        {
            // These two info() calls are identical to the X++ compiler.
            // The second form is the one typically used in X++.
            Global::info("Hello World, 1.");
            info('Hello World, 2.');
        }
        
        if (1 != 1)
        {
            error("This message will not appear.");
        }
        else
        {
            // These two methods are also from the Global class.
            // The '+' operator concatenates two strings.
            warning("This is like info," + " but is for warnings, 3.");
            error("This is like info," + " but is for errors, 4.");
        }
    }

#### ![Cc967415.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967415.collapse_all(en-us,AX.60).gif")Output

Here is the actual output from the Infolog window:

<pre IsFakePre="true" xmlns="http://www.w3.org/1999/xhtml">Message (09:49:48)
Hello World, 1.
Hello World, 2.
This is like info, but is for warnings, 3.
This is like info, but is for errors, 4.</pre>


### ![Cc967415.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967415.collapse_all(en-us,AX.60).gif")C\# Sample

The following C\# program is a rewrite of the previous X++ program. The differences between X++ and C\# are highlighted by commenting out the X++ lines, and replacing them with the C\# syntax.

``` csharp
using System;
class Pgm_CSharp
{
    static void Main( string[] args )
    {
        new Pgm_CSharp().Rs001a_CSharp_HelloWorld();
    }
    
    void Rs001a_CSharp_HelloWorld()
    {
        if (1 == 1) 
        {
            Console .Out .WriteLine(
                "Hello World, Explicit .Out , 1.");
            Console .WriteLine(
                "Hello World, Implicit default to .Out , 2.");
        }
    
        if (1 != 1)
        {
            Console .Error .WriteLine(
                "This message will not appear.");
        }
        else
        {
            Console .Error .WriteLine(".Error is like .Out,"
                + " but can be for warnings, 3.");
            Console .Error .WriteLine(".Error is like .Out,"
                + " but is for errors, 4.");
        }
    }
}
```

#### ![Cc967415.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967415.collapse_all(en-us,AX.60).gif")Output

Here is the actual output to the C\# console:

Hello World, Explicit .Out , 1.

Hello World, Implicit default to .Out , 2.

.Error is like .Out, but can be for warnings, 3.

.Error is like .Out, but is for errors, 4.

## See also

[X++, C\# Comparisons](x-csharp-comparisons.md)

[Relational Operators](relational-operators.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

