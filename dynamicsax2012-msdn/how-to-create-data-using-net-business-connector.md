---
title: 'How to: Create Data Using .NET Business Connector'
TOCTitle: 'How to: Create Data Using .NET Business Connector'
ms:assetid: cc1c6ee5-d78b-4115-8cc2-ad4e8bdcec70
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa868997(v=AX.60)
ms:contentKeyID: 35251573
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# How to: Create Data Using .NET Business Connector 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Using .NET Business Connector, you can access Microsoft Dynamics AX data or business logic from a .NET-connected application. The following example provides the code to create data in a Microsoft Dynamics AX table. For a complete working example, see [Walkthrough: Integrate an Application with Microsoft Dynamics AX Using .NET Business Connector](walkthrough-integrate-an-application-with-microsoft-dynamics-ax-using-net-business-connector.md).

## Procedures

### ![Aa868997.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa868997.collapse_all(en-us,AX.60).gif")Adding a Reference to .NET Business Connector

This example assumes that you have a project in which you want to access Microsoft Dynamics AX data. You must create a connection using .NET Business Connector. In this section, you will add a reference to the .NET Business Connector assembly.

### To add a reference to .NET Business Connector

1.  In Solution Explorer, right-click **References**, and then click **Add Reference**.

2.  In the **Add Reference** window, click the **Browse** tab.

3.  Specify the location of Microsoft.Dynamics.BusinessConnectorNet.dll, and then click **Add**.
    

    > [!NOTE]
    > <P>For a typical install, the assembly is located at C:\Program Files (x86)\Microsoft Dynamics AX\60\Client\Bin\.</P>



4.  Click **OK**.

### To set the project target framework

1.  In Solution Explorer, right-click your application project, and then click **Properties**.

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



### ![Aa868997.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa868997.collapse_all(en-us,AX.60).gif")Creating a Record

In this section, you will add code to create a record in a Microsoft Dynamics AX table. You will log on to Microsoft Dynamics AX using the [Axapta](https://msdn.microsoft.com/en-us/library/aa548601\(v=ax.60\)) class. This example adds a record to the CustStatisticsGroup table called MyState.

### To create a record

1.  Add a using statement to the referenced .NET Business Connector assembly.
    
    ``` csharp
    using Microsoft.Dynamics.BusinessConnectorNet;
    ```

2.  Add the following code to add a record.
    
    ``` csharp
    // Create the .NET Business Connector objects.
    Axapta ax;
    AxaptaRecord axRecord;
    string tableName = "CustStatisticsGroup";
    
    try
    {
        // Login to Microsoft Dynamics AX.
        ax = new Axapta();
        ax.Logon(null, null, null, null);
    
        // Create a new CustStatisticsGroup table record.
        using (axRecord = ax.CreateAxaptaRecord(tableName))
        {
            // Provide values for each of the CustStatisticsGroup record fields.
            axRecord.set_Field("CustStatisticsGroup", "04");
            axRecord.set_Field("StatGroupName", "No Priority Customer");
    
            // Commit the record to the database.
            axRecord.Insert();
        }
    }
    catch (Exception e)
    {
        Console.WriteLine("Error encountered: {0}", e.Message);
        // Take other error action as needed.
    }
    ```

To see the record added in the table, go to **AOT** \> **Data Dictionary** \> **Tables**, right-click **CustStatisticsGroup**, and then click **Open**. Click the green execute button to execute the SQL statement. The new **No Priority Customer** group is added to the table.

## Next Steps

You can also read, update, and delete Microsoft Dynamics AX data. For more information, see [How to: Read Data Using .NET Business Connector](how-to-read-data-using-net-business-connector.md), [How to: Update Data Using .NET Business Connector](how-to-update-data-using-net-business-connector.md), and [How to: Delete Data Using .NET Business Connector](how-to-delete-data-using-net-business-connector.md). You may want to call X++ business logic in addition to accessing data. For more information, see [How to: Call Business Logic Using .NET Business Connector](how-to-call-business-logic-using-net-business-connector.md).

## See also

[Walkthrough: Integrate an Application with Microsoft Dynamics AX Using .NET Business Connector](walkthrough-integrate-an-application-with-microsoft-dynamics-ax-using-net-business-connector.md)

[How to: Call Business Logic Using .NET Business Connector](how-to-call-business-logic-using-net-business-connector.md)

[Axapta](https://msdn.microsoft.com/en-us/library/aa548601\(v=ax.60\))

[AxaptaRecord](https://msdn.microsoft.com/en-us/library/aa548861\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

