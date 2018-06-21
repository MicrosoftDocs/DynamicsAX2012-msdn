---
title: 'X++, C# Comparison: Exceptions'
TOCTitle: 'X++, C# Comparison: Exceptions'
ms:assetid: 28c653f4-ed51-4eb6-9c84-71f5f088d21d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967369(v=AX.60)
ms:contentKeyID: 35241726
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# X++, C\# Comparison: Exceptions [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

There are some similarities but many differences when we compare exception related behavior between X++ and C\#.

## X++ to C\# Comparisons

The try, catch, and throw keywords behave the same in X++ and C\#. But the types of exceptions thrown and caught are different for the two languages.

### ![Cc967369.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967369.collapse_all(en-us,AX.60).gif")Similarities

Similarities between X++ and C\# regarding their exception features include the following:

  - Both languages have the same try keyword.

  - Both have the same catch keyword.

  - Both enable for a catch statement that does not specify any particular exception. Such a catch statement catches all exceptions that reach it.

  - Both have the same throw keyword.

### ![Cc967369.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967369.collapse_all(en-us,AX.60).gif")Differences

Exception-related differences between X++ and C\# are described in the following table.

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
<td><p>retry</p></td>
<td><p>Jumps to the first instruction in the associated try block. For more information, see <a href="exception-handling-with-try-and-catch-keywords.md">Exception Handling with try and catch Keywords</a>.</p></td>
<td><p>The functionality of the retry keyword can be mimicked in C# code, but there is no corresponding keyword.</p></td>
<td><p>Only X++ has a retry keyword. C# has no counterpart. For more information, see <a href="x-csharp-comparison-automated-retry-after-an-exception.md">X++, C# Comparison: Automated Retry After an Exception</a>.</p></td>
</tr>
<tr class="even">
<td><p>finally</p></td>
<td><p>There is no finally keyword in X++.</p></td>
<td><p>The finally keyword marks a block of code that follows the try and catch blocks. The finally will be executed regardless of whether any exception is thrown or caught.</p></td>
<td><p>Only C# has a finally keyword. X++ has no counterpart.</p></td>
</tr>
<tr class="odd">
<td><p>Specific exceptions</p></td>
<td><p>In X++ an exception is an element of the Exception enum, such as:</p>
<ul>
<li><p>Error</p></li>
<li><p>Deadlock</p></li>
<li><p>CodeAccessSecurity</p></li>
</ul>
<p>No exception can contain another.</p></td>
<td><p>In C# an exception is an instance of the System.Exception base class, or any class that inherits from it. An exception can be contained in the InnerException property of the thrown exception.</p></td>
<td><p>In X++ each thrown exception is a value of the Exception enum. For more information, see <a href="https://msdn.microsoft.com/en-us/library/gg882127(v=ax.60)">Exception Enumeration</a>.</p></td>
</tr>
<tr class="even">
<td><p>Exception message</p></td>
<td><p>In X++ the message that is created when an exception is raised is available only in the Infolog, and the message is not directly tied to the exception.</p></td>
<td><p>In C# the message is the Message member of the System.Exception object.</p></td>
<td><p>In X++ the Global::error method is the mechanism that display exception messages in the Infolog. For more information, see <a href="exception-handling-with-try-and-catch-keywords.md">Exception Handling with try and catch Keywords</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Exception conditions</p></td>
<td><p>In X++ an error occurs when you call an instance method on an object variable that has not yet had anything assigned to it. However, no exception is raised along with this error. Therefore no catch block can gain control even if the unassigned variable is misused in a try block. In the following code example, the error caused by the code box4.toString(); does not cause control to transfer to any catch block:</p>
<p>DialogBox box4;</p>
<p>try</p>
<p>{</p>
<p>box4.toString();</p>
<p>info(&quot;toString did not error, but expected an error.&quot;);</p>
<p>}</p>
<p>catch (Exception::Error) // No Exception value catches this.</p>
<p>{</p>
<p>info(&quot;Invalid use of box4 gave control to catch, unexpected.&quot;);</p>
<p>}</p></td>
<td><p>In C# a System.NullReferenceException is raised when an uninitialized variable is treated as an object reference.</p></td>
<td><p>There might be several other differences in the conditions that raise exceptions.</p></td>
</tr>
<tr class="even">
<td><p>SQL transactions</p></td>
<td><p>In X++ when an SQL exception occurs in a ttsBegin - ttsCommit transaction, no catch statement inside the transaction block can process the exception.</p></td>
<td><p>In C# a catch block inside an SQL transaction can catch the exception.</p></td>
<td><p>For more information about X++ exceptions during SQL transactions, see the following topics:</p>
<ul>
<li><p><a href="deadlocks.md">Deadlocks</a></p></li>
<li><p><a href="x-standards-ttsbegin-and-ttscommit.md">X++ Standards: ttsBegin and ttsCommit</a></p></li>
<li><p><a href="exception-handling-with-try-and-catch-keywords.md">Exception Handling with try and catch Keywords</a></p></li>
</ul></td>
</tr>
</tbody>
</table>


## X++ and C\# Samples

This section contains two code samples. One sample is written in X++, and the other is in C\#. Both samples achieve the same result.

The following X++ features are demonstrated:

  - try keyword.

  - catch keyword.

  - The behavior after an Exception::Error exception occurs.

### ![Cc967369.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967369.collapse_all(en-us,AX.60).gif")X++ Sample

    static void JobRs008a_Exceptions(Args _args)
    {
        str sStrings[4];
        int iIndex = 77;
        try
        {
            info("On purpose, this uses an invalid index for this array: "
                + sStrings[iIndex]);
            warning("This message does not appear in the Infolog,"
                + " it is unreached code.");
        }
        // Next is a catch for some of the values of
        // the X++ Exception enumeration.
        catch (Exception::CodeAccessSecurity)
        {
            info("In catch block for -- Exception::CodeAccessSecurity");
        }
        catch (Exception::Error)
        {
            info("In catch block for -- Exception::Error");
        }
        catch (Exception::Warning)
        {
            info("In catch block for -- Exception::Warning");
        }
    
        catch
        {
            info("This last 'catch' is of an unspecified exception.");
        }
        //finally
        //{
        //    //Global::Warning("'finally' is not an X++ keyword, although it is in C#.");
        //}
    
        info("End of program.");
    }

#### ![Cc967369.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967369.collapse_all(en-us,AX.60).gif")Output

Here is the actual output from the Infolog window:

<pre IsFakePre="true" xmlns="http://www.w3.org/1999/xhtml">Message (18:07:24)
Error executing code: Array index 77 is out of bounds.

Stack trace

(C)\Jobs\JobRs008a_Exceptions - line 8

In catch block for -- Exception::Error
End of program.
</pre>


### ![Cc967369.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967369.collapse_all(en-us,AX.60).gif")C\# Sample

The following C\# program is a rewrite of the previous X++ program.

``` csharp
using System;
public class Pgm_CSharp
{
    static void Main( string[] args )
    {
        new Pgm_CSharp().Rs008a_CSharp_Exceptions();
    }

    void Rs008a_CSharp_Exceptions()
    {
        //str sStrings[4];
        string[] sStrings = new string[4];

        try
        {
            Console.WriteLine
                ("On purpose, this uses an invalid index"
                + " for this array: " + sStrings[77]);
            Console.Error.WriteLine
                ("This message does not appear in the Infolog,"
                + " it is unreached code.");
        }

        catch (NullReferenceException exc)
        {
            Console.WriteLine("(e1) In catch block for -- "
                + exc.GetType().ToString() );
        }
        catch (IndexOutOfRangeException exc)
        {
            Console.WriteLine("(e2) In catch block for -- "
                + exc.GetType().ToString() );
        }

        // In C#, System.Exception is the base of all
        // .NET Framework exception classes.
        // No as yet uncaught exception can get beyond
        // this next catch.
        catch (Exception exc)
        {
            Console.WriteLine
                ("This last 'catch' is of the abstract"
                + " base type Exception: "
                + exc.GetType().ToString());
        }

        // The preceding catch of System.Exception makes this catch of
        // an unspecified exception redundant and unnecessary.
        //catch
        //{
        //    Console.WriteLine("This last 'catch' is"
        //        + " of an unspecified exception.");
        //}

        finally
        {
            Console.WriteLine
                ("'finally' is not an X++ keyword,"
                + " although it is in C#.");
        }
        Console.WriteLine("End of program.");
    }
} // EOClass
```

#### ![Cc967369.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967369.collapse_all(en-us,AX.60).gif")Output

Here is the actual output to the C\# console:

<pre IsFakePre="true" xmlns="http://www.w3.org/1999/xhtml">(e2) In catch block for -- System.IndexOutOfRangeException
'finally' is not an X++ keyword, although it is in C#.
End of program.</pre>


## See also

[X++, C\# Comparisons](x-csharp-comparisons.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

