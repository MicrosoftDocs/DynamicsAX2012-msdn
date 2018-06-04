---
title: 'How to: Connect to Microsoft Dynamics AX Using the LogonAs Method'
TOCTitle: 'How to: Connect to Microsoft Dynamics AX Using the LogonAs Method'
ms:assetid: e3ddf4ca-db37-41cc-9f84-eab78608af7b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb986590(v=AX.60)
ms:contentKeyID: 35253167
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# How to: Connect to Microsoft Dynamics AX Using the LogonAs Method 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the [LogonAs](https://msdn.microsoft.com/en-us/library/jj827477\(v=ax.60\)) method to connect to Microsoft Dynamics AX to implement a customized .NET-connected application. This example uses the [LogonAs](https://msdn.microsoft.com/en-us/library/jj827477\(v=ax.60\)) method to connect to the AOS using a specified proxy user account.

## Starting the AOS

In this section, you will ensure that the AOS status is **Started**.

### To start the AOS

1.  Click the **Start** menu, point at **Administrative Tools**, and then click **Services**.

2.  In the **Services** window, in the right pane find the AOS, the default install name is **Microsoft Dynamics AX Object Server 6.0$01-MicrosoftDynamicsAX**. Check the **Status**, it should be **Started**. If not, right-click **Microsoft Dynamics AX Object Server 6.0$01-MicrosoftDynamicsAX** and then click **Start**.

## Setting up the Proxy User

This example assumes that you have created a user to set up as a proxy user or you will use your own user ID, domain, and password. Microsoft Dynamics AX is not supported to run without a domain controller. In this section you will set up the proxy user.

### To set up the proxy user

1.  From the navigation pane, click **System administration** \> **Setup** \> **System** \> **System service accounts**.

2.  In the Business connector proxy area, enter the same user ID credentials that you will specify in the code. Fill in the alias with the user ID and the network domain that has a fully qualified domain name that the user ID is a part of.

## Creating a Project

In this section, you will create a Windows application that will access data in Microsoft Dynamics AX.

### To create a project

1.  Open Visual Studio.

2.  From the **File** menu, click **New**, and then click **Project** to display the **New Project** dialog box.

3.  In the **Project types** pane, click **Visual C\#**. In the **Templates** pane, click **Windows Forms Application**.

4.  Set the name to LogonAsExample.

5.  To change the location of the solution directory, click **Browse** and specify a new location.

6.  Click **OK**.

## Adding a Button to a Form

You can add controls to the form by dragging them from the toolbox. In this example, you will add a button to the form which will be used to log on to Microsoft Dynamics AX.

### To create the layout a form

  - In the **Toolbox**, double-click the **Button** control to add it to the form.

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



## Adding Code Behind the Form

In this section, you will use the [LogonAs](https://msdn.microsoft.com/en-us/library/jj827477\(v=ax.60\)) method to connect to Microsoft Dynamics AX on behalf of a specific user. This example specifies the proxy user. You will use a hard-coded string for the ProxyUserID and password that match the proxy that you specified in the Business Connector proxy.

### To add code behind the form

1.  On the form, double-click **button1** to access the **LogonAsExample.Form1** code.

2.  Add the following using statement to the **LogonAsExample.Form1** form.
    
    ``` csharp
    using Microsoft.Dynamics.BusinessConnectorNet;
    ```

3.  Add the following code on the click event of the button control.
    
    ``` csharp
    private void button1_Click(object sender, EventArgs e)
    {
        // Create an instance of the Axapta class.
        Axapta DynAx = new Axapta();
    
        // Add the proxy user.
        // Replace the ProxyUserID and password parameters with the 
        // proxy user name and password that you specified
        // in the Business Connector Proxy.
        System.Net.NetworkCredential nc = new System.Net.NetworkCredential("ProxyUserID", "password");
        string strUserName = "ProxyUserID";
    
        // Test the connection to the .NET Business Connector.
        try
        {
            DynAx.LogonAs(strUserName.Trim(), "", nc, "", "", "", "");
            MessageBox.Show("Success");
            DynAx.Logoff();
            MessageBox.Show("Logoff completed.");
    
        }
        catch (Exception ex)
        {
            MessageBox.Show(ex.ToString());
            MessageBox.Show(ex.Message);
        }
    }
    ```

4.  Press F5 to run the application.

5.  On the form, click **button1**. The message box displays **Success**. Click **OK**. The message box displays **Logoff completed**.

For more examples and information, see the [LogonAs](https://msdn.microsoft.com/en-us/library/jj827477\(v=ax.60\)) method reference content.

## See also

[Axapta](https://msdn.microsoft.com/en-us/library/aa548601\(v=ax.60\))

[Walkthrough: Integrate an Application with Microsoft Dynamics AX Using .NET Business Connector](walkthrough-integrate-an-application-with-microsoft-dynamics-ax-using-net-business-connector.md)

[.NET Business Connector Overview](net-business-connector-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

