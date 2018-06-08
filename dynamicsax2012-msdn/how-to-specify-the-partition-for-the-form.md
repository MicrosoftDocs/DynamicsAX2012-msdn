---
title: 'How to: Specify the Partition for the Form'
TOCTitle: 'How to: Specify the Partition for the Form'
ms:assetid: e08d7440-52e1-45d1-abb1-2f425ea54786
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ677295(v=AX.60)
ms:contentKeyID: 49384066
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# How to: Specify the Partition for the Form 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

You can use the Dynamics AX COM object to open a form from a client workspace and a specified partition. To include a partition, you must be working with Microsoft Dynamics AX 2012 R2 or a later version of the client. For more information about COM and partitions, see [Using COM to Open a Form from an Application](using-com-to-open-a-form-from-an-application.md).

To specify the partition to use when you open a form, you have to complete the following tasks:

  - Determine whether there is a running client workspace with that partition.

  - If the client and partition are not running, start the client together with the specified partition.

  - Use the OpenMenuItem method of the DynamicsAxApplication interface to open the form.

If you do not specify a partition, the DynamicsAxApplication interface uses the default partition for the AX user who opens the form. The following procedures show how to perform each of these tasks. The steps show how to use a Microsoft.NET application to open a form. For more information about how to use .NET with the Dynamics AX COM object, see [How to: Use COM to Open a Form](how-to-use-com-to-open-a-form.md).

### To determine whether the client is running with a specified partition

1.  Add the GetRunningObjectTable and CreateBindCtx methods from the ole32.dll library to the project.
    
    The following code example adds the GetRunningObjectTable and CreatBindCtx methods to a .NET project. Notice the use of the DllImport attribute to add the methods from the ole32.dll library.
    
    ``` csharp
    [DllImport("ole32.dll")]
    private static extern int GetRunningObjectTable(int reserved, out IRunningObjectTable prot);
     
    [DllImport("ole32.dll")]
    private static extern int CreateBindCtx(int reserved, out IBindCtx ppbc);
    ```

2.  Add a method that you can use to search the running object table for a specified partition. If the specified object is not running, the method should return null. Otherwise, the method should return the object from the running object table that represents the specified partition. You will add the code from the remaining steps to this method.
    
    The following code example adds a method named GetDynamicsAx. Notice how the method uses the parameter to create a display name for a partition. Also notice how comObject is first set to null. You will use comObject as the return value for the method.
    
    ``` csharp
    static object GetDynamicsAx(string partitionKey)
    {
        string displayName = "!DynamicsAx.Application:" + partitionKey;
        
        object comObject = null;
    }
    ```

3.  Use the GetRunningObjectTable method that you added earlier to access the running object table. Retrieve a list of the monikers for the objects in the running object table. A COM moniker is a name that identifies a COM object.
    
    The following code example uses the IRunningObjectTable interface with the GetRunningObject method to access the running object table. Notice the use of EnumRunning method to get a list of monikers from the running object table.
    
    ``` csharp
        IRunningObjectTable runningObjectTable;
        GetRunningObjectTable(0, out runningObjectTable);
    
        IEnumMoniker monikerEnumerator;
        runningObjectTable.EnumRunning(out monikerEnumerator);
        monikerEnumerator.Reset();
    ```

4.  Use the CreateBindCtx method that you added earlier to create a COM context object. You will use the context object when you retrieve the display name for each moniker in the running object table.
    
    The following code example creates a COM context object.
    
    ``` csharp
        IBindCtx ctx;
        CreateBindCtx(0, out ctx);
    ```

5.  Search the list for a moniker with a display name that includes the specified partition. If the display name is found, get the object that has that moniker.
    
    The following code example iterates the list of monikers and searches for a moniker with a display name that matches displayName. If the search finds the display name, the return value is populated with the COM object and the search stops.
    
    ``` csharp
        IMoniker[] monikers = new IMoniker[1];
        System.IntPtr numFetched = new IntPtr();
    
        while (monikerEnumerator.Next(1, monikers, numFetched) == 0)
        {
            monikers[0].GetDisplayName(ctx, null, out runningObjectName);
    
            // If the names are equal, get the specified COM object
            if (runningObjectName == displayName)
            {
                //Get the object with the specified display name
                runningObjectTable.GetObject(monikers[0], out comObject);
    
                //Stop iterating through the running object table
                break;
            }
        }
    ```

6.  Release the COM context object
    
    The following code example uses the ReleaseComObject method to release the context object.
    
    ``` csharp
        Marshal.ReleaseComObject(ctx);
    ```

7.  Return the COM object that represents the specified partition. If the object is not found in the running object table, the return value will be null.
    
    The following code example returns comObject from the GetDynamicsAx method.
    
    ``` csharp
        return comObject;
    ```

### To start the client together with a specified partition

1.  Add a method that you can use to start the Microsoft Dynamics AX client together with a specified partition. You have to use this method when you find that the running object table does not include a client workspace with the targeted partition. You will add the code from the remaining steps to this method.
    
    The following code example creates a method named StartDynamicsAx. Notice how the axDirectory specifies the installation location of the client executable file.
    
    ``` csharp
    static void StartDynamicsAx(string partitionKey)
    {
       string axDirectory = @"C:\Program Files (x86)\Microsoft Dynamics AX\60\Client\Bin";
    }
    ```

2.  Create a process object that you can use to start the client. Specify the name of the executable file and use the partition argument to specify the partition.
    
    The following code example shows how to create a process object that can start the client. Notice how the partitionKey parameter specifies the name of the partition.
    
    ``` csharp
        Process axApplication = new Process();
        axApplication.StartInfo.WorkingDirectory = axDirectory;
        axApplication.StartInfo.FileName = "Ax32.exe";
        axApplication.StartInfo.Arguments = "-partition=" + partitionKey;
    ```

3.  Use the process object to start the application together with the specified partition.
    
    The following code example starts a client workspace using the partition specified by axApplication.StartInfo.Arguments.
    
    ``` csharp
        axApplication.Start();
    ```

### To open the form with the OpenMenuItem method of the DynamicsAxApplication interface

1.  Find the location in your application where you want to open a Microsoft Dynamics AX form. Create a string that specifies the name of the partition.
    
    The following code example shows the Main method from a console application. Notice how partitionKey is populated with the name of a partition.
    
    ``` csharp
    static void Main(string[] args)
    {
        //Specify the partition you want to work with
        string partitionKey = "MyPartition";
    }
    ```

2.  Use the method that you created earlier to determine whether the specified partition is running. If the method returns an object, the client and partition are already running.
    
    The following code example uses a method named GetDynamicsAx to determine whether there is a running client workspace with the specified partition. Note that the value of the dynamicsApplication object will be either a COM object or null.
    
    ``` csharp
        object dynamicsApplication = GetDynamicsAx(partitionKey);
    ```

3.  If the previous step returns null, the running object table does not include the client that has the specified partition. As a result, you have to start the client together with the partition. You can use the method that you added in the previous procedure to start the application.
    
    The following code example uses a method named StartDynamicsAx to start the client together with a specified partition. Notice how the application uses the Sleep method to pause when the client starts.
    
    ``` csharp
        if (dynamicsApplication == null)
        {
            StartDynamicsAx(partitionKey);
    
            //Wait for the AX application to start and register in the running object table
            System.Threading.Thread.Sleep(10000);
        }
    ```

4.  Create an instance of the DynamicsAxApplication interface and use the OpenMenuItem method to open the form specified by the menu item.
    

    > [!WARNING]
    > <P>The DynamicsAxApplication interface binds to the first running instance of the AX client in the running object table and does not verify the partition. If you are running more than one client workspace with more than one partition, you might not connect to the partition that you want to target. If your application runs in environments where there might be multiple partitions, verify that you are using the targeted partition.</P>

    
    The following code example shows how to use the OpenMenuItem method to open a form. Notice how the OpenMenuItem method requires that you specify a company, the name of a menu item, and the type of the menu item.
    
    ``` csharp
        AxClientLib.DynamicsAxApplication AxComClient = new AxClientLib.DynamicsAxApplication();
       
        if (AxComClient != null)
        {
            AxComClient.OpenMenuItem(databaseName, formName, menuType);
        }
    ```

## Example

To show how to use the COM object together with a partition, the following code example shows a console application that opens the customer list page for a specified partition. The example includes all of the code examples shown in the earlier procedures.

``` csharp
using System;
using System.Diagnostics;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Runtime.InteropServices;
using System.Runtime.InteropServices.ComTypes;
using AxClientLib;

namespace ConsoleApplication1
{
    class Program
    {
        static void Main(string[] args)
        {
            //Specify the partition you want to work with
            string partitionKey = "MyPartition";

            try
            {
                //Get the specified Dynamics AX application/partition from the running object table
                object dynamicsApplication = GetDynamicAx(partitionKey);

                //If the Dynamics AX application was not found in the running object table
                // start the application with the specified partition.
                if (dynamicsApplication == null)
                {
                    Console.WriteLine("The Dynamics Application is not running");
                    Console.WriteLine("");
                    StartDynamicsAx(partitionKey);

                    //Wait for the AX application to start and register in the running object table
                    System.Threading.Thread.Sleep(10000);
                }

                // Open the specified form with the specified database
                OpenForm("DAT", "CustTableListPage", AxClientLib.AxMenuType.DisplayMenu);
            }
            catch(Exception e)
            {
                Console.WriteLine("");
                Console.WriteLine("*** An error occurred ***");
                Console.WriteLine("Error: " + e.Message);
                Console.WriteLine("*************************");
            }

            Console.WriteLine(""); 
            Console.WriteLine("Press any key to close the console window");
            Console.ReadKey();
        }

        //This opens a form with the first instance of a DynamicsAX Application that appears in the running object table
        static void OpenForm(string databaseName, string formName, AxMenuType menuType)
        {
            AxClientLib.DynamicsAxApplication AxComClient = new AxClientLib.DynamicsAxApplication();
            
            if (AxComClient != null)
            {
                AxComClient.OpenMenuItem(databaseName, formName, menuType);
            }
            else
            {
                throw new NullReferenceException();
            }
        }

        // Use the GetRunningObjectTable method in the ole32.dll COM library
        // Add a using statement for System.Runtime.InteropServices;
        [DllImport("ole32.dll")]
        private static extern int GetRunningObjectTable(int reserved, out IRunningObjectTable prot);

        //Use the CreateBindCtx method in the ole32.dll COM library
        // You use this method to create a bind context for the COM object
        [DllImport("ole32.dll")]
        private static extern int CreateBindCtx(int reserved, out IBindCtx ppbc);

        static object GetDynamicAx(string partitionKey)
        {
            string displayName = "!DynamicsAx.Application:" + partitionKey;
            
            object comObject = null;
            
            IRunningObjectTable runningObjectTable;
            GetRunningObjectTable(0, out runningObjectTable);

            IEnumMoniker monikerEnumerator;
            runningObjectTable.EnumRunning(out monikerEnumerator);
            monikerEnumerator.Reset();
            
            IBindCtx ctx;
            string runningObjectName = displayName + "not found";
            
            CreateBindCtx(0, out ctx);

            IMoniker[] monikers = new IMoniker[1];
            System.IntPtr numFetched = new IntPtr();

            while (monikerEnumerator.Next(1, monikers, numFetched) == 0)
            {
                monikers[0].GetDisplayName(ctx, null, out runningObjectName);

                // If the names are equal, get the specified COM object
                if (runningObjectName == displayName)
                {
                    //Get the object with the specified display name
                    runningObjectTable.GetObject(monikers[0], out comObject);

                    //Stop iterating through the running object table
                    break;
                }

                //Reset the name value to the default setting
                runningObjectName = displayName + " not found";
            }

            Marshal.ReleaseComObject(ctx);

            Console.WriteLine("Name of returned COM object: " + runningObjectName);
            Console.WriteLine("");

            // If the specified object is not running, returns null object
            return comObject;
        }

        // Starts an instance of the DyanmicsAx.Aapplication with a specified partition
        static void StartDynamicsAx(string partitionKey)
        {
            string axDirectory = @"C:\Program Files (x86)\Microsoft Dynamics AX\60\Client\Bin";
            
            Process axApplication = new Process();
            axApplication.StartInfo.WorkingDirectory = axDirectory;
            axApplication.StartInfo.FileName = "Ax32.exe";
            axApplication.StartInfo.Arguments = "-partition=" + partitionKey;

            axApplication.Start();
        }
    }
}
```

## See also

[Dynamics AX Client Type Library Reference](dynamics-ax-client-type-library-reference.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

