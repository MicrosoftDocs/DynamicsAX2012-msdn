---
title: 'How to: Update Data Using .NET Business Connector'
TOCTitle: 'How to: Update Data Using .NET Business Connector'
ms:assetid: 6402883a-5ee6-4b22-8d5a-067c9e89ea8a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc197114(v=AX.60)
ms:contentKeyID: 35244673
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# How to: Update Data Using .NET Business Connector 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Using .NET Business Connector, you can access Microsoft Dynamics AX data or business logic from a .NET-connected application. The following example provides the code to update data in a Microsoft Dynamics AX table. For a complete working example, see [Walkthrough: Integrate an Application with Microsoft Dynamics AX Using .NET Business Connector](walkthrough-integrate-an-application-with-microsoft-dynamics-ax-using-net-business-connector.md).

## Adding a Reference to .NET Business Connector

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



## Updating a Record

In this section, you will create a query and retrieve the record using the forupdate command so that the record can be updated. You can replace the table name and record to fit your needs. You will use a where clause in your query to select a CustStatisticsGroup record and update one of the StatGroupName records to Premium Customer.

### To update a record

1.  Add the following using statement.
    
    ``` csharp
    using Microsoft.Dynamics.BusinessConnectorNet;
    ```

2.  Add the following code to update a record.
    
    ``` csharp
    Axapta ax;
    AxaptaRecord axRecord;
    string tableName = "CustStatisticsGroup";
    try
    {
        // Login to Microsoft Dynamics AX.
        ax = new Axapta();
        ax.Logon(null, null, null, null);
        // Update the ‘High Priority Customer’    table record.
        using (axRecord = ax.CreateAxaptaRecord(tableName))
        {
    　
            // Execute a query to retrieve an editable record where the StatGroupName is “High Priority Customer”.
            axRecord.ExecuteStmt("select forupdate * from %1 where %1.CustStatisticsGroup =='01'");
            // If the record is found then update the record.
            if (axRecord.Found)
            {
                // Start a transaction that can be committed.
                ax.TTSBegin();
                axRecord.set_Field("StatGroupName", "Priority Customer");
    axRecord.Update();
                // Commit the transaction.
                ax.TTSCommit();
            }
        }
    }
    catch (Exception e)
    {
        Console.WriteLine("Error encountered: {0}", e.Message);
        // Take other error action as needed.
    }
    ```

To see the record added in the table, go to **AOT** \> **Data Dictionary** \> **Tables**, right-click **CustStatisticsGroup**, and then click **Open**. Click the green execute button to execute the SQL statement. The first group has been updated to **Priority Customer**.

You can also create, read, and delete Microsoft Dynamics AX data. For more information, see [How to: Create Data Using .NET Business Connector](how-to-create-data-using-net-business-connector.md), [How to: Read Data Using .NET Business Connector](how-to-read-data-using-net-business-connector.md), and [How to: Delete Data Using .NET Business Connector](how-to-delete-data-using-net-business-connector.md). You may want to call X++ business logic in addition to accessing data. For more information, see [How to: Call Business Logic Using .NET Business Connector](how-to-call-business-logic-using-net-business-connector.md).

## See also

[Walkthrough: Integrate an Application with Microsoft Dynamics AX Using .NET Business Connector](walkthrough-integrate-an-application-with-microsoft-dynamics-ax-using-net-business-connector.md)

[How to: Call Business Logic Using .NET Business Connector](how-to-call-business-logic-using-net-business-connector.md)

[Axapta](https://msdn.microsoft.com/en-us/library/aa548601\(v=ax.60\))

[AxaptaRecord](https://msdn.microsoft.com/en-us/library/aa548861\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

