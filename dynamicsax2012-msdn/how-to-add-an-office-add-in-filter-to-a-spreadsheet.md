---
title: 'How to: Add an Office Add-in Filter to a Spreadsheet'
TOCTitle: 'How to: Add an Office Add-in Filter to a Spreadsheet'
ms:assetid: bc72e08b-b2b6-4e05-8e02-eacbb28a05d8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ677294(v=AX.60)
ms:contentKeyID: 49384065
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# How to: Add an Office Add-in Filter to a Spreadsheet [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

With Microsoft Dynamics AX 2012 R2 you can use an API in the Office Add-ins for Microsoft Dynamics AX to programmatically add, remove, or modify filters in a Microsoft Excel spreadsheet. To use the API, the spreadsheet must include Microsoft Dynamics AX data that was obtained by using Office Add-ins, or the **Export to Excel** or **Generate from template** button of a form. For more information about the Office Add-ins API, see [Using the Office Add-ins API](using-the-office-add-ins-api.md).

The code examples in the following steps add a filter to an Excel spreadsheet named MySpreadsheet.xlsx. You create the spreadsheet by using the **Export to Excel** button in the Action Pane of the **All customers** list page of the **Accounts Receivable** module. In addition, the C\# code examples are from a Visual Studio console application project that adds the filter to the specified spreadsheet. You will find the complete console application code example at the end of this topic.

### To Add a Data Source Filter to a Spreadsheet

1.  Create an application where you can run the code that adds the filter to the spreadsheet.
    
    For example, you can use a Visual Studio console application. To create the application, start Visual Studio, click **File**, click **New**, and then click **Project**. In the **New Project** window specify that you want a Visual C\# Windows console application. Give your project a name and then click **OK**.

2.  Add a reference to the Microsoft.Dynamics.AX.Framework.OfficeAddins.XmlPart.dll and the DocumentFormat.OpenXml.dll to your project.
    
    For example, you add the libraries to your Visual Studio application project by right-clicking **References** in the **Solution Explorer**, and then clicking **Add Reference**. In the **Add Reference** window, click **Browse**, open the folder where you installed the Office Add-ins. You typically find the files in the c:\\Program Files (x86)\\Microsoft Dynamics AX\\60\\OfficeAddins folder. Click Microsoft.Dynamics.AX.Framework.OfficeAddin.XmlPart.dll, and then click **OK**.
    
    To add DocumentFormat.OpenXml, re-open the **Add Reference** window, click the **.NET** tab, click **DocumentFormat.OpenXml**, and then click **OK**.
    

    > [!NOTE]
    > <P>You might also have to add a reference to the WindowsBase .NET assembly.</P>



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

6.  Search the document data sources for the data source you want to modify. To find the name of a data source, you can use the **Filter results** window that opens from the **Dynamics AX** tab
    
    The following code example shows how to search the Office Add-ins XML metadata part for a specified data source. The example shows how to use the name to specify the data source. The code examples from the following three steps should be added inside this code block.
    
    ``` csharp
    foreach (DataSourceXmlPart dataSourceXml in workbookXml.DataSources.Values)
    {
        // The following code example shows the default format for a data source name: ?<form name>?
        if (dataSourceXml.QueryName == "?All customers?")
        {
            
        }
    }
    ```

7.  Create a FilterXmlPart object for the new filter.
    
    The following code example creates a FilterXmlPart object named hasCreditLimit.
    
    ``` csharp
            FilterXmlPart hasCreditLimit = new FilterXmlPart();
    ```

8.  Populate the properties of the filter. Use the properties to specify the table, the field, and the filter criteria.
    
    The following code example populates a filter object. The filter uses the CreditMax field from CustTable. Notice how the value of the Criteria property specifies customers who have a credit limit.
    
    ``` csharp
            // To specify a fully qualified names, use the following format: <data source>.<table name>.<field name>.
            hasCreditLimit.TableFullyQualifiedName = "?All customers?.CustTable";
            hasCreditLimit.FieldFullyQualifiedName = "?All customers?.CustTable.CreditMax";
            hasCreditLimit.Criteria = "> 0";
    ```

9.  Add the filter to the filter collection of the data source.
    
    The following code example uses the Add method of the FilterXmlPartCollection object to add the hasCreditLimit filter object.
    
    ``` csharp
            dataSourceXml.Filters.Add(hasCreditLimit);
    ```

10. Update the spreadsheet file to use the modified Office Add-ins XML metadata. Use the SetWorkbookXmlPart method of the Serializer class.
    
    The following code example updates the spreadsheet file. Notice how the first parameter specifies the spreadsheet object and the second specifies the XML metadata object.
    
    ``` csharp
    Serializer.SetWorkbookXmlPart(myWorkbook, workbookXml);
    ```

## Example

The following code example shows a console application that adds a filter to an Excel spreadsheet. The new filter enables the spreadsheet to show customers who have a credit limit. The example also shows how to lock the spreadsheet and how to refresh the data when you open the spreadsheet file. The example includes all the code used in the previous steps.

``` csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using Microsoft.Dynamics.AX.Framework.OfficeAddin.XmlParts;
using DocumentFormat.OpenXml.Packaging;

namespace ConsoleApplication2
{
    class Program
    {
        static void Main(string[] args)
        {
            try
            {
                // Create a connection to the spreadsheet. Make the spreadsheet editable.
                SpreadsheetDocument myWorkbook = SpreadsheetDocument.Open(@"C:\Users\LocalUser\Documents\MySpreadsheet.xlsx", true);

                // Get the XML metadata from the spreadsheet.
                WorkbookXmlPart workbookXml = Serializer.GetWorkbookXmlPart(myWorkbook);

                // If the spreadsheet is locked, remove the lock.
                workbookXml.WorkbookOptions.IsDesignLocked = false;

                // Find and modify the filter criteria.
                foreach (DataSourceXmlPart dataSourceXml in workbookXml.DataSources.Values)
                {
                    // The following code example shows the default format for the data source name:
                    //  ?<form name>?
                    if (dataSourceXml.QueryName == "?All customers?")
                    {
                        // Create a filter object
                        FilterXmlPart hasCreditLimit = new FilterXmlPart();
                        
                        // Populate the properties of the filter
                        // To specify a fully qualified names, use the following format:
                        //  <data source>.<table name>.<field name>
                        hasCreditLimit.TableFullyQualifiedName = "?All customers?.CustTable";
                        hasCreditLimit.FieldFullyQualifiedName = "?All customers?.CustTable.CreditMax";
                        hasCreditLimit.Criteria = "> 0";

                        // Add the filter to the filter collection of the datasource.
                        dataSourceXml.Filters.Add(hasCreditLimit);
                    }
                }

                // Lock the spreadsheet to prevent changes from the Dynamics AX tab
                workbookXml.WorkbookOptions.IsDesignLocked = true;

                // To show the change to the filter, refresh the spreadsheet when it opens.
                workbookXml.WorkbookOptions.RefreshAllDataOnOpen = true;

                // Update the XML metadata of the spreadsheet.
                Serializer.SetWorkbookXmlPart(myWorkbook, workbookXml);
            }
            catch (Exception e)
            {
                Console.WriteLine(e.Message);
            }
        }
    }
}
```

## See also

[How to: Use Office Add-ins to Lock an Excel Spreadsheet](how-to-use-office-add-ins-to-lock-an-excel-spreadsheet.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

