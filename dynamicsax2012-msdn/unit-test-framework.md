---
title: Unit Test Framework
TOCTitle: Unit Test Framework
ms:assetid: d8048fb0-7833-43c7-a8d9-6a7ad48fbb40
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa874515(v=AX.60)
ms:contentKeyID: 35252065
ms.date: 05/18/2015
mtps_version: v=AX.60
f1_keywords:
- Forms.SysTestParameters
- Forms.SysTestRecordCount
- Forms.SysTestToolbar
- MsDynAx060.Forms.SysTestParameters
- MsDynAx060.Forms.SysTestRecordCount
- MsDynAx060.Forms.SysTestToolbar
---

# Unit Test Framework [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Unit Test framework is tightly integrated into the MorphX IDE of Microsoft Dynamics AX. This integration is very important to test-driven development (TDD) because a unit test can be created alongside the feature code it is testing. For more information about TDD, see [Guidelines for Test-Driven Development](http://go.microsoft.com/fwlink/?linkid=86914).

## What is a Unit Test

A unit test is code that verifies that feature code has been implemented correctly. If you adhere to the principles of TDD, it is best for the developer who is writing the feature code to first write the unit tests. This puts emphasis on how feature code is consumed and creates a more user friendly application programming interface (API). A unit test, in the context of the Unit Test framework, includes test cases, how test cases are staged with data, and the organization of test cases. A test case is a class that extends the [SysTestCase Class](https://msdn.microsoft.com/en-us/library/gg933916\(v=ax.60\)) class. You can add test methods to test each requirement of the feature code. You should execute test cases when code is changed.

### ![Aa874515.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874515.collapse_all(en-us,AX.60).gif")Naming Convention

You should name the test class by using the same name as the class it is testing followed by the word Test. This associates the test with the test case. It also enables the Unit Test framework to collect code coverage data for the class. If this naming convention does not fit you testing needs, see the following table for options that exist.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Naming option</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Override the <a href="https://msdn.microsoft.com/en-us/library/gg933926(v=ax.60)">SysTestCase.testsElementName Method</a></p></td>
<td><p>Associates the correct class with the test.</p>
<p>Use this option if you do not want to use the naming convention of the same name as the class it is testing followed by the word Test.</p></td>
</tr>
<tr class="even">
<td><p>Override the <a href="https://msdn.microsoft.com/en-us/library/gg933927(v=ax.60)">SysTestCase.testsElementType Method</a></p></td>
<td><p>Associates the correct type with the test.</p>
<p>Use this option if you want to test a type other than a class. For example, you may want to associate a test with a table.</p></td>
</tr>
</tbody>
</table>


If code coverage is enabled and the type and name point to a valid code element, then code coverage data is collected.

### ![Aa874515.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874515.collapse_all(en-us,AX.60).gif")Example

This example illustrates how to declare a test class. You can attach an attribute to the class. This example attaches the SysTestTargetAttribute attribute to specify the target class that is tested Employee. This is usually used to redirect the target to a table.
  ```X++  
    [SysTestTargetAttribute('Employee', UtilElementType::Class)]
    class EmployeeTest extends SysTestCase
    {
    }
  ```
#### ![Aa874515.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874515.collapse_all(en-us,AX.60).gif")Test Creation Guidelines

The following list contains suggested guidelines for creating tests.

  - You must name the test class using the same name as the class you are testing followed by the word Test.

  - Group tests in a meaningful way. Do not create many similar tests, group them to recognize redundancy.

  - Do not create one test per property or method. That will lead to many simple tests with an unnecessary overhead when you set prerequisites.

  - Refactor your tests to be clean. If it is code shared by test methods on the same class, create a new private method.

  - Avoid complexity and dependencies. It may be better to avoid code sharing in unit testing.

  - Use attributes to add metadata to tests.

The following sections describe the concepts of the Unit Test framework.

### ![Aa874515.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874515.collapse_all(en-us,AX.60).gif")Run a Test Case

The Unit Test framework provides the following ways to run a test case:

  - From the Unit Test toolbar

  - Programmatically in code from the command prompt

  - From the version control functionality during code check-in

  - From the shortcut menu

For the complete steps, see [How to: Run a Test Case](how-to-run-a-test-case.md).

### ![Aa874515.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874515.collapse_all(en-us,AX.60).gif")Test Attributes Available

The Unit Test framework provides predefined attributes that you can attach to a test class or test method to provide more information. For example, you can attach the SysTestCheckInTestAttribute attribute to indicate that the test case should be run as a check-in specific test. You can define your own attributes. For more information, see [define your own attributes](how-to-categorize-test-cases-using-attributes.md).

The following table describes the predefined attributes.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Test attribute</p></th>
<th><p>Description</p></th>
<th><p>Where the attribute can be applied</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SysTestMethodAttribute</p></td>
<td><p>Indicates that a method is a unit test.</p></td>
<td><p>Apply the attribute to a method.</p></td>
</tr>
<tr class="even">
<td><p>SysTestCheckInTestAttribute</p></td>
<td><p>Indicates the test is a check-in unit test. A check-in test is run when checking in code to a version control system to ensure a proper level of quality.</p></td>
<td><p>Apply the attribute to a method or class.</p></td>
</tr>
<tr class="odd">
<td><p>SysTestNonCheckInTestAttribute</p></td>
<td><p>Indicates the test is not a check-in test.</p></td>
<td><p>Apply the attribute to a method.</p></td>
</tr>
<tr class="even">
<td><p>SysTestTargetAttribute(&lt;name&gt;,&lt;type&gt;)</p></td>
<td><p>Indicates the application object that is being tested by the test case. Examples of tested objects are class, table, and form.</p>
<p>This attribute take two parameters:</p>
<ul>
<li><p>Name - string value name of the code element to test.</p></li>
<li><p>Type - the type of the code element to test. This is optional because a class or table type can be determined by Microsoft Dynamics AX.</p></li>
</ul></td>
<td><p>Apply the attribute to a class.</p></td>
</tr>
<tr class="odd">
<td><p>SysTestInactiveTestAttribute</p></td>
<td><p>Indicates the class or method is deactivated.</p></td>
<td><p>Apply the attribute to a method.</p></td>
</tr>
</tbody>
</table>


### ![Aa874515.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874515.collapse_all(en-us,AX.60).gif")Test Methods Available

The Unit Test framework provides methods that may meet your testing needs. When you create a test case you will create a class and extend SysTestCase.

The following list contains suggested guidelines when you use assertion methods.

  - Do not assert conditions for which you already have a test.

  - Reference assertion methods where an expected value is specified.

  - Use labels instead of constant strings when you compare strings.

The following table describes the assertion methods on the SysTestCase class. For more information, follow the link for each method.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Method</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg933787(v=ax.60)">SysTestAssert.assertEquals Method</a></p></td>
<td><p>Tests if two values are equal.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg933788(v=ax.60)">SysTestAssert.assertFalse Method</a></p></td>
<td><p>Tests if the value is false.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg933789(v=ax.60)">SysTestAssert.assertNotEqual Method</a></p></td>
<td><p>Tests if two values are different.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg933790(v=ax.60)">SysTestAssert.assertNotNull Method</a></p></td>
<td><p>Tests if the value is not null.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg933791(v=ax.60)">SysTestAssert.assertNotSame Method</a></p></td>
<td><p>Tests if the objects referenced are not the same.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg933792(v=ax.60)">SysTestAssert.assertNull Method</a></p></td>
<td><p>Tests if the value is null.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg933794(v=ax.60)">SysTestAssert.assertRealEquals Method</a></p></td>
<td><p>Tests if real values differ by the amount specified in the delta.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg933795(v=ax.60)">SysTestAssert.assertSame Method</a></p></td>
<td><p>Tests if the objects referenced are the same.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg933796(v=ax.60)">SysTestAssert.assertTrue Method</a></p></td>
<td><p>Tests if the value is true.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg933799(v=ax.60)">SysTestAssert.fail Method</a></p></td>
<td><p>Enables you to create your own validation logic and then call the fail method to integrate with the Unit Test framework.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg933918(v=ax.60)">SysTestCase.parmExceptionExpected Method</a></p></td>
<td><p>Tests for an exception that is expected.</p></td>
</tr>
</tbody>
</table>


## Unit Test Toolbar

The Unit Test toolbar enables you to select a test case, run the test case, view the results, and access additional details. Access the toolbar within Microsoft Dynamics AX with the following steps, in a Development Environment, on the toolbar, click **Tools**, point to **Development tools**, point to **Unit test**, and then click **Show toolbar**.

You can also access the Unit Test toolbar with the following steps, right-click the test case, point to **Add-ins**, and then select **Run tests**. This will open the toolbar and click **Run** for you.

## Unit Test Details

Unit Test details provide information about whether the test case passed or failed, when and by whom the test was created, code coverage, and environment settings. You can access these details from the Unit Test toolbar by clicking the **Details** button.

### ![Aa874515.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874515.collapse_all(en-us,AX.60).gif")Code Coverage

During test execution, each line of code that is run is recorded. This enables you to see how well the feature area is tested and uncovers where to focus your efforts when you improve tests.

You must enable the debugging feature to capture code coverage. Forms are in the Unit Test framework to provide information about the code coverage for a test case after it is run. For information about how to enable code coverage and access the forms that provide code coverage details, see [How to: Access Code Coverage Details](how-to-access-code-coverage-details.md).

### ![Aa874515.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874515.collapse_all(en-us,AX.60).gif")Test Results Output

The Unit Test framework provides various reporting options called listeners. By default, the database is used as a listener when you run the test case using the Unit Test toolbar. You can add listeners in the Unit Test parameters form. For information about how to select additional listeners for your test cases, see [How to: Display Test Case Results](how-to-display-test-case-results.md). The following is a list of the test listeners that the Unit Test framework provides:

  - Database

  - Infolog

  - Infolog (result only)

  - Print window

  - Progress bar

  - Text file

  - XML file

## Test Organization

As the number of test cases grows it becomes increasingly more important to organize test cases into groups. Test cases can be grouped into test suites. A test suite can contain one or more test cases and other test suites. This enables test cases to be grouped in a hierarchy. For more information about how to create test suites and projects, see [How to: Organize Test Cases](how-to-organize-test-cases.md).

You can also use attributes to categorize groups of test cases. For example, you might want to group all of the test cases that cross module boundaries as integration tests. You can define a new test attribute class that is named IntegrationTest that inherits from the base test attribute BaseTest. After you compile the attribute class, you can attach the attribute to test cases that you want to run when executing integration level testing. For more information, see [How to: Categorize Test Cases Using Attributes](how-to-categorize-test-cases-using-attributes.md).

### ![Aa874515.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874515.collapse_all(en-us,AX.60).gif")Set Up and Tear Down Shared Data

You can set up and tear down data at the test case or the test suite level. This provides benefits beyond having your test cases organized in a meaningful way. If all your tests share the same set up or tear down code then put it in setUp and tearDown methods of the test case. The framework makes sure that the code is executed before and after each test in your test class.

Another option exists if you want the code to be executed one time before the whole test class and after the last test method. You will create a test suite and override the setUp and tearDown methods.

For more information, see [How to: Create Set Up and Tear Down Logic for a Test Case](how-to-create-set-up-and-tear-down-logic-for-a-test-case.md).

### ![Aa874515.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874515.collapse_all(en-us,AX.60).gif")Isolating Test Cases

The isolation level of a test case varies based on the changes that the test case will make to the data. Each test case could have different needs for isolation based on what data it will change. The Unit Test framework provides four test suites that provide different levels of isolation. The following table describes the test suites by the level of isolation that they provide.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Test suite</p></th>
<th><p>Isolation level description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg966233(v=ax.60)">SysTestSuite Class</a></p></td>
<td><p>Provides no isolation. This is the default test suite.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg966265(v=ax.60)">SysTestSuiteCompanyIsolateClass Class</a></p></td>
<td><p>Constructs an empty company account for the test class. All test methods run in this company account, and then the company account is deleted.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg966273(v=ax.60)">SysTestSuiteCompanyIsolateMethod Class</a></p></td>
<td><p>Constructs an empty company account for each test method. The company is used in each test method and then the company account is deleted. This provides the best isolation at the cost of performance. This is caused by a company account created and deleted for each test method.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg966292(v=ax.60)">SysTestSuiteTTS Class</a></p></td>
<td><p>Wraps each test method in a transaction. After the test method has executed, the transaction is aborted.</p>
<p>This isolation level performs well but there are two limitations.</p>
<ul>
<li><p>Does not work for tests that commit data.</p></li>
<li><p>The parmExceptionExpected exception is not supported.</p></li>
</ul></td>
</tr>
</tbody>
</table>


### ![Aa874515.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874515.collapse_all(en-us,AX.60).gif")Example

The following code example illustrates how to use one of the different levels of isolation. You will override the createSuite method in your test case and set the return value to the appropriate test suite.
  ```X++  
    class SysTestSuite createSuite()
    {
        // Set the isolation level to construct a company account for the
        // entire test class.
        return new SysTestSuiteCompanyIsolateClass(this);
    }
  ```
For a detailed example that creates, runs, and evaluates a test case, see [Walkthrough: Testing a Class Using the Unit Test Framework](walkthrough-testing-a-class-using-the-unit-test-framework.md).

## See also

[How to: Create a Test Case](how-to-create-a-test-case.md)

[How to: Run a Test Case](how-to-run-a-test-case.md)

[How to: Display Test Case Results](how-to-display-test-case-results.md)

[How to: Access Code Coverage Details](how-to-access-code-coverage-details.md)

[How to: Organize Test Cases](how-to-organize-test-cases.md)

[How to: Create Set Up and Tear Down Logic for a Test Case](how-to-create-set-up-and-tear-down-logic-for-a-test-case.md)

[How to: Test Exceptions Using a Test Case](how-to-test-exceptions-using-a-test-case.md)

[SysTestCase Class](https://msdn.microsoft.com/en-us/library/gg933916\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

