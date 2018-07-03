---
title: 'How to: Display Test Case Results'
TOCTitle: 'How to: Display Test Case Results'
ms:assetid: c013b1de-10cd-45ee-a3c3-96eaacb162dc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb496538(v=AX.60)
ms:contentKeyID: 35250077
ms.date: 05/18/2015
mtps_version: v=AX.60
f1_keywords:
- Forms.SysTestLineLog
- Forms.SysTestTable
- MsDynAx060.Forms.SysTestLineLog
- MsDynAx060.Forms.SysTestTable
---

# How to: Display Test Case Results 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX includes a framework to create, run, and analyze test cases. After you create and run a test case, you will want to view the results. Various forms exist to display details about test cases. You can also enable one or more listeners. Each listener produces unique output options to display test case results.

For information about creating and running a test case, see [How to: Create a Test Case](how-to-create-a-test-case.md) and [How to: Run a Test Case](how-to-run-a-test-case.md).

## Displaying Results

The following table describes Microsoft Dynamics AX forms that display test case results.

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
<td><p>Displays date, time, author, percent of code coverage, duration that the test ran, number of records that are updated by the test, and a pass/fail status for each test.</p></td>
</tr>
<tr class="even">
<td><p><strong>Test jobs</strong> (General tab)</p></td>
<td><p>On the <strong>Test jobs</strong> form, click the <strong>General</strong> tab.</p></td>
<td><p>Displays details specific to an individual test including code coverage, date, time, author, and the duration that the test ran.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Test jobs</strong> (Environment tab)</p></td>
<td><p>On the <strong>Test jobs</strong> form, click the <strong>Environment</strong> tab.</p></td>
<td><p>Displays details about the computer configuration that the test ran under. This includes the build number, client mode, database details, and the operating system for the client and server.</p></td>
</tr>
<tr class="even">
<td><p><strong>Test</strong></p></td>
<td><p>On the <strong>Test jobs</strong> form, click the <strong>Tests</strong> button.</p></td>
<td><p>The <strong>Overview</strong> tab displays test case code coverage, duration that the test ran, number of records that were updated by the test, and the status. Also displays the same information at the method level.</p>
<p>The <strong>General</strong> tab displays detail of each test regarding identification, time, and code coverage.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Comparison</strong></p></td>
<td><p>On the <strong>Test</strong> form, click the <strong>Coverage</strong> button.</p></td>
<td><p>Displays code coverage details regarding the lines of code that were executed. Click <strong>Compare</strong> to see the differences.</p></td>
</tr>
<tr class="even">
<td><p><strong>Infolog</strong></p></td>
<td><p>On the <strong>Test</strong> form, click the <strong>Infolog</strong> button.</p></td>
<td><p>Displays status information about the test case and the methods that start and finish in an <strong>Overview</strong> tab that displays all tests or the <strong>General</strong> tab that displays detail for a specific test.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Test log</strong></p></td>
<td><p>On the <strong>Test</strong> form, click the <strong>Log</strong> button.</p></td>
<td><p>Displays the method name, log type, and the log messages.</p></td>
</tr>
</tbody>
</table>


You can select the output format to display your results by clicking one or more listeners. The available listeners include output to the database, Infolog, Message window, Print window, Progress bar, text file, and XML file. The following procedure describes how to enable one or more listeners to identify the output that you want.

### To select the output format to display results

1.  Click **Tools** \> **Unit test** \> **Parameters**.

2.  In the Unit test parameters form, click the **Listeners** link.

3.  From the **Remaining** pane, click the listeners that you want to enable, and then click **\<** to move them to the **Selected** pane.
    

    > [!NOTE]
    > <P>For listeners that will send output to a file, the default location is the application log directory at C:\Program Files\Microsoft Dynamics AX\60\Client\Log. To change location of the file, you must programmatically register a listener. For an example, see <A href="how-to-run-a-test-case.md">How to: Run a Test Case</A>.</P>
    > <P>This procedure described how to select the output at the unit test level. To select listeners for a test project, right-click the project and then click <STRONG>Settings</STRONG>.</P>



If the output options provided by Microsoft Dynamics AX do not meet your needs, you can create your own listener. You might want to create your own listener if you want to log on to a different database, need a specific file format, or use a .NET object. The following procedure describes how to create a listener class by implementing the [SysTestListener Interface](https://msdn.microsoft.com/en-us/library/gg933994\(v=ax.60\)) interface.

### To create an alternative output format

1.  In the AOT, right-click the **Classes** node and click **New Class**.

2.  Double-click the new class to open it in the Code Editor.

3.  Change the code to the following.
    ```X++  
        public class AlternativeListener implements SysTestListener
         {
         }
    ```
4.  Add methods to provide the behavior of the alternative listener.

5.  Press F7 to compile the class.

6.  In the AOT, expand the **Data Dictionary** node, expand the **Base Enums** node, right-click the **SysTestListeners** enumeration, and then click **New Element**.

7.  Click the new element, open the **Properties** window, and change the name and the label to AlternativeListener.
    

    > [!NOTE]
    > <P>This causes the new listener to display on the Test parameters form.</P>



8.  Click **Tools** \> **Unit test** \> **Parameters**.

9.  On the Unit test parameters form, click the **Listeners** link.
    

    > [!NOTE]
    > <P>The AlternativeListener will be listed with the Remaining listeners. You will use the new listener the same as the existing default listeners. For an example of how to use a listener, see <A href="how-to-run-a-test-case.md">How to: Run a Test Case</A>.</P>



Next, think about how to organize your tests in a meaningful way. For information, see [How to: Organize Test Cases](how-to-organize-test-cases.md). It may be necessary to create setup and tear down logic at the test case or suite of test cases level. For more information, see [How to: Create Set Up and Tear Down Logic for a Test Case](how-to-create-set-up-and-tear-down-logic-for-a-test-case.md).

## See also

[Unit Test Framework](unit-test-framework.md)

[Walkthrough: Testing a Class Using the Unit Test Framework](walkthrough-testing-a-class-using-the-unit-test-framework.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

