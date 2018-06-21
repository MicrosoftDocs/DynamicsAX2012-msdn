---
title: 'How to: Call Business Logic Using .NET Business Connector'
TOCTitle: 'How to: Call Business Logic Using .NET Business Connector'
ms:assetid: a730bea1-809c-43ed-a326-16d221008807
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa851743(v=AX.60)
ms:contentKeyID: 35248462
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# How to: Call Business Logic Using .NET Business Connector [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Using .NET Business Connector, you can access Microsoft Dynamics AX data or business logic from a .NET-connected application. This example shows how to use.NET Business Connector to call the Microsoft Dynamics AX class static method. For a complete working example, see [Walkthrough: Integrate an Application with Microsoft Dynamics AX Using .NET Business Connector](walkthrough-integrate-an-application-with-microsoft-dynamics-ax-using-net-business-connector.md).

## Procedures

### ![Aa851743.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa851743.collapse_all(en-us,AX.60).gif")Adding a Reference to .NET Business Connector

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



### ![Aa851743.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa851743.collapse_all(en-us,AX.60).gif")Adding Code to Call a Method

In this section, you will add code to call a Microsoft Dynamics AX method. This example calls the static labelId2String2 method of the SysLabel class.

### To add code to call a method

  - Add the following code.
    
    ``` csharp
    using System;
    using Microsoft.Dynamics.BusinessConnectorNet;
    
    namespace BCNetSample1
    {
        /// <summary>
        /// This sample uses the .NET Business Connector to 
        /// call a Microsoft Dynamics AX class static method.
        /// </summary>
        class Class1
        {
            
            [STAThread]
            static void Main(string[] args)
            {
                // Create the .NET Business Connector objects.
                Axapta ax;
                string sID = "@SYS21669";
                object o;
                bool b;
    
                try
                {
                    // Login to Microsoft Dynamics Ax.
                    ax = new Axapta();
                    ax.Logon(null, null, null, null);
    
                }
                catch (Exception e)
                {
                    Console.WriteLine("An error occurred in object creation 
                        or Axapta logon: {0}", e.Message);
                    return;
                }
    
                // Logon was successful.
                try
                {
                    // Call a static class method.
                    // In this example, call SysLabel::labelId2String2 
                    // to determine the label string for a particular label ID.
                    o = ax.CallStaticClassMethod("SysLabel", 
                        "labelId2String2", sID);
                }
                catch (Exception e)
                {
                    Console.WriteLine("An error has been encountered during 
                        CallStaticClassMethod: {0}", e.Message);
                    b = ax.Logoff();
                    return;
                }
    
                // Display the returned string.
                Console.WriteLine("The label string for {0} is {1}.", 
                    sID, o.ToString());
                Console.WriteLine("Press any key to continue.");
                Console.ReadLine();
    
                // Log off from Microsoft Dynamics AX.
                b = ax.Logoff();
            }
        }
    }
    ```
    

    > [!NOTE]
    > <P>The console window will open with the following text:</P>
    > <P><STRONG>The label string for @SYS21669 is ABC.</STRONG></P>
    > <P><STRONG>Press any key to continue.</STRONG></P>



You can also create, read, update, and delete Microsoft Dynamics AX data. For more information, see [How to: Create Data Using .NET Business Connector](how-to-create-data-using-net-business-connector.md), [How to: Read Data Using .NET Business Connector](how-to-read-data-using-net-business-connector.md), [How to: Update Data Using .NET Business Connector](how-to-update-data-using-net-business-connector.md), and [How to: Delete Data Using .NET Business Connector](how-to-delete-data-using-net-business-connector.md).

## See also

[Walkthrough: Integrate an Application with Microsoft Dynamics AX Using .NET Business Connector](walkthrough-integrate-an-application-with-microsoft-dynamics-ax-using-net-business-connector.md)

[How to: Debug X++ Code Running in .NET Business Connector](how-to-debug-x-code-running-in-net-business-connector.md)

[How to: Create Data Using .NET Business Connector](how-to-create-data-using-net-business-connector.md)

[Axapta](https://msdn.microsoft.com/en-us/library/aa548601\(v=ax.60\))

[AxaptaRecord](https://msdn.microsoft.com/en-us/library/aa548861\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

