---
title: 'How to: Import Data on Startup'
TOCTitle: 'How to: Import Data on Startup'
ms:assetid: 9fc7b678-ae7b-44d7-b261-abc7197335d6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa548627(v=AX.60)
ms:contentKeyID: 35589852
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- xml
---

# How to: Import Data on Startup [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can import data into Microsoft Dynamics AX without user interaction by starting Microsoft Dynamics AX from the command line with an XML file as an input parameter. The XML file specifies the data to be imported. Results are written to a log file or shown in the Infolog.

Running the import process without user interaction is particularly useful in test environments.

## Create an XML file

1.  On the Microsoft Dynamics AX client computer, create an XML file.

2.  Add tags to the XML file by entering the following parameters:
    
      - The Microsoft Dynamics AX version.
    
      - The name and location of the log file.
    
      - The data file to import, along with the appropriate attributes.
        

        > [!NOTE]
        > <P>The XML file syntax is described in the documentation for the <A href="https://msdn.microsoft.com/en-us/library/gg922801(v=ax.60)">SysAutoRun Class</A>.</P>



3.  Open a command prompt and type the following:
    
        ax32.exe -StartupCmd=AutoRun_c:\PathToFile\FileName.XML

## Sample XML input file

``` xml
<?xml version="1.0" encoding="utf-8" ?> 
<AxaptaAutoRun exitWhenDone="true" version="6.0" logFile="D:\AX\axautodata.log">
<CompanyAccounts>
<Company name="Demo Company" id="DMO" overwrite="true" />
</CompanyAccounts>
<DataImport companyId="DMO" file="\\ServerName\ShareName\DemoData.dat" />
</AxaptaAutoRun>
```

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

