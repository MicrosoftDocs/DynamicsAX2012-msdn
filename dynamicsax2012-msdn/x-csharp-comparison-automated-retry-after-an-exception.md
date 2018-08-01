---
title: 'X++, C# Comparison: Automated Retry After an Exception'
TOCTitle: 'X++, C# Comparison: Automated Retry After an Exception'
ms:assetid: 94ff92fe-e94e-47fb-8128-b9646b241369
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967407(v=AX.60)
ms:contentKeyID: 35247607
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# X++, C\# Comparison: Automated Retry After an Exception [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Sometimes you can write code in a catch block that fixes the cause of an exception that occurs during run time. X++ provides a retry keyword that can be used only inside a catch block. The retry keyword enables a program to jump back to the start of the try block after the problem has been corrected by code in the catch block.

C\# does not have a retry keyword. However, C\# code can be written to provide equivalent behavior.

## X++ and C\# Code Samples for Retry

The following X++ sample program causes an Exception::Error to be raised. This occurs when it first tries to read an element from the sStrings array by using an invalid index value. When the exception is caught, corrective action is taken during run time inside the catch block. The retry statement then jumps back to the first statement in the try block. This second iteration works without encountering any exception.

```X++
    static void JobRs008b_ExceptionsAndRetry(Args _args)
    {
        str sStrings[4];
        str sTemp;
        int iIndex = 0;
        ;
        sStrings[1] = "First array element.";
        try
        {
            print("At top of try block: " + int2str(iIndex));
            sTemp = sStrings[iIndex];
            print( "The array element is: " + sTemp );
        }
        catch (Exception::Error)
        {
            print("In catch of -- Exception::Error (will retry)."
                + " Entering catch.");
            ++iIndex;
            print("In catch of -- Exception::Error (will retry).
                + " Leaving catch.");
    
            // Here is the retry statement.
            retry;
        }
    
        print("End of X++ retry program.");
        pause;
    }
```

#### ![Cc967407.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967407.collapse_all(en-us,AX.60).gif")Output

Here is the actual output to the Print window:

<pre IsFakePre="true" xmlns="http://www.w3.org/1999/xhtml">At top of try block: 0
In catch of -- Exception::Error (will retry). Entering catch.
In catch of -- Exception::Error (will retry). Leaving catch.
At top of try block: 1
The array element is: First array element.
End of X++ retry program.</pre>


### ![Cc967407.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967407.collapse_all(en-us,AX.60).gif")C\# Sample

The following C\# sample is not a line-by-line translation from the previous X++ sample. Instead the C\# program has a different structure so that it mimics the behavior of the retry keyword that the X++ program relies on.

The try and catch blocks are in a called method. The variables that are used in the try block are stored in the caller method. The caller method passes the variables as parameters that are decorated with the ref keyword, so that their values can be corrected inside the catch block of the called method. The called method captures all exceptions, and returns a boolean to communicate back to the caller whether a second call is required.

``` csharp
using System;
public class Pgm_CSharp
{
    static void Main(string[] args)
    {
        new Pgm_CSharp() .Rs008b_CSharp_ExceptionsAndRetry();
    }
    void Rs008b_CSharp_ExceptionsAndRetry() // Caller
    {
        int iIndex = -1
            , iNumRetriesAllowed = 3;
        bool bReturnCode = true; // Means call the callee method.

        for (int xx=0; xx <= iNumRetriesAllowed; xx++)
        {
            if (bReturnCode)
            {
                bReturnCode = this
                    .Rs008b_CSharp_ExceptionsAndRetry_Callee
                    (ref iIndex);
            }
            else
            {
                break;
            }
        }
        Console.WriteLine("End of C# caller method.");
    }

    private bool Rs008b_CSharp_ExceptionsAndRetry_Callee
            (ref int iIndex)
    {
        bool bReturnCode = true; // Means call this method again.
        string[] sStrings = new string[4];
        string sTemp;

        sStrings[0] = "First array element.";
        try
        {
            Console.WriteLine("At top of try block: "
                + iIndex.ToString());
            sTemp = sStrings[iIndex];
            Console.WriteLine( "The array element is: " + sTemp );

            bReturnCode = false; // Means do not call this method again.
        }
        catch (Exception)
        {
            Console.WriteLine
                ("In catch of -- Exception. Entering catch.");
            ++iIndex; // The 'ref' parameter in C#.
            Console.WriteLine
                ("In catch of -- Exception. Leaving catch.");

            //retry;
            // In C# we let the caller method do the work
            // that the retry keyword does in X++.
        }
        Console.WriteLine("End of C# callee method.");
        return bReturnCode;
    }
}
```

#### ![Cc967407.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967407.collapse_all(en-us,AX.60).gif")Output

Here is the actual output to the console:

<pre IsFakePre="true" xmlns="http://www.w3.org/1999/xhtml">At top of try block: -1
In catch of -- Exception. Entering catch.
In catch of -- Exception. Leaving catch.
End of C# callee method.
At top of try block: 0
The array element is: First array element.
End of C# callee method.
End of C# caller method.</pre>


## See also

[X++, C\# Comparisons](x-csharp-comparisons.md)

[X++ Standards: try/catch Statements](x-standards-try-catch-statements.md)

[Exception Handling with try and catch Keywords](exception-handling-with-try-and-catch-keywords.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

