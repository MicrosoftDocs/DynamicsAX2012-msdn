---
title: 'How to: Use Office Add-ins to Lock an Excel Spreadsheet'
TOCTitle: 'How to: Use Office Add-ins to Lock an Excel Spreadsheet'
ms:assetid: 32fbbaed-ef64-4303-9115-9ac7f83d002f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ677287(v=AX.60)
ms:contentKeyID: 49384058
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# How to: Use Office Add-ins to Lock an Excel Spreadsheet [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

With Microsoft Dynamics AX 2012 R2, you can use an API in the Office Add-ins for Microsoft Dynamics AX to programmatically lock a Microsoft Excel spreadsheet. You lock the spreadsheet when you do not want anyone to change the Office Add-ins data sources or design for the spreadsheet. For more information about Office Add-ins, see [Using the Office Add-ins API](using-the-office-add-ins-api.md).

When you view a locked spreadsheet in Microsoft Excel, the **Dynamics AX** tab lets you **Refresh** or **Publish** the spreadsheet. The buttons you use to modify the data source and fields in the spreadsheet are removed or disabled.

The following steps show how to lock a spreadsheet. The code examples use a Visual Studio console application that lock a spreadsheet named MySpreadsheet.xlsx. You create the spreadsheet by using the **Export to Excel** button in the Action Pane of the **All customers** list page of the **Accounts Receivable** module. To view the complete console application, see the code example at the bottom of [How to: Add an Office Add-in Filter to a Spreadsheet](how-to-add-an-office-add-in-filter-to-a-spreadsheet.md).

### To Lock an Excel Spreadsheet

1.  Create an application where you can run the code that locks the spreadsheet.
    
    For example, you can use a Visual Studio console application. To create the application, start Visual Studio, click **File**, click **New**, and then click **Project**. In the **New Project** window specify that you want a Visual C\# Windows console application. Give your project a name and then click **OK**.

2.  Add a reference to the Microsoft.Dynamics.AX.Framework.OfficeAddins.XmlPart.dll and the DocumentFormat.OpenXml.dll to your project.
    
    For example, you add the libraries to a .NET application project by right-click **References** in the **Solution Explorer**, and then click **Add Reference**. In the **Add Reference** window, click **Browse**, open the folder where you installed the Office Add-ins. You typically find the files in the c:\\Program Files (x86)\\Microsoft Dynamics AX\\60\\OfficeAddins folder. Click Microsoft.Dynamics.AX.Framework.OfficeAddin.XmlPart.dll, and then click **OK**.
    
    To add DocumentFormat.OpenXml, re-open the **Add Reference** window, click the **.NET** tab, click **DocumentFormat.OpenXml**, and then click **OK**.

3.  Add the Microsoft.Dynamics.AX.Framework.OfficeAddin.XmlParts and DocumentFormat.OpenXml.Packaging namespaces to the project.
    
    The following code example shows how to add the namespaces.
    
    ``` csharp
    using Microsoft.Dynamics.AX.Framework.OfficeAddin.XmlParts;
    using DocumentFormat.OpenXml.Packaging;
    ```

4.  Create a spreadsheet object for the Excel spreadsheet that you want to modify.
    
    The following code example creates a document object named myWorkbook. Notice how the first parameter of the Open method specifies the location of the file. Also notice how the second parameter specifies that the file is editable.
    
    ``` csharp
    SpreadsheetDocument myWorkbook = SpreadsheetDocument.Open("@c:\Users\UserName\Documents\MySpreadsheet.xlsx", true);
    ```

5.  Use the GetWorkbookXmlPart method of the Serializer class to retrieve the Office Add-ins XML from the spreadsheet file.
    
    The following code example creates a WorkbookXmlPart object that includes the Office Add-ins XML for the spreadsheet. Notice how the parameter of the GetWorkbookXmlPart method specifies the spreadsheet object.
    
    ``` csharp
    WorkbookXmlPart workbookXml = Serializer.GetWorkbookXmlPart(myWorkbook);
    ```

6.  Use the IsDesignLocked property of WorkbookOptions to specify whether the spreadsheet is locked. To lock the spreadsheet, set the property to true.
    
    The following codes example uses the IsDesignLocked property to lock the spreadsheet. Notice how the property is a member of the WorkbookOptions object.
    
    ``` csharp
    workbookXml.WorkbookOptions.IsDesignLocked = true;
    ```
    

    > [!NOTE]
    > <P>You can also use WorkbookOptions to specify whether the spreadsheet data is refreshed when you open the file in Excel. To automatically refresh the data, set the RefreshAllDataOnOpen property to true.</P>



7.  Update the spreadsheet file to use the modified Office Add-ins XML metadata. Use the SetWorkbookXmlPart method of the Serializer class.
    
    The following code example updates the spreadsheet file. Notice how the first parameter specifies the spreadsheet object and the second specifies the XML metadata object.
    
    ``` csharp
    Serializer.SetWorkbookXmlPart(myWorkbook, workbookXml);
    ```

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

