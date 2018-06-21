---
title: 'How to: Run a Test Case'
TOCTitle: 'How to: Run a Test Case'
ms:assetid: 9cbd598e-a1aa-4ef0-81ba-8781e224dcb4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb496534(v=AX.60)
ms:contentKeyID: 35248226
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Run a Test Case [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX includes a framework to create, run, and analyze test cases. Once you create a test case, you will want to run it to analyze the results. Microsoft Dynamics AX provides the following ways to run a test case:

  - From the Unit Test toolbar

  - Programmatically in code at the command prompt

  - From the version control functionality during code check-in

  - From the shortcut menu

For information about how to create a test case, see [How to: Create a Test Case](how-to-create-a-test-case.md). The steps to run a test case are provided in the following procedures.

## Running a Test Case from the Unit Test Toolbar

In this procedure, you will access the Unit Test toolbar to run a test case.

### To run a test case from the Unit Test toolbar

1.  Click **Tools** \> **Unit test** \> **Show toolbar**.
    

    > [!NOTE]
    > <P>This displays the Unit Test toolbar.</P>



2.  On the Unit Test toolbar, click the **Test** drop-down list, and then select the test case that you want to run.
    

    > [!NOTE]
    > <P>If this is the first time that you have used the Unit Test Toolbar there will be no tests in the drop-down list, you must type the name of the test to run.</P>



3.  Click the **Parameters** button. The following table describes the options in the Unit test parameters form.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Option</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Record code coverage</p></td>
    <td><p>Mark this check box to record the lines of code that are executed to evaluate your test coverage. For more information, see <a href="how-to-access-code-coverage-details.md">How to: Access Code Coverage Details</a>.</p></td>
    </tr>
    <tr class="even">
    <td><p>Record number of records</p></td>
    <td><p>Mark this check box to record the number of records inserted during execution of a test case.</p>
    <p>As you verify data as a measure of quality for your test, use this check box to track inserts to the database. This provides the ability to track cleanup of these records. By tracking all inserts from a unit test and then deleting all the inserted records, the stability of test cases running successively is improved.</p></td>
    </tr>
    <tr class="odd">
    <td><p>Action on error</p></td>
    <td><p>From the drop-down, you can opt to <strong>Continue</strong> or <strong>Fail</strong> when an exception occurs.</p></td>
    </tr>
    <tr class="even">
    <td><p>Filter</p></td>
    <td><p>From the drop-down, you can opt to run <strong>Active tests</strong>, <strong>Check-in tests</strong>, or <strong>All tests</strong>. Use attributes to indicate that a test case is active or a check-in test. You can add more categories to filter on, see <a href="how-to-categorize-test-cases-using-attributes.md">How to: Categorize Test Cases Using Attributes</a>.</p></td>
    </tr>
    </tbody>
    </table>


4.  Close the Unit test parameters form.

5.  On the Unit test toolbar, click **Run**.
    

    > [!NOTE]
    > <P>When you run the test from the Unit Test toolbar, the Unit Test framework uses the database listener to store the details about the test. For more information about listeners, see <A href="how-to-display-test-case-results.md">How to: Display Test Case Results</A>.</P>



## Running a Test Case from the Command Prompt

In this procedure, you will run a test case at the command prompt. There is only one startup command to run tests RunTestProject. This command is used at the project, suite, and test case level. First, the Unit Test framework will search for the name that you specify as a project. If the project is not found, it will search for a test suite with the specified name, and finally it will search for a test case.

### To run a test case at the command prompt

1.  On the taskbar, click **Start**, and then click **Run**.

2.  Type **cmd** in the Run box and then click **OK**.

3.  At the command prompt, type the following: ax32 -StartupCmd=RunTestProject\_\<name of test\>
    

    > [!NOTE]
    > <P>When you use this command, Microsoft Dynamics AX will start and run the test. The Unit Test framework uses the XML listener to store details about the test. The file is saved to the default log directory at C:\Users\&lt;username&gt;\Microsoft\Dynamics Ax\Log\. For more information about listeners, see <A href="how-to-display-test-case-results.md">How to: Display Test Case Results</A>.</P>



## Running a Test Case During Version Control Check-in

In this procedure, you will run a test case during the version control code check-in process. You will specify the project that contains a test case to run using the version control functionality during code check-in. If the test fails, code check-in will stop.

### To run a test case during version control check-in of code

1.  Click **Version Control** \> **System Settings**.

2.  In the **Version Control Configuration** form, in the **Best Practice Settings** section, set the **Test project** to the project that you want to run during check-in of code. For more information about version control, see [Version Control System](version-control-system.md).

## Running a Test Case from the Shortcut Menu

In this procedure, you will run a test case from the shortcut menu.

### To run a test case from the shortcut menu

  - In the AOT, right-click the test case you want to run, point to **Add-ins**, and then click **Run tests**.
    

    > [!NOTE]
    > <P>This will open the Unit Test toolbar and initiate the running of the test case.</P>



Next, you can analyze the results of the test case. For more information, see [How to: Display Test Case Results](how-to-display-test-case-results.md). As your library of test cases grows you will want to organize test cases in meaningful groups. For more information, see [How to: Organize Test Cases](how-to-organize-test-cases.md). It may be required to create set up and tear down logic at the test case or suit level. For more information, see [How to: Create Set Up and Tear Down Logic for a Test Case](how-to-create-set-up-and-tear-down-logic-for-a-test-case.md).

## See also

[Unit Test Framework](unit-test-framework.md)

[Walkthrough: Testing a Class Using the Unit Test Framework](walkthrough-testing-a-class-using-the-unit-test-framework.md)

[How to: Create a Test Case](how-to-create-a-test-case.md)

[SysTestCase Class](https://msdn.microsoft.com/en-us/library/gg933916\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

