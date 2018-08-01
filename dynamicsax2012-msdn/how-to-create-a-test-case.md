---
title: 'How to: Create a Test Case'
TOCTitle: 'How to: Create a Test Case'
ms:assetid: 4b081a28-b363-483d-a93a-7725c90024b2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb496525(v=AX.60)
ms:contentKeyID: 35243256
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Test Case [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, a unit test is code used to test code that implements feature logic. Unit tests include test cases, the set up and tear down of tests, and the organization of one or more test cases. To implement a unit test, you create a test case which is a new class that extends the [SysTestCase Class](https://msdn.microsoft.com/en-us/library/gg933916\(v=ax.60\)) class.

## Adding a Test Class

When you create a test case, you will create a class that must follow the naming convention best practice. Use the same name as the class that you are testing followed by Test. This will associate the test class together with the class you are testing. In this procedure, you will create a class named EmployeeTest that extends the SysTestCase class. The EmployeeTest class will test the Employee class and the Name method. For the complete steps to create the Employee class, see [Walkthrough: Testing a Class Using the Unit Test Framework](walkthrough-testing-a-class-using-the-unit-test-framework.md). The following summarizes what the code should look like in the Employee class. The Employee class should have the following code in the classDeclaration:
```X++  
    class Employee
    {
        Name name; 
        boolean retired;
    } 
```
The new method should have the following code:
```X++  
    public void new (Name _name)
    {
        Name = _name;
    } 
```
The name method should have the following code:
```X++  
    public Name _name()
    {
        return name;
    } 
```
### To create a test class

1.  Open the Development Workspace. See [How to: Open a Development Workspace](how-to-open-a-development-workspace.md) for more information.

2.  Press CTRL+D to open the Application Object Tree (AOT).

3.  In the AOT, right-click the **Classes** node and click **New Class**.

4.  Double-click **Class1** to open the Code Editor.

5.  In the Code Editor, extend SysTestCase by changing the class declaration to the following code.
    ```X++  
        [SysTestTargetAttribute('Employee',UtilElementType::Class)]
        class EmployeeTest extends SysTestCase
        {
            // Create a member variable.
            Employee employee;
        }
    ```
## Adding a Test Method

In this procedure you will add a test method. You will do this by adding a method to the EmployeeTest class. You will verify that the name of an employee is set when you use the assertEquals assertion method.

### To add a test method for the name requirement

1.  In the AOT, right-click EmployeeTest, point to **New**, and then click **Method**.

2.  In the Code Editor, change the method to the following code.
    ```X++  
        [SysTestMethodAttribute]
        void testName()
        {
           // Verify that the employee name is set correctly.
           this.assertEquals("your name", employee.name());
        }
    ```
3.  In the AOT, right-click the **EmployeeTest** class, point to **Override method** and then click **setup**.

4.  In the Code Editor, change the setup method to the following code.
    ```X++  
        public void setUp()
        {
            // Create an employee instance to use in the test.
            employee = new Employee("your name");
            super();
        }
    ```
5.  In the AOT, right-click the **EmployeeTest** class, point to **Override method** and then click **createSuite**.

6.  In the Code Editor, change the createSuite method to the following code.
    ```X++  
        public sysTestSuite createSuite()
        {
            return new SysTestSuiteCompanyIsolateClass(this);    
        }
    ```
For a list of the assertion methods, see [Unit Test Framework](unit-test-framework.md).

Next, you can run a test case and analyze the results. For more information, see [How to: Run a Test Case](how-to-run-a-test-case.md) and [How to: Display Test Case Results](how-to-display-test-case-results.md). As your library of test cases grows, you will want to organize test cases into meaningful groups. For information, see [How to: Organize Test Cases](how-to-organize-test-cases.md)anize Test Cases. It may be necessary to create set up and tear down logic at the test case or suit of test cases level. For more information see, [How to: Create Set Up and Tear Down Logic for a Test Case](how-to-create-set-up-and-tear-down-logic-for-a-test-case.md).

## See also

[Unit Test Framework](unit-test-framework.md)

[Walkthrough: Testing a Class Using the Unit Test Framework](walkthrough-testing-a-class-using-the-unit-test-framework.md)

[SysTestCase Class](https://msdn.microsoft.com/en-us/library/gg933916\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

