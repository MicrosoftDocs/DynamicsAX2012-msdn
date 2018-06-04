---
title: 'How to: Categorize Test Cases Using Attributes'
TOCTitle: 'How to: Categorize Test Cases Using Attributes'
ms:assetid: 14cefa40-2f0a-49a5-ae75-bf2e98f9847c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh272117(v=AX.60)
ms:contentKeyID: 36536727
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Categorize Test Cases Using Attributes 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The unit test framework uses the attribute feature that is found in the X++ language. The purpose of an attribute is to represent or store metadata about types and methods. Use test attributes to do the following tasks:

  - Specify the target class or target table for your test

  - Specify which methods on the unit test class are the test methods

  - Specify which tests are the tests for the check in process and are integrated with a version control system

This topic provides a summary of the attributes and how they are used in code. For the complete steps, see [Walkthrough: Testing a Class Using the Unit Test Framework](walkthrough-testing-a-class-using-the-unit-test-framework.md). The following table describes the attributes that are predefined by the unit test framework.

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
<td><p>Indicates that a method is a test method. A test method must be public, void, and take no parameter values.</p></td>
<td><p>Apply the attribute to a method.</p></td>
</tr>
<tr class="even">
<td><p>SysTestCheckInTestAttribute</p></td>
<td><p>Indicates that the test is a check in test. A check in test is run when you check in code to a version control system to make sure that there is a good level of quality.</p></td>
<td><p>Apply the attribute to a method or class.</p></td>
</tr>
<tr class="odd">
<td><p>SysTestNonCheckInTestAttribute</p></td>
<td><p>Indicates the test is not a check in test. This is used when the class is marked with the attribute SysTestCheckInAttribute but it has one or more methods that should not be check in methods.</p></td>
<td><p>Apply the attribute to a method or class.</p></td>
</tr>
<tr class="even">
<td><p>SysTestTargetAttribute(&lt;name&gt;,&lt;type&gt;)</p></td>
<td><p>Indicates the application object that is being tested by the test case. Examples of objects to test are class, table, and form.</p>
<p>This attribute takes two parameters:</p>
<ul>
<li><p>Name - string value name of the code element to test.</p></li>
<li><p>Type - the type of the code element to test. If the type is not specified, the Unit Test framework treats it as a class.</p></li>
</ul></td>
<td><p>Apply the attribute to a class.</p></td>
</tr>
<tr class="odd">
<td><p>SysTestInactiveTestAttribute</p></td>
<td><p>Indicates that the test is deactivated.</p></td>
<td><p>Apply the attribute to a method or class.</p></td>
</tr>
</tbody>
</table>


## Examples

### To specify the target class for your test

  - This example illustrates how to attach an attribute to a class to specify that it should be used for a test. This example attaches the SysTestTargetAttribute attribute to specify the class that is tested is the Employee class.
    
        [SysTestTargetAttribute(classStr(Employee), UtilElementType::Class)]
        class EmployeeTest extends SysTestCase
        {
        }

### To specify which methods on the unit test class are test methods

  - The following code example illustrates how to attach an attribute to a method to indicate that it is a test method.
    
        [SysTestMethodAttribute]
        public void myTest()
        {
        }

### To specify which tests are tests for check in and integrate with a version control system

  - You can run and classify the most critical test methods as check in tests. When you set up the version control system, you can specify which test project to run during check in. You can also specify whether to run all test methods, or only the test methods that are marked as check in tests. If all tests pass, the code will be submitted in the version control system. For more information about version control, see [Version Control System](version-control-system.md).The following code example illustrates how to attach an attribute to a method to indicate that it is a check in test method.
    
        [SysTestCheckInTestAttribute]
        public void myCheckInTest()
        {
        }

## See also

[Unit Test Framework](unit-test-framework.md)

[Attributes on X++ Types and Methods](attributes-on-x-types-and-methods.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

