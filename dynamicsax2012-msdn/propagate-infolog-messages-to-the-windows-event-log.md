---
title: Propagate Infolog Messages to the Windows Event Log
TOCTitle: Propagate Infolog Messages to the Windows Event Log
ms:assetid: 5de76b18-cfad-459b-b6d2-28c6bcf4d733
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg845722(v=AX.60)
ms:contentKeyID: 35244410
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- xml
- csharp
---

# Propagate Infolog Messages to the Windows Event Log 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how you can propagate Microsoft Dynamics AX Infolog messages to the Windows Event Log. A .NET C\# sample program is provided to show how you can read those messages from the Event Log.

To propagate Infolog messages, edit the AX32.exe.config XML file to add listeners from the .NET System.Diagnostics namespace. One listener that you can add is the EventLogTraceListener. After you add this listener, all messages that are written to the Infolog are also written to the Windows Event Log. Your .NET program can search the Windows Event Log for messages that have the source name of Dynamics Infolog.

## XML for Infolog Listeners

You can copy the whole \<system.diagnostics\> section of following XML code into your AX32.exe.config file. The AX32.exe program reads the config file each time the program is restarted.

``` xml
<configuration>

  <system.diagnostics>
    <trace autoflush="true"/>
    <sources>
      <source name="Microsoft.Dynamics.Kernel.Client.DiagnosticLog-Infolog"
              switchValue="Information">
        <listeners>
          <add name="EventLog" 
               type="System.Diagnostics.EventLogTraceListener" 
               initializeData="Dynamics Infolog"/>
          <add name="TextFile" 
               type="System.Diagnostics.TextWriterTraceListener" 
               initializeData="DynamicsInfologTrace.log" 
               traceOutputOptions="DateTime"/>
        </listeners>
      </source>
    </sources>
  </system.diagnostics>

</configuration>
```

 


> [!NOTE]
> <P>The AX32.exe.config file is located in the same client bin directory where AX32.exe is located. The whole path might be as follows:</P>
> <P>C:\Program Files (x86)\Microsoft Dynamics AX\&lt;versionNumber&gt;\Client\Bin\</P>



### ![Gg845722.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845722.collapse_all(en-us,AX.60).gif")XML Attributes

In the previous XML, each \<add\> element defines a separate listener. For information about the attributes on the \<add\> element, see [\<add\> Element for \<listeners\> for \<trace\>](http://go.microsoft.com/fwlink/?linkid=169516) on the Microsoft Developer Network (MSDN).

## C\# Code Sample

The following C\# code sample obtains Infolog messages from the Windows Event Log. The messages were copied from the Infolog to the Windows Event Log by the EventLogTraceListener that is mentioned in the previous XML.

``` csharp
using           System;
using SysCGen = System.Collections.Generic;
using SysDiag = System.Diagnostics;

namespace EventLogSnooperNs
{
    class EventLogSnooper
    {
        static void Main(string[] args)
        {
            SysDiag.EventLog eventLog;
            SysCGen.SortedDictionary<int, SysDiag.EventLogEntry>
                    sortedEventEntries = new SysCGen.SortedDictionary
                    <int, SysDiag.EventLogEntry>();
            int sampleCounter = 0;
            //------ End of variable declarations. --------

            eventLog = new SysDiag.EventLog();
            eventLog.Log = "Application";

            for (int kk=0; kk < eventLog.Entries.Count; kk++)
            {
                sortedEventEntries.Add
                    (eventLog.Entries[kk].Index,
                    eventLog.Entries[kk]);
            }

            for (int ii = sortedEventEntries.Keys.Count - 1; ii > 0; ii--)
            {
                if (eventLog.Entries[ii].Source != "Dynamics Infolog")
                    { continue; }
                Console.WriteLine("- - - - - - - - - - - - - -");
                Console.WriteLine("EntryType == {0}", eventLog.Entries[ii].EntryType);
                Console.WriteLine("Index == {0}", eventLog.Entries[ii].Index);
                Console.WriteLine("Source == {0}", eventLog.Entries[ii].Source);
                Console.WriteLine("TimeGenerated == {0}", eventLog.Entries[ii].TimeGenerated);
                Console.WriteLine("Message == {0}", eventLog.Entries[ii].Message);
                if (++sampleCounter >= 2)
                    { break; }
            }
            Console.WriteLine("- - - - - - - - - - - - - -");
        }
    }
}
```

### ![Gg845722.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845722.collapse_all(en-us,AX.60).gif")Actual Output to the Console

The following output was written to the console by the previous C\# program.

    [C:\VS\EventLogSnooper\EventLogSnooper\bin\Debug\]
    >> EventLogSnooper.exe
    - - - - - - - - - - - - - -
    EntryType == Error
    Index == 9705
    Source == Dynamics Infolog
    TimeGenerated == 11/2/2009 2:40:29 PM
    Message == Test, error mesg to Infolog.
    - - - - - - - - - - - - - -
    EntryType == Warning
    Index == 9704
    Source == Dynamics Infolog
    TimeGenerated == 11/2/2009 2:40:29 PM
    Message == Test, warning mesg to Infolog.
    - - - - - - - - - - - - - -
    
    [C:\VS\EventLogSnooper\EventLogSnooper\bin\Debug\]
    >>

## See also

[Integration with Microsoft Dynamics AX](integration-with-microsoft-dynamics-ax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

