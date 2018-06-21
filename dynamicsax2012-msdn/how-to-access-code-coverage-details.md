---
title: 'How to: Access Code Coverage Details'
TOCTitle: 'How to: Access Code Coverage Details'
ms:assetid: 93275cbb-2ba0-49e7-8b91-be35b7e998ab
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb496533(v=AX.60)
ms:contentKeyID: 35247546
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Access Code Coverage Details [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX includes a framework to create, run, and analyze test cases. After you create and run a test case, you may be interested in the percentage of code that your tests cover. Various forms exist to display details about test cases. You can also enable one or more listeners. Each listener produces unique output options to display test case results.

For information about creating and running a test case, see [How to: Create a Test Case](how-to-create-a-test-case.md) and [How to: Run a Test Case](how-to-run-a-test-case.md).

## Displaying Code Coverage Details

You must enable the debugging feature to capture code coverage. In this procedure you will set the debug mode to **When Breakpoint**. You will also see the various forms available in the Unit Test framework that provide information about the test case after it is run.

### To set the debug mode and record code coverage

1.  In a Microsoft Dynamics AX development workspace, click **Tools** \> **Options**.

2.  On the **Options** form, click the **Development** link.

3.  On the **Set up options for the development workspace** area, in the **Debug** section, click the **Debug mode** drop-down list, click **When Breakpoint**, and then click the **Close** button.

4.  Click **Tools** \> **Unit test** \> **Parameters**.

5.  On the Unit test parameters form, click the **General** link, click the **Record code coverage** check box and then click the **Close** button. By default, the Database listener is enabled to capture code coverage.

6.  Click **Tools** \> **Unit test** \> **Show toolbar**.

7.  On the Unit Test toolbar, click a test to run, and then click **Run**.
    

    > [!NOTE]
    > <P>When you do not want to capture code coverage, clear the <STRONG>Record code coverage</STRONG> check box. Capturing code coverage causes decreased performance.</P>



The following table describes the Microsoft Dynamics AX forms and details about code coverage.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Form name</p></th>
<th><p>How to access</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Test jobs</strong> (Overview tab)</p></td>
<td><ol>
<li><p>Click <strong>Tools</strong> &gt; <strong>Unit test</strong> &gt; <strong>Test jobs</strong>.</p></li>
<li><p>On the Unit test toolbar, click the <strong>Details</strong> button.</p></li>
</ol></td>
<td><p>Displays date, time, author, percent of code coverage, and a pass/fail status for each test.</p></td>
</tr>
<tr class="even">
<td><p><strong>Test jobs</strong> (General link)</p></td>
<td><p>On the <strong>Test jobs</strong> form, click the <strong>General</strong> tab.</p></td>
<td><p>Displays detail specific to an individual test including code coverage, date, time, author, and the duration that the test ran.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Test</strong></p></td>
<td><p>On the <strong>Test jobs</strong> form, click the <strong>Tests</strong> button.</p></td>
<td><p>Displays test case code coverage, status and the duration that the test ran. Also displays the same information at the method level.</p></td>
</tr>
<tr class="even">
<td><p><strong>Comparison</strong></p></td>
<td><p>On the <strong>Test</strong> form, click the <strong>Coverage</strong> button.</p></td>
<td><p>Displays code coverage details to differentiate between two versions of a class. Click <strong>Compare</strong> to see the differences.</p></td>
</tr>
</tbody>
</table>


You can also send the code coverage details to an XML file. The following procedure describes how to access code coverage details in XML format.

### To access code coverage details in XML format

1.  Click **Tools** \> **Unit test** \> **Parameters**.

2.  In the **Unit test parameters** form, click the **Listeners** link.

3.  From the **Remaining** pane, click **XML File** and click **\<** to add the listener to the **Selected** pane.

4.  Close the **Unit test parameters** form.

5.  Click **Tools** \> **Unit test** \> **Show toolbar**.

6.  On the Unit Test toolbar, click a test to run, and then click **Run**.

7.  Open the XML file. The default log directory and file name is C:\\Users\\\[User Name\]\\Microsoft\\Dynamics AX\\Log\\Unit.xml
    

    > [!NOTE]
    > <P>In the XML file, you can see the percentage of code coverage at the test case level and the method level.</P>



Next, think about how to organize your tests in a meaningful way. For information, see [How to: Organize Test Cases](how-to-organize-test-cases.md). It may be necessary to create setup and tear down logic at the test case or suite of test cases level. For more information, see [How to: Create Set Up and Tear Down Logic for a Test Case](how-to-create-set-up-and-tear-down-logic-for-a-test-case.md).

## See also

[Unit Test Framework](unit-test-framework.md)

[Walkthrough: Testing a Class Using the Unit Test Framework](walkthrough-testing-a-class-using-the-unit-test-framework.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

