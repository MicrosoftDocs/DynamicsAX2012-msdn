---
title: 'How to: Catch Exceptions Thrown from CLR Objects'
TOCTitle: 'How to: Catch Exceptions Thrown from CLR Objects'
ms:assetid: 032f8c77-fa84-4e54-bc37-a651ab1a301a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Ee677495(v=AX.60)
ms:contentKeyID: 35240221
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Catch Exceptions Thrown from CLR Objects 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, when your X++ code calls .NET framework methods it is important that your code be designed to handle exceptions. When your code catches exceptions it can relay valuable diagnostic information to the user.

## Processing a CLRException

The X++ code sample in this section calls methods that are in a .NET assembly. As we recommend, these calls are inside a try block.

To demonstrate the exception handling, the sample purposely tries to create a Windows event log source a second time, which causes a duplicate name. The duplicate causes the system to throw a .NET exception. The sample shows how to obtain detailed diagnostic information from that exception.

The sample has a catch block for the X++ enum value Exception::CLRError. In that catch block the following steps are taken:

1.  ClrInterop::getLastException is called.

2.  ex.get\_InnerException is called.

### ![Ee677495.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Ee677495.collapse_all(en-us,AX.60).gif")X++ Code Sample

The following X++ code sample demonstrates how to handle exceptions that are thrown from .NET methods.

    // X++
    static void JobCreateEventLog(Args _args)
    {
        #define.LogSource("Dynamics AX")
        #define.LogName("Dynamics AX Log")
        System.Exception ex;
        System.Diagnostics.EventLog eventLog;
        ;
        try
        {
            // Create the log if it does not already exist.
            if (!System.Diagnostics.EventLog::SourceExists(#LogSource))
            {
                System.Diagnostics.EventLog::CreateEventSource(#LogSource, #LogName);
            }
    
            // Next line is an intentional bug for this demonstration of CLR exceptions.
            // It causes an exception due to a name duplication.
            System.Diagnostics.EventLog::CreateEventSource(#LogSource, #LogName);
    
            // Write to this newly created log source, if the process gets this far.
            eventLog = new System.Diagnostics.EventLog();
            eventLog.set_Source(#LogSource);
            eventLog.WriteEntry
                ("The exception should prevent this line from appearing in the Windows event viewer.",
                System.Diagnostics.EventLogEntryType::Warning
                );
        }
        catch (Exception::CLRError)
        {
             ex = ClrInterop::getLastException();
             if (ex != null)
             {
                ex = ex.get_InnerException();
                if (ex != null)
                {
                    error(ex.ToString());
                }
            }
        }
        // Clean up.
        System.Diagnostics.EventLog::DeleteEventSource(#LogSource, #LogName);
    }
    /*** Messages displayed in the Infolog:
    System.ArgumentException: Source Dynamics AX already exists on the local computer.
       at System.Diagnostics.EventLog.CreateEventSource(EventSourceCreationData sourceData)
       at System.Diagnostics.EventLog.CreateEventSource(String source, String logName)
    ***/

## See also

[Exception Handling with try and catch Keywords](exception-handling-with-try-and-catch-keywords.md)

[.NET Interop from X++](net-interop-from-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

