---
title: Top Best Practices to Consider
TOCTitle: Top Best Practices to Consider
ms:assetid: ef35672f-d23e-45ad-a1f6-8641b0e9ee89
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967435(v=AX.60)
ms:contentKeyID: 35253291
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Top Best Practices to Consider [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following sections provide guidance to avoid best practice violations. The sections provide guidance in the following areas:

  - Formatting

  - Naming

  - Commenting Code

  - XML Documentation

  - Labels and text

  - Database

  - Exceptions

## General Best Practice Guidance

The following list provides general best practices guidance.

  - Favor using positive logic.

  - Use constants instead of numeric literals.

  - Use enumerations in place of constants.

  - Use explicit access modifiers.

  - Do not use method parameters as an l-value.

### ![Cc967435.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967435.collapse_all(en-us,AX.60).gif")Formatting Guidance

The following table provides formatting best practice guidance.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Best Practice</p></th>
<th><p>Example</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Place the opening brace at the beginning of the next line.</p></td>
<td><p>if (someExpression)</p>
<p>{</p>
<p>doSomething();</p>
<p>}</p></td>
</tr>
<tr class="even">
<td><p>Align the closing brace with the corresponding opening brace.</p></td>
<td><p>if (someExpression)</p>
<p>{</p>
<p>doSomething();</p>
<p>}</p></td>
</tr>
<tr class="odd">
<td><p>Place the opening and closing braces each on their own line.</p></td>
<td><p>if (someExpression)</p>
<p>{</p>
<p>doSomething();</p>
<p>}</p></td>
</tr>
<tr class="even">
<td><p>Do not omit braces. Braces are not optional because they increase code readability and maintainability. They should be included, even for single statement blocks.</p></td>
<td><p>if (someExpression)</p>
<p>{</p>
<p>doSomething();</p>
<p>}</p></td>
</tr>
<tr class="odd">
<td><p>Omit braces for switch statements. These braces can be omitted because the case and break statements clearly indicate the beginning and ending.</p></td>
<td><p>case 0:</p>
<p>doSomething();</p>
<p>break;</p></td>
</tr>
<tr class="even">
<td><p>Use a single space in the following cases:</p>
<ul>
<li><p>On either side of the assignment operator.</p></li>
</ul></td>
<td><p>Correct: cust.Name = &quot;Jo&quot;;</p>
<p>Incorrect: cust.Name=&quot;Jo&quot;;</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>After the comma between parameters.</p></li>
</ul></td>
<td><p>Correct:</p>
<p>public void doSomething(int _x, int _y)</p>
<p>Incorrect:</p>
<p>public void doSomething(int _x,int _y)</p></td>
</tr>
<tr class="even">
<td><ul>
<li><p>Between arguments.</p></li>
</ul></td>
<td><p>Correct: myAddress(myStr, 0, 1)</p>
<p>Incorrect: myAddress(myStr,0,1)</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>Before flow control statements.</p></li>
</ul></td>
<td><p>Correct: while (x == y)</p>
<p>Incorrect: while(x == y)</p></td>
</tr>
<tr class="even">
<td><ul>
<li><p>Before and after binary operators.</p></li>
</ul></td>
<td><p>Correct: if (x == y)</p>
<p>Incorrect: if (x==y)</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>After the semicolon between the parts of a for statement.</p></li>
</ul></td>
<td><p>Correct: for (i = 0; i &lt; 10; i++)</p>
<p>Incorrect: for (i = 0;i &lt; 10;i++)</p></td>
</tr>
<tr class="even">
<td><p>Do not use any spaces in the following cases:</p>
<ul>
<li><p>After the opening or before the closing parenthesis.</p></li>
</ul></td>
<td><p>Correct: myAddress(myStr, 0, 1)</p>
<p>Incorrect: myAddress( myStr, 0, 1 )</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>Between a member name and opening parenthesis.</p></li>
</ul></td>
<td><p>Correct: myAddress()</p>
<p>Incorrect: myAddress ()</p></td>
</tr>
<tr class="even">
<td><ul>
<li><p>Before or after the brackets.</p></li>
</ul></td>
<td><p>Correct: x = dataArray[index];</p>
<p>Incorrect: x = dataArray[ index ];</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>Before or after unary operators.</p></li>
</ul></td>
<td><p>Correct: if (!y)</p>
<p>Incorrect: if (! y)</p></td>
</tr>
<tr class="even">
<td><p>Use four spaces as the standard indent. The tab key in code editor inserts four spaces. Indent in the following cases:</p>
<ul>
<li><p>The contents of code blocks.</p></li>
</ul></td>
<td><p>if (someExpression)</p>
<p>{</p>
<p>doSomething();</p>
<p>}</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>Case blocks even though they do not use braces.</p></li>
</ul></td>
<td><p>switch (someExpression)</p>
<p>{</p>
<p>case 0:</p>
<p>doSomething();</p>
<p>break;</p>
<p>…</p>
<p>}</p></td>
</tr>
<tr class="even">
<td><ul>
<li><p>A wrapped line one indent from the previous line.</p></li>
</ul></td>
<td><p>lastAccount = this.doSomething(</p>
<p>cust,</p>
<p>firstAccount,</p>
<p>startDate,</p>
<p>endDate);</p></td>
</tr>
<tr class="odd">
<td><p>Wrap lines that get too long to fit on a single line.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Wrap shorter lines to improve clarity.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Place each wrapped select and while select statement keyword at the beginning of a new line. The content associated with each keyword should be indented by one indent under the corresponding keyword.</p></td>
<td><p>select firstonly cust</p>
<p>where someExpression1</p>
<p>&amp;&amp; someExpression2</p>
<p>&amp;&amp; someExpression3;</p>
<p></p>
<p>select count(RecId)</p>
<p>from cust</p>
<p>where someExpression1</p>
<p>&amp;&amp; someExpression2</p>
<p>&amp;&amp; someExpression3;</p>
<p></p>
<p>while select firstonly cust</p>
<p>order by Name, AccountNum</p>
<p>where someExpression1</p>
<p>&amp;&amp; someExpression2</p>
<p>&amp;&amp; someExpression3</p>
<p>{</p>
<p>…</p>
<p>}</p></td>
</tr>
<tr class="even">
<td><p>Do not use more or less than four spaces to force special alignment.</p></td>
<td><p>Right</p>
<p>lastAccount = this.doSomething(</p>
<p>cust,</p>
<p>firstAccount,</p>
<p>startDate,</p>
<p>endDate);</p>
<p>Wrong (indent is 14 spaces)</p>
<p>last = this.do(</p>
<p>cust,</p>
<p>firstAccount,</p>
<p>startDate,</p>
<p>endDate);</p></td>
</tr>
<tr class="odd">
<td><p>Put each indented parameter or argument on a separate line.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Use switch statements over consecutive if statements.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Do not use parenthesis around the value of the cases of a switch statement.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Do not put the closing parenthesis for a method call on a new line.</p></td>
<td></td>
</tr>
</tbody>
</table>


### ![Cc967435.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967435.collapse_all(en-us,AX.60).gif")Naming Guidance

The following table provides naming best practice guidance.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Best Practice</p></th>
<th><p>Example</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Use Camel case naming for member variables, method names, and local variables.</p></td>
<td><p>serverClass;</p></td>
</tr>
<tr class="even">
<td><p>Use Pascal case naming for Application Object Tree (AOT) elements.</p></td>
<td><p>AddressCountyRegion;</p></td>
</tr>
<tr class="odd">
<td><p>Prefix parameter names with an underscore (_).</p></td>
<td><p>myJob(Args _args)</p></td>
</tr>
<tr class="even">
<td><p>Do not use Hungarian notation. Do not encode the type of a variable in its name.</p></td>
<td><p>Incorrect: strName</p></td>
</tr>
<tr class="odd">
<td><p>Avoid prefixing local variables.</p></td>
<td><p>Incorrect: stringName or intCount</p></td>
</tr>
<tr class="even">
<td><p>Use meaningful and self-documenting names.</p></td>
<td></td>
</tr>
</tbody>
</table>


### ![Cc967435.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967435.collapse_all(en-us,AX.60).gif")Commenting Code Guidance

This section provides best practice guidance for writing code comments. Comments should be used to describe the intent, algorithmic overview, and logical flow. Provide comments so that someone other than the original developer could understand the behavior and purpose of the code. It is a best practice that most code will have comments reflecting the developer intent and approach for the code. Use comments liberally. Include comments that indicate who made the changes, when the changes were made, why the changes were added, and what the changes do. Comments are particularly beneficial when multiple parties are involved in modifying and maintaining code. The following table provides code commenting best practice guidance.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Best Practice</p></th>
<th><p>Example</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Do not use comments that repeat the code.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Do not use multi-line syntax /* … */ for comments. The single-line syntax // … is preferred even when a comment spans multiple lines.</p></td>
<td><p>public int getCount()</p>
<p>{</p>
<p>;</p>
<p></p>
<p>// This comment spans multiple</p>
<p>// lines because it has</p>
<p>// a lot to say. The use of</p>
<p>// multi-line syntax is</p>
<p>// not allowed.</p>
<p>…</p>
<p>}</p></td>
</tr>
<tr class="odd">
<td><p>Do not place comments at the end of a line unless the comment is very short. In most cases, comments should be placed above the code.</p></td>
<td><p>public class ArrayList</p>
<p>{</p>
<p>int count; // -1 indicates uninitialized array</p>
<p>}</p></td>
</tr>
<tr class="even">
<td><p>Remove TODO comments well in advance of a release.</p></td>
<td><p>// TODO: The TODO comments should start with TODO.</p>
<p>For more information, see <a href="todo-comments-for-x-developer-tasks.md">TODO Comments for X++ Developer Tasks</a>.</p></td>
</tr>
</tbody>
</table>


### ![Cc967435.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967435.collapse_all(en-us,AX.60).gif")XML Documentation Guidance

XML documentation should provide information related to usage. It should help a programmer decide if they want to use the method. The following list provides best practice guidance for XML documentation.

  - Add XML documentation with meaningful content.

  - Use XML documentation to provide users and potential users with the information they need.

  - Do not use XML documentation to discuss implementation details or other items not related to use.

  - Do not add XML documentation for the sake of improving code coverage.

  - Be aware of the methods with automatically generated XML documentation; for example, New and construct.

### ![Cc967435.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967435.collapse_all(en-us,AX.60).gif")Labels and Text Guidance

The following list provides best practice guidance for labels and text.

  - Use labels for text that will appear on the user interface.

  - Put labels in double quotes.

  - Do not concatenate multiple labels together.

  - Use single quotes for text that will not appear in the user interface.

### ![Cc967435.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967435.collapse_all(en-us,AX.60).gif")Database Guidance

The following list provides best practice guidance related to the database.

  - Include a try catch around all transactions that could result in deadlock.

  - Make sure the try for a deadlock is idempotent meaning no matter how many times the try is attempted, it will yield the same result.

  - Consider the clarity when deciding the number of return statements in a method.

  - Use throw instead of ttsAbort.

  - Avoid display methods where possible.

  - Set Optimistic Concurrency Control (**OccEnabled**) to **Yes** for most tables.

  - Do not include user interaction inside a database transaction.

  - Keep database transactions as short as possible.

  - Run code on the Application Object Server (AOS) whenever possible.

  - Use where clauses in select statements and in queries that align with indexes.

  - If method calls are used to test conditions, put the method calls after the other conditions. If the other conditions fail, then you will not incur the cost of running the method.

  - Minimize the size of database transactions.

  - Consider specifying a field list in select statements to increase performance.

  - Use firstonly where applicable to increase performance.

  - Use aggregates in the selection criteria instead of having the code do the aggregation. If aggregations are issued in the select statement rather than in code, the processing is done at the database server which is much more efficient.

  - Use table joins instead of nested while loops. Whenever possible use a join in the select statement rather than using a while loop and then an inner while loop on the related table. This reduces the amount of communication between the AOS and the database.

  - Do not include any sort of user interaction in a transaction.

### ![Cc967435.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967435.collapse_all(en-us,AX.60).gif")Exceptions Guidance

The following list provides best practice guidance related to exceptions.

  - Throw an exception to stop the currently executing X++ call stack.

  - Include a localized error message with all thrown exceptions.

  - Use the info, warning, and error functions without a thrown exception in cases where the executing X++ call stack should not be stopped.

  - Use throw with the static helpers on the Error class such as Error::missingParameter and Error::wrongUseOfFunction for errors targeted at developers.

  - Do not throw an exception for an error condition that you expect will need to be caught.

  - Do not throw an exception for invalid assumption cases where a Debug::assert is more appropriate.

## See also

[X++ Coding Standards](x-coding-standards.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

