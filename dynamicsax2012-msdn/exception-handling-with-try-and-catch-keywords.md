---
title: Exception Handling with try and catch Keywords
TOCTitle: Exception Handling with try and catch Keywords
ms:assetid: fe47bc25-ae7f-42df-a8c3-592d9f714471
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa893385(v=AX.60)
ms:contentKeyID: 35254212
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Exception Handling with try and catch Keywords 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can write your X++ code to handle errors by using the statements for generating and handling exceptions.

For example, your method might receive an input parameter value that is invalid. Your method can throw an exception to immediately transfer control to a catch code block that contains logic to handle this particular error situation. You do not necessarily need to know the location of the catch block that will receive control when the exception is thrown.

## What is an Exception?

An exception is a regulated jump away from the regular sequence of program instruction execution. The instruction at which program execution resumes is determined by try - catch blocks and the type of exception that is thrown.

In X++, an exception is represented by a value of the enum named Exception. A frequently thrown exception is Exception::error enumeration value. This exception is thrown in a variety of situations. It is common practice to write diagnostic information to the **Infolog** before throwing the exception, and the Global::error method is often the best way to do that.

## Exception Related X++ Statements

You use the following X++ statements to generate and handle exceptions:

  - throw

  - try

  - catch

  - retry


> [!NOTE]
> <P>There is no finally statement in X++.</P>



### ![Aa893385.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa893385.collapse_all(en-us,AX.60).gif")The throw Statement with an Exception Member

You can use the throw keyword to throw an Exception enum value. For example, the following statement throws an enum value as an exception:

throw Exception::error;

#### ![Aa893385.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa893385.collapse_all(en-us,AX.60).gif")The throw Statement with the Global::error Method

Instead of throwing an enum value, it is a best practice to use the Global::error method output as the operand for throw:

throw Global::error("The parameter value is invalid.");

The Global::error method can automatically convert a label into the corresponding text. This helps you to write code that can be more easily localized.

throw Global::error("@SYS98765");


> [!TIP]
> <P>In X++ code, the static methods on the Global class can be called without the Global:: prefix. For example, the Global::error method can be called simply as error("My message.");.</P>



### ![Aa893385.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa893385.collapse_all(en-us,AX.60).gif")The try and catch Statements

When an exception is thrown, it is first processed through the catch list of the innermost try block.

If a catch is found that handles the kind of exception that is being thrown, program control jumps to that catch block. If the catch list has no block that specifies the particular exception, the system passes the exception to the catch list of the next innermost try block.

The catch statements are processed in the same sequence that they appear in the X++ code. It is common to have the first catch statement handle the Exception::Error enumeration value.

One strategy is to have the last catch statement leave the exception type unspecified. This means it handles all exceptions that are not handled by a previous catch. This strategy is appropriate for the outermost try - catch blocks.

    try { /* Code here. */ }
    catch (Exception::Numeric) { info("Caught a Numeric exception."); }
    catch { info("Caught an exception."); }

### ![Aa893385.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa893385.collapse_all(en-us,AX.60).gif")The retry Statement

The retry statement can be written only in a catch block. The retry statement causes control to jump up to the first line of code in the associated try block.


> [!WARNING]
> <P>You must prevent your use of retry from causing an infinite loop. The early statements in your try block must contain an if test of a variable that eventually ends the looping.</P>



The retry statement is used when the cause of the exception can be fixed by the code in the catch block. The retry statement gives the code in the try block another chance to succeed.


> [!NOTE]
> <P>The retry statement erases messages that were written to the <STRONG>Infolog</STRONG> since program control entered the try block.</P>



## The System Exception Handler

If no catch statement handles the exception, it is handled by the system exception handler. The system exception handler does not write to the **Infolog**. This means that an unhandled exception can be hard to diagnose. Therefore we recommended that you do all the following to provide effective exception handling:

  - Have a try block that contains all your statements in the outermost frame on the call stack.

  - Have an unqualified catch block at the end of your outermost catch list.

  - Avoid throwing an Exception enum value directly.

  - Do throw the enum value that is returned from one of the following methods on the Global class (you have the option of omitting the implicit Global:: prefix):
    
      - Global::error
    
      - Global::warning
    
      - Global::info

  - When you catch an exception that has not been displayed in the **Infolog**, call the Global::info function to display it.
    

    > [!TIP]
    > <P>Exception::CLRError, Exception::UpdateConflictNotRecovered, and system kernel exceptions are examples of exceptions that are not automatically displayed in the <STRONG>Infolog</STRONG>.</P>



## Exceptions and CLR Interop

From X++ you can call .NET Framework classes and methods that reside in assemblies that are managed by the common language runtime (CLR). When a .NET Framework System.Exception instance is thrown, your code can catch it by referencing Exception::CLRError.

Your code can obtain a reference to the System.Exception instance by calling the CLRInterop::getLastException method.

### ![Aa893385.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa893385.collapse_all(en-us,AX.60).gif")Ensure Exceptions are Displayed

Exceptions of type Exception::CLRError are not displayed in the **Infolog**. These exceptions are not issued by a call to a method such as Global::error. In your catch block, your code can call Global::error to report the specific exception.

## Global Class Methods for Exceptions

This section describes some Global class methods in more detail.

### ![Aa893385.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa893385.collapse_all(en-us,AX.60).gif")The Global::error Method Parameters

The error method is declared as follows:

```X++
    server client static Exception error
        (SysInfoLogStr txt,
        URL helpURL = '',
        SysInfoAction _sysInfoAction = null)
```

The return type is the Exception::Error enum value. The error method does not throw an exception. It only provides an enum value that could be used in a throw statement. The throw statement throws the exception.

Only the first parameter is required. The parameters are described in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Parameter</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SysInfoLogStr txt</p></td>
<td><p>A str of the message text.</p>
<p>This can also be a label reference, such as strFmt(&quot;@SYS12345&quot;, strThingName).</p></td>
</tr>
<tr class="even">
<td><p>URL helpUrl</p></td>
<td><p>A reference to the location of a Help topic in the Application Object Tree (AOT). For example:</p>
<p>&quot;KernDoc:\\\\Functions\\substr&quot;</p>
<p>This parameter value is ignored if _sysInfoAction is supplied.</p></td>
</tr>
<tr class="odd">
<td><p>SysInfoAction _sysInfoAction</p></td>
<td><p>An instance of a class that extends the SysInfoAction class.</p>
<p>The following list shows the method overrides we recommend for the child class:</p>
<ul>
<li><p>description</p></li>
<li><p>run</p></li>
<li><p>pack</p></li>
<li><p>unpack</p></li>
</ul>
<p>For sample code that uses SysInfoAction, see Sample 6.</p></td>
</tr>
</tbody>
</table>


### ![Aa893385.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa893385.collapse_all(en-us,AX.60).gif")The Global::info Method

The Global::info method is routinely used to display text in the **Infolog**. It is often written in programs as just info("My message.");. Even though the info method returns an Exception::Info enumeration value it would be rare to want to throw an Exception::Info because nothing unexpected has occurred.

### ![Aa893385.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa893385.collapse_all(en-us,AX.60).gif")The Global::exceptionTextFallThrough Method

Occasionally you want to do nothing inside your catch block. The X++ compiler issues a warning when you have an empty catch block. You should avoid this warning by calling the Global::exceptionTextFallThrough method in the catch block. The method does nothing, but it satisfies the compiler.

## Exceptions Inside Transactions

If an exception is thrown inside a transaction, the transaction is automatically aborted (a ttsAbort operation occurs). This applies both for exceptions thrown manually and for exceptions thrown by the system.

When an exception is thrown inside a ttsBegin - ttsCommit transaction block, no catch statement inside that transaction block can process the exception. Instead, the innermost catch statements that are outside the transaction block are the first catch statements to be tested.

## Code Samples

The next sections have the following code samples:

  - Sample 1: Display exceptions in the infolog

  - Sample 2: error method to write exception to infolog

  - Sample 3: Handle a CLRError

  - Sample 4: Use of the retry statement

  - Sample 5: Exception thrown inside a transaction

  - Sample 6: throw Global::error with a SysInfoAction parameter

## Sample 1: Display Exceptions in the Infolog

This X++ code sample shows that a direct throw of Exception::Error does not display a message in the **Infolog**. That is why we recommend the Global::error method.

```X++
    static void TryCatchThrowError1Job(Args _args)
    {
    /***
      The 'throw' does not directly add a message to the Infolog.
      The exception is caught.
    ***/
        ;
        try
        {
            info("In the 'try' block. (j1)");
            throw Exception::Error;
        }
        catch (Exception::Error)
        {
            info("Caught 'Exception::Error'.");
        }
    /**********  Actual Infolog output
    Message (03:43:45 pm)
    In the 'try' block. (j1)
    Caught 'Exception::Error'.
    **********/
    }
```

## Sample 2: error Method to Write Exception to Infolog

The sample shows that use of the Global::error method is a reliable way to display exceptions in the **Infolog**.

```X++
    static void TryCatchGlobalError2Job(Args _args)
    {
    /***
      The 'Global::error()' does directly add a message to the Infolog.
      The exception is caught.
    ***/
        ;
        try
        {
            info("In the 'try' block. (j2)");
            throw Global::error("Written to the Infolog.");
        }
        catch (Exception::Error)
        {
            info("Caught 'Exception::Error'.");
        }
    /**********  Actual Infolog output
    Message (03:51:44 pm)
    In the 'try' block. (j2)
    Written to the Infolog.
    Caught 'Exception::Error'.
    **********/
    }
```

## Sample 3: Handle a CLRError

This sample shows that a CLRError exception is not displayed in the **Infolog** (unless you catch the exception and manually call the info method). The use of the CLRInterop::getLastException method is also demonstrated.

```X++
    static void TryCatchCauseCLRError3Job(Args _args)
    {
    /***
      The 'netString.Substring(-2)' causes a CLRError,
    but it does not directly add a message to the Infolog.
      The exception is caught.
    ***/
        System.String netString = "Net string.";
        System.Exception netExcepn;
        ;
        try
        {
            info("In the 'try' block. (j3)");
            netString.Substring(-2); // Causes CLR Exception.
        }
        catch (Exception::Error)
        {
            info("Caught 'Exception::Error'.");
        }
        catch (Exception::CLRError)
        {
            info("Caught 'Exception::CLRError'.");
            netExcepn = CLRInterop::getLastException();
            info(netExcepn.ToString());
        }
    /**********  Actual Infolog output (truncated for display)
    Message (03:55:10 pm)
    In the 'try' block. (j3)
    Caught 'Exception::CLRError'.
    System.Reflection.TargetInvocationException: Exception has been thrown by the target of an invocation. ---> System.ArgumentOutOfRangeException: StartIndex cannot be less than zero.
    Parameter name: startIndex
       at System.String.InternalSubStringWithChecks(Int32 startIndex, Int32 length, Boolean fAlwaysCopy)
       at System.String.Substring(Int32 startIndex)
    
       at ClrBridgeImpl.InvokeClrInstanceMethod(ClrBridgeImpl* , ObjectWrapper* objectWrapper, Char* pszMethodName, Int32 argsLength, ObjectWrapper** arguments, Boolean* argsAreByRef, Boolean* isException)
    **********/
    }
```

For more information, see [How to: Catch Exceptions Thrown from CLR Objects](how-to-catch-exceptions-thrown-from-clr-objects.md).

## Sample 4: Use of the retry Statement

This sample shows how to use the retry statement. The print statements are included because retry causes earlier **Infolog** messages to be erased.

```X++
    static void TryCatchRetry4Job(Args _args)
    {
    /***
      Demonstration of 'retry'. The Infolog output is partially erased
    by 'retry', but the Print window is fully displayed.
    ***/
        Exception excepnEnum;
        int nCounter = 0;
        ;
        try
        {
            info("        .");
            print("        .");
            info("In the 'try' block, [" + int2str(nCounter) + "]. (j4)");
            print("In the 'try' block, [" + int2str(nCounter) + "]. (j4)");
            pause;
            nCounter++;
            if (nCounter >= 3) // Prevent infinite loop.
            {
                info("---- Will now throw a warning, which is not caught.");
                print("---- Will now throw a warning, which is not caught.");
                pause;
                throw Global::warning("This warning will not be caught. [" + int2str(nCounter) + "]");
            }
            else
            {
                info("Did not throw a warning this loop. [" + int2str(nCounter) + "]");
                print("Did not throw a warning this loop. [" + int2str(nCounter) + "]");
            }
            excepnEnum = Global::error("This error message is written to the Infolog.");
            throw excepnEnum;
        }
        catch (Exception::Error)
        {
            info("Caught 'Exception::Error'.");
            print("Caught 'Exception::Error'.");
            retry;
        }
        info("End of job.");
        print("End of job.");
        pause;
    /**********  Actual Infolog output
    Message (04:33:56 pm)
            .
    In the 'try' block, [2]. (j4)
    ---- Will now throw a warning, which is not caught.
    This warning will not be caught. [3]
    **********/
    }
```

## Sample 5: Exception Thrown Inside a Transaction

This sample uses three levels of try nesting to illustrate where an exception is caught when the exception is thrown inside a ttsBegin - ttsCommit transaction block.

```X++
    static void TryCatchTransaction5Job(Args _args)
    {
    /***
      Shows an exception that is thrown inside a ttsBegin - ttsCommit
    transaction block cannot be caught inside that block.
    ***/
        ;
        try
        {
            try
            {
                ttsbegin;
                try
                {
                    throw error("Throwing exception inside transaction.");
                }
                catch (Exception::Error)
                {
                    info("Catch_1: Unexpected, caught in 'catch' inside the transaction block.");
                }
                ttscommit;
            }
            catch (Exception::Error)
            {
                info("Catch_2: Expected, caught in the innermost 'catch' that is outside of the transaction block.");
            }
        }
        catch (Exception::Error)
        {
            info("Catch_3: Unexpected, caught in 'catch' far outside the transaction block.");
        }
        info("End of job.");
    /**********  Actual Infolog output
    Message (04:12:34 pm)
    Throwing exception inside transaction.
    Catch_2: Expected, caught in the innermost 'catch' that is outside of the transaction block.
    End of job.
    **********/
    }
```

## Sample 6: use Global::error with a SysInfoAction parameter

When your code throws an exception, your code can write messages to the **Infolog** window. You can make those **Infolog** messages more helpful by using the SysInfoAction class.

In the following X++ code sample, a SysInfoAction parameter is passed in to the Global::error method. The error method writes the message to the **Infolog**. When the user double-clicks the **Infolog** message, the SysInfoAction.run method is run. You can write code in the run method that helps to diagnose or fix the problem that caused the exception.

The object that is passed in to the Global::error method is constructed from a class that you write that extends SysInfoAction.

The following code sample is shown in two parts. The first part shows a job that calls the Global::error method, and then throws the returned value. An instance of the SysInfoAction\_PrintWindow\_Demo class is passed into the error method. The second part shows the SysInfoAction\_PrintWindow\_Demo class.

#### ![Aa893385.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa893385.collapse_all(en-us,AX.60).gif")Part 1: The Job that calls Global::error

```X++
    static void Job_SysInfoAction(Args _args)
    {
        ;
        try
        {
            throw Global::error
                ("Click me to make the Print window display."
                ,""
                ,new SysInfoAction_PrintWindow_Demo()
                );
        }
        catch
        {
            warning("Issuing a warning from the catch block.");
        }
    }
```

#### ![Aa893385.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa893385.collapse_all(en-us,AX.60).gif")Part 2: the SysInfoAction\_PrintWindow\_Demo class

```X++
    public class SysInfoAction_PrintWindow_Demo
        extends SysInfoAction
    {
        str m_sGreeting; // In classDeclaration.
    
        public str description()
        {
            ;
            return "Starts the Print Window for demonstration.";
        }
    
    
        public void run()
        {
            ;
            print("This appears in the Print window.");
            print(m_sGreeting);
            pause;
    
    /*********** Actual Infolog output
    Message (03:19:28 pm)
    Click me to make the Print window display.
    Issuing a warning from the catch block.
    ***************/
        }
    
    
        public container pack()
        {
            ;
            return ["Packed greeting."]; // Literal container.
        }
    
        public boolean unpack
            (container packedClass
            , Object object = null
            )
        {
            ;
            [m_sGreeting] = packedClass;
            return true;
        }
    }
```

## List of Exceptions

The exception literals shown in the following table are the values of the [Exception Enumeration](https://msdn.microsoft.com/en-us/library/gg882127\(v=ax.60\)).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Exception literal</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Break</p></td>
<td><p>Indicates that the user has pressed BREAK or CTRL+C.</p></td>
</tr>
<tr class="even">
<td><p>CLRError</p></td>
<td><p>Indicates that an error has occurred during the use of the common language runtime (CLR) functionality.</p></td>
</tr>
<tr class="odd">
<td><p>CodeAccessSecurity</p></td>
<td><p>Indicates that an error has occurred during the use of the CodeAccessPermission.demand method. For more information, see <a href="code-access-security.md">Code Access Security</a>.</p></td>
</tr>
<tr class="even">
<td><p>DDEerror</p></td>
<td><p>Indicates that an error occurred in the use of the DDE system class.</p></td>
</tr>
<tr class="odd">
<td><p>Deadlock</p></td>
<td><p>Indicates that there is a database deadlock because several transactions are waiting for each other.</p></td>
</tr>
<tr class="even">
<td><p>DuplicateKeyException</p></td>
<td><p>Indicates that an error has occurred in a transaction that is using Optimistic Concurrency Control. The transaction can be retried (use a retry statement in the catch block).</p></td>
</tr>
<tr class="odd">
<td><p>DuplicateKeyExceptionNotRecovered</p></td>
<td><p>Indicates that an error has occurred in a transaction that is using Optimistic Concurrency Control. The code will not be retried.</p>

> [!note]  
> <P>This exception cannot be caught inside a transaction.</P>

</td>
</tr>
<tr class="even">
<td><p>Error</p></td>
<td><p>Indicates that a fatal error has occurred. The transaction has been stopped.</p></td>
</tr>
<tr class="odd">
<td><p>Info</p></td>
<td><p>Holds a message for the user.</p>
<p>Do not throw an info exception.</p></td>
</tr>
<tr class="even">
<td><p>Internal</p></td>
<td><p>Indicates an internal error in the development system.</p></td>
</tr>
<tr class="odd">
<td><p>Numeric</p></td>
<td><p>Indicates that an error has occurred during the use of the str2int, str2int64, or str2num functions.</p></td>
</tr>
<tr class="even">
<td><p>Sequence</p></td>
<td><p>(TBD)</p></td>
</tr>
<tr class="odd">
<td><p>UpdateConflict</p></td>
<td><p>Indicates that an error has occurred in a transaction that is using Optimistic Concurrency Control. The transaction can be retried (use a retry statement in the catch block).</p></td>
</tr>
<tr class="even">
<td><p>UpdateConflictNotRecovered</p></td>
<td><p>Indicates that an error has occurred in a transaction that is using Optimistic Concurrency Control. The code will not be retried.</p>

> [!note]  
> <P>This exception cannot be caught within a transaction.</P>

</td>
</tr>
<tr class="odd">
<td><p>Warning</p></td>
<td><p>Indicates that something exceptional has happened. The user might have to take action, but the event is not fatal.</p>
<p>Do not throw a warning exception.</p></td>
</tr>
</tbody>
</table>


## See also

[Exception Handling for User Controls](exception-handling-for-user-controls.md)

[insert Table Method](insert-table-method.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

