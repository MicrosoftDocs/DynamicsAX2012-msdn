---
title: 'How to: Use COM to Open a Form'
TOCTitle: 'How to: Use COM to Open a Form'
ms:assetid: 877209f1-3a93-471f-9aa3-a92382d07a34
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ677292(v=AX.60)
ms:contentKeyID: 49384063
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# How to: Use COM to Open a Form 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

The Microsoft Dynamics AX client includes a COM interface that you can use to open a form. As a result, you can use COM to open a form from another application or from a script file. In addition, you can create a desktop shortcut that uses the script to open the form. For more information about COM and the Microsoft Dynamics AX client, see [Using COM to Open a Form from an Application](using-com-to-open-a-form-from-an-application.md).

## Using a .NET Application to Open a Form

The following steps show how to use COM to open a form from an application built by using the Microsoft .NET Framework. You can use the Dynamics AX COM object to open a form in the Microsoft Dynamics AX workspace. Beginning with Microsoft Dynamics AX 2012 R2, you can also specify the partition for the workspace. For more information about partitions, see [How to: Specify the Partition for the Form](how-to-specify-the-partition-for-the-form.md).

### To add a reference to the Dynamics AX Client Type Library

1.  In the **Solution Explorer** of Visual Studio, expand your project. Right-click on the project name and then click **References**.

2.  Click **Add Reference**. The **Add Reference** window appears.

3.  Click the **COM** tab, scroll down the list of components, click **Dynamics AX Client 1.0 Type Library**, and then click **OK**.

4.  AxClientLib is added to the list of references for your project. AxClientLib is the namespace for the .NET interop assembly. In a .NET application, you use the interop assembly to interact with the Dynamics AX COM object.

### To use the DynamicsAxApplication interface

1.  Add the AxClientLib namespace to your project.
    
    The following code example shows how to import the namespace to a C\# application.
    
    ``` csharp
    using AxClientLib;
    ```

2.  Create an instance of the DynamicsAxApplication interface.
    
    The following code example creates an instance of the DynamicsAxApplication interface.
    
    ``` csharp
    AxClientLib.DynamicsAxApplication axComClient = new AxClientLib.DynamicsAxApplication();
    ```

3.  Use the OpenMenuItem method of the DynamicsAxApplication interface to open the form. To specify the form, you supply a company name, the name of a menu item, and the type of the menu item.
    
    The following code example shows how to use OpenMenuItem. Notice how the method parameters specify a company name, a menu item, and that the menu item is a Display type. AxMenuType is an enumeration found in the AxClientLib namespace.
    
    ``` csharp
    axComClient.OpenMenuItem("CEU", "CustTableListPage", AxClientLib.AxMenuType.DisplayMenu);
    ```

## Using a Shortcut to Open a Form

You can also use COM in a script file that can open a specified form. This enables you to create a desktop shortcut that opens a frequently used form. The following steps show how to create a script file and how to create a desktop shortcut that opens a form.

### To use the DynamicsAx.Application interface

1.  Use a text editor to create a file for your script. Specify the name and type of your script file.
    
    For example, create a file that is named **OpenAxMenuItem.vbs**.

2.  Create an instance of the DynamicsAx.Application interface.
    
    The following code example uses CreateObject to create the DynamicsAx.Application interface.
    
      ```VBScript
       Set objDynamicsAx = CreateObject("DynamicsAx.Application")
      ```

3.  To open a form, use the OpenMenuItem method of the DynamicsAx.Application interface. The method requires that you specify a company, a menu item, and the type of the menu item.
    
    The following code example uses VBScript to open a form. Notice how the script enables you to specify the company, menu item, and menu item type with the command line arguments. Also notice how the command line values are used with the OpenMenuItem method.

    ```VBScript

        '--------------------------------------------------
        '
        'Opens the Dynamics Ax Menu Item that was specified.
        '
        'Usage:
        '    openAxMenu -c <companycode> {-d "<displaymenu>" | -a "<actionmenu>" | -o "<outputmenu>"}
        '    openAxMenu [-help|-?]
        '
        '--------------------------------------------------
        
        Option Explicit
        
        Dim objDynamicsAx, oArgs, ArgNum
        Dim companyName, displayMenuName, actionMenuName, outputMenuName
        
        Set oArgs = WScript.Arguments
        ArgNum = 0
        companyName=""
        displayMenuName=""
        actionMenuName=""
        outputMenuName=""
        
        While ArgNum < oArgs.Count
            Select Case LCase(oArgs(ArgNum))
                Case "-c":
                    ArgNum = ArgNum + 1
                    companyName = oArgs(ArgNum)
                Case "-d":
                    ArgNum = ArgNum + 1
                    displayMenuName = oArgs(ArgNum)
                Case "-a":
                    ArgNum = ArgNum + 1
                    actionMenuName = oArgs(ArgNum)
                Case "-o":
                    ArgNum = ArgNum + 1
                    outputMenuName = oArgs(ArgNum)
                Case "-help","-?":
                    Call DisplayUsage
                Case Else:
                    Call DisplayUsage
            End Select
            ArgNum = ArgNum + 1
        Wend
        
        If oArgs.Count = 0 Then
            Call DisplayUsage
        ElseIf (displayMenuName="" And actionMenuName="" And outputMenuName="") Then
            WScript.Echo "ERROR: You must specify the menu item to launch"
            Call DisplayUsage
        Else
           Set objDynamicsAx = CreateObject("DynamicsAx.Application")
            If displayMenuName <> "" Then
                 objDynamicsAx.OpenMenuItem companyName, displayMenuName, 1
            ElseIf actionMenuName <> "" Then
                 objDynamicsAx.OpenMenuItem companyName, actionMenuName, 3
            ElseIf outputMenuName <> "" Then
                objDynamicsAx.OpenMenuItem companyName, outputMenuName, 2
            End If
        End If
        
        'Display the usage for this script
        'Usage:
        '    openAxMenu -c <companycode> {-d "<displaymenu>" | -a "<actionmenu>" | -o "<outputmenu>"}
        '    openAxMenu [-help|-?]
        Sub DisplayUsage
            WScript.Echo "Usage:"
            WScript.Echo "  openAxMenu.vbs [-c <companyCode>] {-d " & _
               Chr(34) & "<displayMenuItemName>" & Chr(34) & " | -a " & _
               Chr(34) & "<actionMenuItemName>" & Chr(34) & " | -o " & _
               Chr(34) & "<outputMenuItemName>" & Chr(34) & "}"
            WScript.Echo "  openAxMenu [-help|-?]"
            WScript.Echo ""
            WSCript.Quit
        End Sub
       ```

4.  Save the file.

### To create a desktop shortcut that runs the script

1.  Right-click the desktop where you want to add the shortcut. Click **New** and then click **Shortcut**. The **Create Shortcut** window appears.

2.  In the **Type the location of the item** box, type the name of the script file that you created. Include the path of the folder where you put the script file. Add the command line parameters. Click **Next**.
    
    The following example uses a script file to open the **Customers** form. The shortcut uses the script from the previous procedure that was saved to a file that is named OpenAxMenu.vbs. Notice how command line arguments are used to specify the company, the menu item, and the menu item type. In the example, –d specifies that the menu item is a Display menu item.
    
        C:\Users\LocalUser\Desktop\OpenAxMenu.vbs –c CEU –d "CustTable"

3.  In the **Type a name for this shortcut** box, type the name for the shortcut. Click **Finish**.
    
    For example, type **View Customer** to specify the form that opens when you double-click the shortcut.

4.  To open the form, double-click the shortcut.

## See also

[Dynamics AX Client Type Library Reference](dynamics-ax-client-type-library-reference.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

