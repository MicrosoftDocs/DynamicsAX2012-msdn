---
title: 'Walkthrough: Integrate an Application with Microsoft Dynamics AX Using .NET Business Connector'
TOCTitle: 'Walkthrough: Integrate an Application with Microsoft Dynamics AX Using .NET Business Connector'
ms:assetid: 23e881cd-48f9-48c5-9bea-bbace5d692ef
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb931177(v=AX.60)
ms:contentKeyID: 35241596
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Walkthrough: Integrate an Application with Microsoft Dynamics AX Using .NET Business Connector [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Microsoft Dynamics AX development environment enables you to integrate a .NET application with Microsoft Dynamics AX. This feature gives developers a way to develop integrations using Microsoft Visual Studio. The ability to integrate Microsoft Dynamics AX with other systems is a common requirement. There are a variety of technologies that you can use to integrate Microsoft Dynamics AX with other applications, which include .NET Business Connector. The following table describes the suggested ways to integrate with Microsoft Dynamics AX in different scenarios.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Technology</p></th>
<th><p>Intended Use</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>.NET Business Connector</p></td>
<td><p>Author business logic using a .NET language. For more information, see <a href="net-business-connector-overview.md">.NET Business Connector Overview</a>.</p></td>
</tr>
<tr class="even">
<td><p>Services</p></td>
<td><p>Access Microsoft Dynamics AX data and functionality. For more information, see <a href="https://msdn.microsoft.com/en-us/library/hh509053(v=ax.60)">Developing with Services and AIF</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Common language runtime (CLR)</p></td>
<td><p>Create and execute managed components from X++ code. For more information, see <a href="net-interop-from-x.md">.NET Interop from X++</a>.</p></td>
</tr>
</tbody>
</table>


This walkthrough illustrates the following tasks:

  - Creating a C\# Windows project

  - Adding a reference to .NET Business Connector

  - Creating the layout for a form

  - Adding code behind the form

  - Retrieving a record using a where clause

## Prerequisites

To complete this walkthrough, you will need:

  - Microsoft Dynamics AX with data in the **CustTrans** table

  - Microsoft Visual Studio 2010

  - 4.0 .NET Framework
    

    > [!NOTE]
    > <P>This topic contains steps to use the 4.0 .NET Framework. You can use an earlier version of the .NET Framework but the project target framework setting and application configuration settings need to be updated accordingly.</P>



## Creating a C\# Windows Project

The first step is to create a Windows application that will access data in Microsoft Dynamics AX.

### To create a C\# Windows project

1.  Open Visual Studio.

2.  From the **File** menu, click **New**, and then click **Project** to display the **New Project** dialog box.

3.  In the **Installed Templates** pane, click **Visual C\#**. In the **Templates** pane, click **Windows Forms Application**.

4.  Set the name to DisplayCustTransAccountNum.

5.  To change the location of the solution directory, click **Browse**, and specify a new location.

6.  Click **OK**.

## Adding a Reference to .NET Business Connector

To access Microsoft Dynamics AX data and functionality, you must create a connection between a .NET application and Microsoft Dynamics AX using .NET Business Connector. In this section, you will add a reference to the .NET Business Connector assembly, update the target framework, and update the application configuration settings. For more information assemblies, see [How the Runtime Locates Assemblies](http://go.microsoft.com/fwlink/?linkid=227042).

### To add a reference to .NET Business Connector

1.  In Solution Explorer, right-click **References**, and then click **Add Reference**.

2.  In the **Add Reference** window, click the **Browse** tab.

3.  Specify the location of Microsoft.Dynamics.BusinessConnectorNet.dll, and then click **Add**.
    

    > [!NOTE]
    > <P>For a typical install, the assembly is located at C:\Program Files (x86)\Microsoft Dynamics AX\60\Client\Bin\.</P>



4.  Click **OK**.

### To set the project target framework

1.  In Solution Explorer, right-click the DisplayCustTransAccountNum project, and then click **Properties**.

2.  In the **Application** tab, set the **Target framework** to **.NET Framework 4**.

### To update the application configuration settings

1.  In Solution Explorer, double-click the app.config file and update the following configuration settings.
    
        <startup useLegacyV2RuntimeActivationPolicy=”true”>
        <supportedRuntime version “v4.0” />

2.  On the **File** menu, click **Save app.config**.
    

    > [!NOTE]
    > <P>When you build your project, the development environment automatically creates a copy of your app.config file, changes its file name so that it has the same file name as your executable, and then moves the new .config file in the bin directory.</P>
    > <P>If you do not update the app.config file, you will get the following error:</P>
    > <P>“Mixed mode assembly is built against version 'v2.0.50727' of the runtime and cannot be loaded in the 4.0 runtime without additional configuration information.”</P>



## Creating the Layout of the Form

After you have created DisplayCustTransAccountNum, you can add controls to the form by dragging them from the toolbox.

### To create the layout a form

1.  In the toolbox, click the **Label** control, and then add it to the form.

2.  Click the **TextBox** control and add it to the form next to the **Label**.

3.  Click **Button** and add it to the form next to the **TextBox**.

## Adding Code Behind the Form

In this section, you will add code behind the form to extract the data from Microsoft Dynamics AX. You will use the [AxaptaRecord](https://msdn.microsoft.com/en-us/library/aa548861\(v=ax.60\)) class to execute a query. This query will extract data from Microsoft Dynamics AX. You will retrieve and display customer data on the controls that you have added to the Windows form.

### To add code behind the form

1.  On the form, double-click **button1** to access the **Form1** code.

2.  Add the following code to the **button1\_Click** method.
    
    ``` csharp
    Microsoft.Dynamics.BusinessConnectorNet.Axapta DynAx = new 
        Microsoft.Dynamics.BusinessConnectorNet.Axapta();
    Microsoft.Dynamics.BusinessConnectorNet.AxaptaRecord DynRec;
    try
    {
        // Authenticate the user and establish a session.
        DynAx.Logon(null, null, null, null);
    
        // Define the record as the CustTrans table.
        DynRec = DynAx.CreateAxaptaRecord("CustTrans");
    
        // Define the query that will run on the CustTrans records.
        // This will return all the data in the CustTrans table with 
        // the cursor positioned at the first record in the table.
        DynRec.ExecuteStmt("select * from %1");
    
        // Check if the query returned any data.
        if(DynRec.Found)
        {
            // Display the record on the form that was retrieved from the query.
            textBox1.Text = (string) DynRec.get_Field("AccountNum");
        }
    }
    // In a finally block, log the user off.
    finally
    {
        DynAx.Logoff();
    }
    ```

3.  Press F5 to run the application.

4.  On the form, click **button1**. The text box displays the first AccountNum record in your CustTrans table.

5.  Close the form.


> [!WARNING]
> <P>An instance of the Axapta class must not be given to a second thread.</P>



## Retrieving a Record Using a Where Clause

In this section, you will modify the code to look for a specific record. You will use a where clause to find a record in your CustTrans table. In the following example you will replace the ' your\_search\_criteria\_here ' with the name of a record in your CustTrans table, for example **1103** .

### To retrieve a record using a where clause

1.  On the form, double-click **button1** to access the **Form1** code.

2.  Declare the following variable.
    
    ``` csharp
    string fieldAccountNum = ("AccountNum");
    ```

3.  Change the execute statement to include a where clause.
    
    ``` csharp
    DynRec.ExecuteStmt(string.Format("select * from %1 where %1.{0} ==
        'your_search_criteria_here'", fieldAccountNum));
    ```

4.  Press F5 to run the application.

5.  On the form, click **button1**. The text box displays the record for the criteria you supplied, like **1103**.

## Next Steps

This topic demonstrates how to access data in Microsoft Dynamics AX using .NET Business Connector. Using .NET Business Connector enables information technology (IT) departments and independent software vendors (ISV) to build .NET solutions and integrate them with Microsoft Dynamics AX. For more information, see [.NET Business Connector Overview](net-business-connector-overview.md).

## See also

[Integration with Microsoft Dynamics AX](integration-with-microsoft-dynamics-ax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

