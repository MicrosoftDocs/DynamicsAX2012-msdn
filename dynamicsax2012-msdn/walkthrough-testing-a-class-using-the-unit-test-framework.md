---
title: 'Walkthrough: Testing a Class Using the Unit Test Framework'
TOCTitle: 'Walkthrough: Testing a Class Using the Unit Test Framework'
ms:assetid: 4992b02a-27b3-46af-aece-9da58e9911df
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb410465(v=AX.60)
ms:contentKeyID: 35243154
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Testing a Class Using the Unit Test Framework 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX includes a framework for creating, running, and analyzing unit tests. In this walkthrough, you will create an Employee class that satisfies specific requirements. You will also create a test case that verifies that the requirements for the class have been met. The Unit Test framework is based on the principles of Test-Driven Development (TDD). For more information about TDD, see [Guidelines for Test-Driven Development](http://go.microsoft.com/fwlink/?linkid=86914). TDD advises that you have a failing test case and then write the feature code to satisfy the requirement that enables the test case to pass. The following steps mention the TDD process but the goal is to emphasize the Unit Test framework. After you create and run the test case, you will view the code coverage and set the isolation level for the test case.

The requirements for the Employee class include the following:

  - When an instance of an Employee class is created, the name is set using the name method.

  - The Employee class has a retire method that is called when the employee retires. The method can only be called one time per employee.

This walkthrough illustrates the following tasks:

  - Creating an Employee class stub.

  - Creating a test class.

  - Setting up data for test cases.

  - Adding a test case for the name requirement.

  - Running a test case.

  - Adding a test case for the retire requirement.

  - Capturing code coverage.

  - Setting the isolation level.

## Prerequisites

To complete this walkthrough, you will need:

  - Microsoft Dynamics AX

  - A license file that has access to the MorphX development environment

## Creating an Employee Class Stub

To abide by the principles of TDD, you will create the test class before you create the logic for the Employee class. To continue with fewer compile errors you will create a stub for the Employee class that does not contain any feature logic.

### To create an Employee class

1.  Open a Microsoft Dynamics AX development workspace.

2.  Press CTRL+D to open the Application Object Tree (AOT).

3.  In the AOT, right-click the **Classes** node and click **New Class**.
    

    > [!NOTE]
    > <P>The <STRONG>Classes</STRONG> node expands with a new class that has a name such as <STRONG>Class1</STRONG>.</P>



4.  Right-click **Class1**, click **Rename** and then rename the class Employee.

## Creating a Test Class

When you create a test case you will create a class that must use the naming convention best practice to associate the test with the class you are testing. Use the same name as the class that you are testing followed by Test. You can provide additional information by attaching attributes. For more information on attributes, see [How to: Categorize Test Cases Using Attributes](how-to-categorize-test-cases-using-attributes.md). In this procedure, you will create another class named EmployeeTest that extends the [SysTestCase Class](https://msdn.microsoft.com/en-us/library/gg933916\(v=ax.60\)) class.

### To create a test class

1.  Right-click the **Classes** node and click **New Class**.

2.  Double-click **Class1** to open the Code Editor.

3.  In the Code Editor, extend SysTestCase by changing the class declaration to the following code and create an Employee instance to use for the test cases.
    
        [SysTestTargetAttribute(‘Employee’,UtilElementType::Class)]
        
        class EmployeeTest extends SysTestCase
        {
            // Create a member variable named employee.
            Employee employee;
        }

## Setting up Data for Test Cases

In this procedure you will create an instance of the Employee class to use in all the test cases.

### To set up data for test cases

1.  In the AOT, right-click EmployeeTest, point to **Override Method**, and then click **setUp**.

2.  In the Code Editor, change the setUp method to the following code.
    
        public void setUp()
        {
            // Create an employee instance to use in test cases.
            employee = new Employee("your name");
        
            super();
        }

## Adding a Test Case for the Name Requirement

In this procedure you will add a test case. You will do this by adding a method to the EmployeeTest class. Attach the SysTestMethodAttribute attribute to indicate the method is a test method. You will verify that the name of an employee is set correctly.

### To add a test case for the name requirement

1.  In the AOT, right-click EmployeeTest and then click **New** \> **Method**.

2.  In the Code Editor, change the method to the following code.
    
        [SysTestMethodAttribute]
        void testName()
        {
            // Verify that the employee name is set correctly.
            this.assertEquals("your name", employee.name());
        }

You now have a failing test case therefore, you can write the feature code to allow for the test case to compile and pass. Add code to the Employee class by overriding the new method to accept a string as a parameter.

### To add feature code

1.  In the AOT, in the Employee class node, double-click the **classDeclaration** method.

2.  In the Code Editor, change the Employee **classDeclaration** to the following code.
    
        class Employee
        {
            // Create member variables.
            Name name;
        }

3.  In the AOT, right-click the Employee class, point to **Override Method**, and then click **new**.

4.  In the Code Editor, change the **new** method to the following code.
    
        Public void new(Name _name)
        {
            name = _name;
        }

5.  In the AOT, right-click the Employee class, and then click **New** \> **Method**.

6.  In the Code Editor, change the method to the following code.
    
        public Name name()
        {
            // Return the expected string.
            return name;
        }

7.  In the AOT, right-click the Employee class and click **Compile**.

8.  Right-click the EmployeeTest class and click **Compile**.

## Running a Test Case

In this procedure you will access the Unit Test toolbar to run the test case. For information about the other ways to run a test case, see [How to: Run a Test Case](how-to-run-a-test-case.md).

### To run a test case

  - In the AOT, right-click EmployeeTest, point to **Add-Ins**, and then click **Run tests**.
    

    > [!NOTE]
    > <P>This opens the Unit Test toolbar and runs the test. One test case has been added so the results show <STRONG>1 run, 0 failed</STRONG>.</P>



In this procedure you will make the test fail to see the fail result. In TDD, it is appropriate to create the failing test first. For compile reasons, in this example you created the passing test case first.

### To make the test case fail

1.  In the AOT, in the Employee class node, double-click the name  **method**.

2.  In the Code Editor, change the method to the following code.
    
        public Name name()
        {
            // Return the expected string.
            // return name;
        
            // Return an empty string to make the test case fail.
            return "";
        }

3.  In the AOT, right-click the Employee class and click **Compile**.

4.  On the Unit Test toolbar, click **Run**.
    

    > [!NOTE]
    > <P>The results show <STRONG>1 run, 1 failed</STRONG>. The Infolog provides additional information about the value that was expected and the actual value.</P>
    > <P><STRONG>Error:</STRONG></P>
    > <P><STRONG>[EmployeeTest.testName]Failure: Assertion failed! (Expected: your name; Actual: )</STRONG></P>

    
    In the Infolog, you can click the **Edit** button to open the Code Editor at the point where the assertion line failed.

5.  In the AOT, in the Employee class node, double-click the name method.

6.  In the Code Editor, change the method to the following code.
    
        public Name name()
        {
            // Return the expected string.
            return name;
        
            // Return an empty string to make the test case fail.
            // return "";
        }

7.  In the AOT, right-click the Employee class and click **Compile**.

## Adding a Test Case for the Retire Requirement

In this procedure you will add another test case for the retirement requirement. You will do this by adding a method to the EmployeeTest class. You will verify that when the retire method is called more than one time for an employee that an error is thrown. Attach the SysTestMethodAttribute attribute to indicate the method is a test method. Again, following the guidance of TDD, you will create the test before the feature code so the test will not compile.

### To add a test case for the retire requirement

1.  In the AOT, right-click EmployeeTest and then click **New** \> **Method**.

2.  In the Code Editor, change the method to the following code.
    
        [SysTestMethodAttribute]
        void testRetire()
        {
            // Call the retire method, first time should be successful.
            employee.retire();
        
            // Expect an exception to be thrown because the employee is
            // already retired.
            this.parmExceptionExpected(true, "Already retired");
            employee.retire();
        }

The code added for the new test case will not compile until you add the retire method to the Employee class. You must also add a variable to store whether the employee is retired. To simplify this example, you will throw a string error message, in a real world example you would create a label for the error message "**Already retired.**"

### To add the retire method

1.  In the AOT, in the Employee class node, double-click **classDeclaration**.

2.  In the Code Editor, add the following member variable in the **classDeclaration** braces.
    
        boolean retired;

3.  In the AOT, right-click Employee and then click **New** \> **Method**.

4.  In the Code Editor, change the method to the following code.
    
        public void retire()
        {
            // If retired, throw an exception, otherwise set the retired value to true.
            if (retired)
                throw error("Already retired");
        
            retired = true;
        }

5.  In the AOT, right-click the Employee class and click **Compile**.

6.  Right-click the EmployeeTest class and click **Compile**.

7.  On the Unit Test toolbar, click **Run**.
    

    > [!NOTE]
    > <P>Two test cases have been added so the results show <STRONG>2 run, 0 failed</STRONG>. You can make the test fail by not calling the retire method a second time in the testRetire method, an error will not be thrown. Change the code to the following.</P>

    
        [SysTestMethodAttribute]
        void testRetire()
        {
            // Call the retire method, first time should be successful.
            employee.retire();
        
            // Expect an exception to thrown because the employee is already retired.
            this.parmExceptionExpected(true, "Already retired");
            // employee.retire();
        }

## Capturing Code Coverage

You must enable the debugging feature to capture code coverage. In this procedure you will set the debug mode to **When Breakpoint**. You will also see the various forms available in the Unit Test framework that provide information about the test case after it is run.

### To set the debug mode and display test case results

1.  Click **Tools** \> **Options**.

2.  On the Options form, click the **Development** link.

3.  In the **Development** area, in the **Debug** section, click the **Debug mode** drop-down list, and then select **When Breakpoint**.

4.  Click **Tools** \> **Unit test** \> **Parameters**.

5.  On the Unit test parameters form, click the **General** link, select the **Record code coverage** check box. By default, the Database listener is enabled to capture code coverage.

6.  Close all forms and reports.

7.  On the Unit Test toolbar, click **Run**.

8.  On the Unit Test toolbar, click **Details**.
    

    > [!NOTE]
    > <P>You will see that the EmployeeTest test case ran. Details display regarding the date and time it was run, by whom, a percentage of the code that is covered by the test, and whether it passed or failed.</P>



9.  Click the **General** tab.
    

    > [!NOTE]
    > <P>You will see additional information about the EmployeeTest test case that includes the time in milliseconds it took to run the test.</P>



10. Click the **Environment** tab.
    

    > [!NOTE]
    > <P>You will see information about the environment in which you are running the EmployeeTest test case.</P>



11. Click the **Tests** button.
    

    > [!NOTE]
    > <P>The Test form lower pane provides information about the test case at the method level. You see the code coverage percentage broken down for each method.</P>



## Setting the Isolation Level

The isolation level of a test case varies based on the changes that the test case will make to the data. Each test case could have different needs for isolation based on what data it will change. The Unit Test framework provides four test suites that provide different levels of isolation. For more information, see [Unit Test Framework](unit-test-framework.md). In this procedure, you will override the createSuite method to use the SysTestSuiteCompanyIsolateClass test suite. This test suite constructs an empty company account for the test class and runs each test method in the company account.

### To set the isolation level for a test case

1.  In the AOT, right-click the EmployeeTest class, point to **Override Method**, and then click **createSuite**.

2.  In the Code Editor, on the line of code that reads ret = super; right-click super, and then click **Lookup Definition**.
    

    > [!NOTE]
    > <P>By default, createSuite base class returns the SysTestSuite test suite. This provides no isolation level.</P>



3.  Close the Code Editor for the base class createSuite method.

4.  In the Code Editor, change the EmployeeTest createSuite method to the following code.
    
        public SysTestSuite createSuite()
        {
            // Specify the isolation level that constructs an empty company account for the entire test class and then deletes when complete.
            return new SysTestSuiteCompanyIsolateClass(this);
        }

5.  In the AOT, right-click EmployeeTest and then click **Compile**.

6.  On the Unit Test toolbar, click **Run**.
    

    > [!NOTE]
    > <P>The first time that you run the test, after the test case executes, all tables are iterated through and must be deleted. The second time that you run the test, the test case will run much faster because information is cached about which tables should be deleted after the test case runs.</P>



## Next Steps

You should execute test cases whenever code is changed. As you build your library of test cases, organize them into groups. Test cases can be grouped into test projects or suites. For more information, see [How to: Organize Test Cases](how-to-organize-test-cases.md).

## See also

[Unit Test Framework](unit-test-framework.md)

[SysTestSuiteCompanyIsolateClass Class](https://msdn.microsoft.com/en-us/library/gg966265\(v=ax.60\))

[SysTestSuite Class](https://msdn.microsoft.com/en-us/library/gg966233\(v=ax.60\))

[How to: Organize Test Cases](how-to-organize-test-cases.md)

[How to: Access Code Coverage Details](how-to-access-code-coverage-details.md)

[How to: Create Set Up and Tear Down Logic for a Test Case](how-to-create-set-up-and-tear-down-logic-for-a-test-case.md)

[How to: Test Exceptions Using a Test Case](how-to-test-exceptions-using-a-test-case.md)

[MorphX Development Tools](morphx-development-tools.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

