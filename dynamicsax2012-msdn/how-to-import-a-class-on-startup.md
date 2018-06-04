---
title: 'How to: Import a Class on Startup'
TOCTitle: 'How to: Import a Class on Startup'
ms:assetid: 28908472-eaff-4ff4-bf11-3a13740dd925
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa496462(v=AX.60)
ms:contentKeyID: 35589494
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- xml
---

# How to: Import a Class on Startup 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can import a class, and execute methods within it without user interaction by starting Microsoft Dynamics AX from the command line with an XML file as input parameter. The XML file specifies the class and methods to use. The result of importing and executing is written to a log file or shown to the user in Infolog.

Executing with no user interaction is useful for any automation of customer tasks, in particular during the test phase.

## Create an XML file

1.  On the Microsoft Dynamics AX client computer, create an XML file.

2.  Add tags to the XML file specifying:
    
      - The Microsoft Dynamics AX version.
    
      - The name and location of the log file.
    
      - The XPO file that contains the class to import.
    
      - The method to run.
        

        > [!NOTE]
        > <P>The XML file syntax is described in the documentation for the <A href="https://msdn.microsoft.com/en-us/library/gg922801(v=ax.60)">SysAutoRun Class</A>.</P>



3.  Open a command line window and type
    
    **ax32.exe -StartupCmd=AutoRun\_** c:\\folder\\filename **.XML**

## Sample XML file

The following example shows an XML file that can be used to import data silently.

``` xml
<AxaptaAutoRun version="6.0" logFile="AXAutoCreateClass.log">
  <XpoImport file="d:\share\CreateClass.xpo" />
  <Run type="class" name="CreateClass" method="main" />
</AxaptaAutoRun>
```

## See also

[Run the checklist items without user interaction](https://msdn.microsoft.com/en-us/library/aa497052\(v=ax.60\))

[How to: Import Data on Startup](how-to-import-data-on-startup.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

