---
title: 'How to: Read Data Using .NET Business Connector'
TOCTitle: 'How to: Read Data Using .NET Business Connector'
ms:assetid: fb2a4c7f-5347-4924-9994-c64257d80b17
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc197126(v=AX.60)
ms:contentKeyID: 35254195
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# How to: Read Data Using .NET Business Connector [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Using .NET Business Connector, you can access Microsoft Dynamics AX data or business logic from a .NET-connected application. The following example provides the code to read data in a Microsoft Dynamics AX table. For a complete working example, see [Walkthrough: Integrate an Application with Microsoft Dynamics AX Using .NET Business Connector](walkthrough-integrate-an-application-with-microsoft-dynamics-ax-using-net-business-connector.md).

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



## Reading a Record

In this section, you will execute a query to read records from the LogisticsAddressState table. You will use the [AxaptaRecord](https://msdn.microsoft.com/en-us/library/aa548861\(v=ax.60\)) class to create a query by calling the Axapta.CreateAxaptaRecord method. This returns the data by using the AxaptaRecord.Field property. The AxaptaRecord.Next method is used to iterate through the list of returned records so that you can display the records. This example displays the output in a console window.

### To read data

1.  Add the following using statement.
    
    ``` csharp
    using Microsoft.Dynamics.BusinessConnectorNet;
    ```

2.  Add the following code to read and display records.
    
    ``` csharp
    // Create the .NET Business Connector objects.
    Axapta ax;
    AxaptaRecord axRecord;
    string tableName = "LogisticsAddressState";
    
    // The LogisticsAddressState field names for calls to
    // the AxRecord.get_field method.
    string strNameField = "NAME";
    string strStateIdField = "STATEID";
    
    // The output variables for calls to the 
    // AxRecord.get_Field method.
    object fieldName, fieldStateId; 
    
    try
    {
        // Login to Microsoft Dynamics AX.
        ax = new Axapta();
        ax.Logon(null, null, null, null);
    
        // Create a query using the AxaptaRecord class
        // for the StateAddress table.
        using (axRecord = ax.CreateAxaptaRecord(tableName))
        {
    
            // Execute the query on the table.
            axRecord.ExecuteStmt("select * from %1");
    
            // Create output with a title and column headings
            // for the returned records.
            Console.WriteLine("List of selected records from {0}",
                tableName);
            Console.WriteLine("{0}\t{1}", strNameField, strStateIdField);
    
            // Loop through the set of retrieved records.
            while (axRecord.Found)
            {
                // Retrieve the record data for the specified fields.
                fieldName = axRecord.get_Field(strNameField);
                fieldStateId = axRecord.get_Field(strStateIdField);
    
                // Display the retrieved data.
                Console.WriteLine(fieldName + "\t" + fieldStateId);
    
                // Advance to the next row.
                axRecord.Next();
            }
    
            // Keep the console window open.
            System.Console.WriteLine("Press any key to exit.")
            System.Console.ReadKey();        
        }
    }
    
    catch (Exception e)
    {
        Console.WriteLine("Error encountered: {0}", e.Message);
        // Take other error action as needed.
    }
    ```

You will see the results in a console window when this code is executed. You can also, create, update, and delete Microsoft Dynamics AX data. For more information, see [How to: Create Data Using .NET Business Connector](how-to-create-data-using-net-business-connector.md), [How to: Update Data Using .NET Business Connector](how-to-update-data-using-net-business-connector.md), and [How to: Delete Data Using .NET Business Connector](how-to-delete-data-using-net-business-connector.md).You may want to call X++ business logic in addition to accessing data. For more information, see [How to: Call Business Logic Using .NET Business Connector](how-to-call-business-logic-using-net-business-connector.md).

## See also

[Walkthrough: Integrate an Application with Microsoft Dynamics AX Using .NET Business Connector](walkthrough-integrate-an-application-with-microsoft-dynamics-ax-using-net-business-connector.md)

[How to: Call Business Logic Using .NET Business Connector](how-to-call-business-logic-using-net-business-connector.md)

[Axapta](https://msdn.microsoft.com/en-us/library/aa548601\(v=ax.60\))

[AxaptaRecord](https://msdn.microsoft.com/en-us/library/aa548861\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

