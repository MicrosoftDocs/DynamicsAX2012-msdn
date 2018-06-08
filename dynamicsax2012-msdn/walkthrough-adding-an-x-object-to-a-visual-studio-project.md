---
title: 'Walkthrough: Adding an X++ Object to a Visual Studio Project'
TOCTitle: 'Walkthrough: Adding an X++ Object to a Visual Studio Project'
ms:assetid: 55663cc6-f865-4316-ab58-dfb3117f78b1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg889200(v=AX.60)
ms:contentKeyID: 35272092
ms.date: 11/21/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Walkthrough: Adding an X++ Object to a Visual Studio Project 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Visual Studio, you use Application Explorer to add an X++ element to a managed code project. This walkthrough illustrates the following tasks:

  - Creating the class library, adding a Microsoft Dynamics AX table to the project, and accessing that table from code.

  - Creating a console application project and testing the generated assembly.


> [!TIP]
> <P>Although this topic shows you how to test the generated assembly from Visual Studio, you can also test it from X++ because after you add the project to the AOT, the classes in the assembly are available from Microsoft Dynamics AX.</P>



## Prerequisites

To complete this walkthrough you will need:

  - Microsoft Dynamics AX with Visual Studio Tools and sample data installed

  - Visual Studio 2010

## Creating the Class Library

The first step is to create the class library in Visual Studio. After you have created the class library project, you can then add a Microsoft Dynamics AX table to the project. Then you can create class methods that access that table.

### To create the class library

1.  To create a new class library project, click **File** \> **New**\> **Project**.

2.  Below the Installed Templates tree, click **Visual C\#** \> **Windows**, select the **Class Library** project type and then click **OK**.

3.  Save the new project.

4.  Add the project to the AOT by clicking **File** \> **Add ClassLibrary1 to AOT**. Notice that the project icon changes in Solution Explorer. Alternatively, you can right-click the ClassLibrary1 project and select **Add ClassLibrary1 to AOT**.

### To add a Microsoft Dynamics AX table to the project

1.  Open the Application Explorer by clicking **View** \> **Application Explorer**. Expand the **Data Dictionary** \> **Tables** node and locate the CustTable table.

2.  Click the CustTable table and drag it onto the project in Solution Explorer. Alternatively, you can right-click the table and then click **Add to Project**. In Solution Explorer, you can see that the table and a proxy to the CustTable table are created internally by the system. In the **References** node you can see a reference to the assembly Microsoft.Dynamics.Ax.ManagedInterop.
    

    > [!TIP]
    > <P>You can add a system table or system class to your Visual Studio project even if the interface does not support the dragging of system objects. For example, to add the <STRONG>FormRun</STRONG> system class, first add any application class, such as the <STRONG>Bank</STRONG> class. Then rename the new proxy node from <STRONG>Class.Bank.axproxy</STRONG> to <STRONG>Class.FormRun.axproxy</STRONG>.</P>



### To create methods that use the table

  - Open the Class1.cs file and add the following code. This code contains two methods that each take two parameters and return data for the specified customer.
    
    ``` csharp
    using System;
    
    namespace ClassLibrary1
    {
        public class Class1
        {
            public string GetCustomerPaymentMode(string accountNum, string dataAreaId)
            {
    
                string paymentMode = String.Empty;
                CustTable custTable = new CustTable();
    
                // Search for the customer.
                custTable = CustTable.findByCompany(dataAreaId, accountNum);
             
                    if (custTable.Found)
                    {
                        // Get the value for the customer's payment mode.
                        paymentMode = custTable.PaymMode;
                    }
    
                return paymentMode;
            }
    
            public bool GetCustomerCreditLimit(string accountNum, string dataAreaId)
            {
    
                bool hasCreditLimit = false;
                CustTable custTable = new CustTable();
    
                // Search for the customer.
                custTable = CustTable.findByCompany(dataAreaId, accountNum);
    
                if (custTable.Found)
                {
                    // Get the value for whether the customer has a credit limit.
                    hasCreditLimit = (custTable.MandatoryCreditLimit == NoYes.No ? false : true);
                }
    
                return hasCreditLimit;
            }
        }
    }
    ```

## Creating a Console Application Project

### To create a console application project to test the assembly

1.  In Solution Explorer, right-click the solution ClassLibrary1 and select **Add** \> **New Project**.

2.  Below the Installed Templates tree, click **Visual C\#** \> **Windows**, select the **Console Application** project type and then click **OK**.

3.  In Solution Explorer, add a reference to the ClassLibrary1 project by right-clicking the **References** node under the ConsoleApplication1 project and then clicking **Add Reference**.

4.  Click the **Projects** tab, select the ClassLibrary1 project and then click **OK**.

5.  In Solution Explorer, add a reference to the managed interop assembly by right-clicking the **References** node under the ConsoleApplication1 project and then clicking **Add Reference**.

6.  Click the **Browse** tab, locate the Microsoft.Dynamics.AX.ManagedInterop assembly and select **OK**. This assembly is located in the Client\\Bin directory. For example, C:\\Program Files (x86)\\Microsoft Dynamics AX\\60\\Client\\Bin. This reference is necessary to use the [Session](https://msdn.microsoft.com/en-us/library/ee894214\(v=ax.60\)) object.

### To call methods to display output to the console application

1.  Open the Program.cs file and add the following code. This code calls the GetCustomerPaymentMode and the GetCustomerCreditLimit methods from the class you created and displays the values in the console window.
    
    ``` csharp
    using System;
    using ClassLibrary1;
    using Microsoft.Dynamics.AX.ManagedInterop;
    
    namespace ConsoleApplication1
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Create a session
                using (Session session = new Session())
                {
                    session.Logon(null, null, null, null);
    
                    Class1 class1 = new Class1();
                    string accountNum = "3003";
                    string dataAreaId = "ceu";
                    string paymentMode = String.Empty;
                    string hasCreditLimitText = String.Empty;
                    bool hasCreditLimit;
    
                    // Get the customer payment mode and credit limit.
                    paymentMode = class1.GetCustomerPaymentMode(accountNum, dataAreaId);
                    hasCreditLimit = class1.GetCustomerCreditLimit(accountNum, dataAreaId);
                    hasCreditLimitText = (hasCreditLimit == false ? " and does not have" : " and has");
    
                    // Write the data to the console
                    Console.WriteLine("Customer " + accountNum + " in company " + dataAreaId +
                        " has a payment mode of " + paymentMode + hasCreditLimitText +
                        " a mandatory credit limit." );
                    Console.ReadLine();
                }
    
            }
        }
    }
    ```

2.  In Solution Explorer, set the console application to be the startup project by right-clicking ConsoleApplication1 and then clicking **Set as StartUp Project**.

### To test the generated assembly

  - Run the application. If you have the sample data installed, you will see the following output in the console window:
    
    Customer 3003 in company ceu has a payment mode of CHCK and does not have a mandatory credit limit.
    

    > [!TIP]
    > <P>You may receive an error about the .NET target framework because both projects target the .NET Framework 4 by default but the Microsoft.Dynamics.AX.ManagedInterop assembly is a mixed-mode assembly that targets the 2.0 runtime.</P>
    > <P>To resolve this error you have two options: you can change the target framework for both projects to .NET Framework 3.5 or you can add an attribute to the app.config file of the console application project. To change the target framework, right-click each project in Solution Explorer and then click <STRONG>Properties</STRONG>. In the <STRONG>Target framework</STRONG> field, select <STRONG>.NET Framework 3.5</STRONG>.</P>
    > <P>If you want the console application project to target the .NET Framework 4, add the useLegacyV2RuntimeActivationPolicy attribute to the startup element in the app.config file and set it to true. For example, &lt;startup useLegacyV2RuntimeActivationPolicy="true"&gt;.</P>



## Next Steps

You can call the managed code in your class library from X++ by using [.NET Interop from X++](net-interop-from-x.md)

## See also

[Integration with X++ Objects from Visual Studio](integration-with-x-objects-from-visual-studio.md)

[.NET Interop from X++](net-interop-from-x.md)

