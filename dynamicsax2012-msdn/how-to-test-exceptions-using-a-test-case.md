---
title: 'How to: Test Exceptions Using a Test Case'
TOCTitle: 'How to: Test Exceptions Using a Test Case'
ms:assetid: 6083a333-d50e-4502-86e6-6cf429c23c2b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb496528(v=AX.60)
ms:contentKeyID: 35244493
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Test Exceptions Using a Test Case [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX includes a Unit Test framework to create, run, analyze, and organize test cases. Within the framework you can test the expected exceptions for a given feature. In this example, you will create a class that contains an exception and then you will test the class. For a working example, see [Walkthrough: Testing a Class Using the Unit Test Framework](walkthrough-testing-a-class-using-the-unit-test-framework.md).

For information about how to create, run, analyze, and organize test cases, see [How to: Create a Test Case](how-to-create-a-test-case.md), [How to: Run a Test Case](how-to-run-a-test-case.md), [How to: Display Test Case Results](how-to-display-test-case-results.md), and [How to: Organize Test Cases](how-to-organize-test-cases.md).

## Create a Class with an Exception

You will create the Employee class that throws an exception.

### To create an Employee class

1.  Open the Development Workspace. See [How to: Open a Development Workspace](how-to-open-a-development-workspace.md) for more information.

2.  Press CTRL+D to open the Application Object Tree (AOT).

3.  In the AOT, right-click the **Classes** node and click **New Class**.

4.  Right-click **Class1**, click **Rename**, and then rename the class Employee.

In this section you will add a method to the Employee class that throws an exception.

### To throw an exception

1.  In the AOT, in the Employee class node, double-click **classDeclaration**.

2.  In the Code Editor, add the following member variable in the **classDeclaration** braces.
    
        boolean retired;

3.  In the AOT, right-click Employee, point to **New**, and then click **Method**.

4.  In the Code Editor, change the method to the following code.
    
        public void retire()
        {
            // If retired, throw an exception. 
            // Otherwise, set the retired value to true.
            if (retired)
                throw error("Already retired.");
        
            retired = true;
        }

5.  In the AOT, right-click the Employee class and click **Compile**.

## Adding an Exception Test Class

In this procedure, you will create a class named EmployeeTest that extends the SysTestCase class.

### To create an exception test class

1.  Right-click the **Classes** node and click **New Class**.

2.  Double-click **Class1** to open the Code Editor.

3.  In the Code Editor, extend SysTestCase by changing the class declaration to the following code.
    
        [SysTestTargetAttribute('Employee',UtilElementType::Class)]
        class EmployeeTest extends SysTestCase
        {
        }

## Adding an Exception Test Method

In this procedure you will add a test method named testRetire. You will do this by adding a method to the EmployeeTest class. If an employee is already retired you should receive an exception if the retire method is called again. You will verify that the expected exception is thrown when an employee is set to retire more than one time.

### To add an exception test method

1.  In the AOT, right-click EmployeeTest, point to **New**, and then click **Method**.

2.  In the Code Editor, change the method to the following code.
    
        [SysTestMethodAttribute]
        void testRetire()
        {
            // Create an instance of the employee.
            Employee employee = new Employee();
         
            // Call the retire method, first time should be successful.
            employee.retire();
        
            // Assert that an exception is expected.
            this.parmExceptionExpected(true, "Already retired");
        
            // Call the retire method. An exception is expected.
            employee.retire();
        }

## Running the Exception Test Case

In this procedure, you will access the Unit Test toolbar to run the exception test case.

### To run an exception test case from the Unit Test toolbar

  - In the AOT, right-click EmployeeTest, point to **Add-Ins**, and then click **Run tests**. This displays the Unit Test toolbar and the toolbar results show **1 run, 0 failed**.

Next, you may have more general testing needs not related to exceptions. For more information about how to create, run, analyze, and organize test cases, see [How to: Create a Test Case](how-to-create-a-test-case.md), [How to: Run a Test Case](how-to-run-a-test-case.md), [How to: Display Test Case Results](how-to-display-test-case-results.md), and [How to: Organize Test Cases](how-to-organize-test-cases.md).

## See also

[Unit Test Framework](unit-test-framework.md)

[Walkthrough: Testing a Class Using the Unit Test Framework](walkthrough-testing-a-class-using-the-unit-test-framework.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

