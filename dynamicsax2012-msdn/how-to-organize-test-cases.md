---
title: 'How to: Organize Test Cases'
TOCTitle: 'How to: Organize Test Cases'
ms:assetid: 6a0a86d2-2274-4b06-882e-247e4fbfbe53
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb496529(v=AX.60)
ms:contentKeyID: 35244786
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Organize Test Cases 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX includes a framework to create, run, and analyze test cases. After you create a library of test cases, you might want to organize them in a meaningful way. The development environment in Microsoft Dynamics AX provides the ability to group test cases in test projects. The project provides an icon next to each test case that indicates whether it ran or failed during the last run. When you hover the cursor over a failed test case, the exception that occurred displays. The following illustration provides a view of test cases in a project, the icons for each test that indicate whether the test case ran or failed, and an exception that displays for a failed test case.

![A Test Project that shows run or fail icons](images/Bb496529.TestProject(en-us,AX.60).gif "A Test Project that shows run or fail icons")

For information about how to create, run, and analyze a test case, see [How to: Create a Test Case](how-to-create-a-test-case.md), [How to: Run a Test Case](how-to-run-a-test-case.md), and [How to: Display Test Case Results](how-to-display-test-case-results.md).

## Creating a Test Project

In this section you will create a test project with the project designer in MorphX. A test project can contain groups of test case classes and references to other test projects. You have the option to create a private or shared project. Creating a project enables you to run tests during version control check-in and at the command prompt.

### To create a test project

1.  On the main menu, click the Project icon.

2.  In the **\\Projects** form, right-click the **Private** or **Shared** node, point to **New**, and then click **Test project**. This creates a project with a test suite.

3.  Press CTRL+D to open the Application Object Tree (AOT).

4.  In the AOT, click one or more test cases to include in the test suite. Drag them to the **TestCase** node in the **Test project** form.
    
    You can now run all the tests in the project. Right-click the project and then click **Run**. For other ways to run a project of tests, see [How to: Run a Test Case](how-to-run-a-test-case.md). For more information about how to work with projects, see [MorphX Development Projects](morphx-development-projects.md).

## Creating a Test Suite with Code

In this section you will create your own class extending from the SysTestSuite class and you will use code to add a test case.

### To add tests to a suite

1.  In the AOT, right-click the **Classes** node and then click **New Class**.

2.  Double-click the new class to open the Code Editor and change the code to the following.
    
        [SysTestTargetAttribute(‘Employee’)]
        public class EmployeeSuite extends SysTestSuite
        {
        }

3.  In the AOT, right-click EmployeeSuite, point to **Override Method**, and then click **New**.

4.  Create a suite to add an existing test case to the test suite with the following code. For a complete list of steps to create the EmployeeTest test case in this example, see [Walkthrough: Testing a Class Using the Unit Test Framework](walkthrough-testing-a-class-using-the-unit-test-framework.md).
    
        public void new()
        {
            // Create an instance of a test suite.
            // Associate the suite with an existing test class.
            SysTestSuite suite = new SysTestSuite(classstr(EmployeeTest));
            ;
            super();
        
            // Add one or more test cases to the suite.
            this.add(suite);
        }

Next, you may have to create setup and tear down logic at the test case or suite of test cases level. For more information, see [How to: Create Set Up and Tear Down Logic for a Test Case](how-to-create-set-up-and-tear-down-logic-for-a-test-case.md).

## See also

[Unit Test Framework](unit-test-framework.md)

[Walkthrough: Testing a Class Using the Unit Test Framework](walkthrough-testing-a-class-using-the-unit-test-framework.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

