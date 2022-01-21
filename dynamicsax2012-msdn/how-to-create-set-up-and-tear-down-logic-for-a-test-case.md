---
title: 'How to: Create Set Up and Tear Down Logic for a Test Case'
TOCTitle: 'How to: Create Set Up and Tear Down Logic for a Test Case'
ms:assetid: c6ccaeea-03b8-462e-b52a-79644f6f1d2f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb496539(v=AX.60)
ms:contentKeyID: 35251119
ms.date: 01/21/2022
mtps_version: v=AX.60
---

# How to: Create Set Up and Tear Down Logic for a Test Case 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX includes a framework to create, run, analyze, and organize test cases. Test cases can be organized into test suites. Your testing needs may require specific logic to run before the test or suite of tests is run. Additionally, you may require that logic will run to tear down the test or suite of tests environment. The development environment in Microsoft Dynamics AX provides the ability to stage data before and after a test case or suite of test cases runs.

For information about how to create, run, analyze and organize test cases, see [How to: Create a Test Case](how-to-create-a-test-case.md), [How to: Run a Test Case](how-to-run-a-test-case.md), [How to: Display Test Case Results](how-to-display-test-case-results.md), and [How to: Organize Test Cases](how-to-organize-test-cases.md).

## Creating a setUp Method for a Test Case

As the number of test methods grows for a test case or in a suite of test cases, you may have to create setUp and tearDown methods. All of your test methods will call these methods to set up and stage data. Determine what should go into the setup method by looking at the test methods to see what code could be reused. In this example, each test method creates an instance of a class. This section provides the steps to create a setUp method for a test case and provides code to create an instance of the Employee class. For a complete list of the steps to create this example, see [Walkthrough: Testing a Class Using the Unit Test Framework](walkthrough-testing-a-class-using-the-unit-test-framework.md).

### To create a setUp method

1.  Open a Microsoft Dynamics AX development workspace.

2.  Press CTRL+D to open the Application Object Tree (AOT).

3.  Find the test class that you want to create a setUp method for.

4.  Right-click the test class, point to **Override Method**, and then click **setUp**.

5.  Add the following code to create an instance of an Employee class in the setUp method.
    
       ```X++
       public void setUp()
        {
            // Create an employee instance to use in test cases.
            employee = new Employee("your name");
            super();
        }
       ```
    

    > [!NOTE]
    > <P>This method will now be called before each test method is called.</P>



## Creating a tearDown Method for a Test Case

This section provides the steps to create a tearDown method for a test case.

### To create a tearDown method

1.  In the AOT, find the test class that you want to create a tearDown method for.

2.  Right-click the test class, point to **Override Method**, and then click **tearDown**.

3.  Add the following code to run after a test method executes.
    
       ```X++
       public void tearDown()
        {
            print 'Test method cleaning called...';
            super();
        }
       ```
    

    > [!NOTE]
    > <P>This method will now be called after each test method is called.</P>



## Creating setUp and tearDown Methods for a Test Suite

Depending on your testing needs, other options for setting up tests and staging data exist. You may only need the setUp and tearDown method logic to execute one time for a group of test cases. You can create a test suite and add the setUp and tearDown methods at the suite level.

### To add setUp and tearDown methods at the test suite level

1.  In the AOT, right-click the **Classes** node and then click **New Class**.

2.  Double-click the new class to open the Code Editor and change the code to the following.
    
       ```X++
       public class EmployeeSuite extends SysTestSuite
        {
        }
       ```

3.  In the AOT, right-click EmployeeSuite, and then point to **Override Method**. Select the setUp or tearDown method and include the code that you want to run before or after the suite of tests.
    

    > [!NOTE]
    > <P>The setUp and tearDown methods are called one time. Create a suite when you need to call setup or data staging logic before a group of tests that should only run one time. For information about how to add a test case to a test suite, see <A href="how-to-organize-test-cases.md">How to: Organize Test Cases</A>.</P>



Additionally, you can set the isolation level of a test suite. The isolation level of a test suite varies based on the changes that each test case will make to the data. Each test case could have different needs for isolation based on what data it will change. For more information about isolation levels, see [Unit Test Framework](unit-test-framework.md).

Next, you may have specific testing needs regarding exceptions. For more information, see [How to: Test Exceptions Using a Test Case](how-to-test-exceptions-using-a-test-case.md).

## See also

[Unit Test Framework](unit-test-framework.md)

[Walkthrough: Testing a Class Using the Unit Test Framework](walkthrough-testing-a-class-using-the-unit-test-framework.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

