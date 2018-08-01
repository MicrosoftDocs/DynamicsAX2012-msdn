---
title: Setting Development Options
TOCTitle: Setting Development Options
ms:assetid: 03cd4e38-d045-4802-a06b-4bedc7c2e548
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa572935(v=AX.60)
ms:contentKeyID: 35240244
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Setting Development Options [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To set development options in Microsoft Dynamics AX click **Tools** \> **Options**, and then click the **Development** link. The following table describes the options for development.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>General</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Startup project</p></td>
<td><p>Specify the project to load at startup.</p></td>
</tr>
<tr class="even">
<td><p>Message limit</p></td>
<td><p>Specify the maximum number of lines to save in the info window. When this limit is reached, the lines are discarded.</p>
<p>To view the discarded lines, you can examine the objects log file in the systems main directory. Log files are called &lt;first four letters from object&gt;comp.log, for example Bankcomp.log for the log file that results from a compile of the object called BankAccountReconcile.</p>
<p>These log files are temporary and the file names are not unique.</p>
<p>The log file in the above example is overwritten when you next compile an object called, for example, BankDepositSlip.</p></td>
</tr>
<tr class="odd">
<td><p>Development warnings</p></td>
<td><p>Specify whether to view development warnings in the message window during X++ code translation.</p>
<p>A warning is displayed if, for example, there are SQL statements that may result in inferior performance. The following SQL statements result in a warning if a key does not exist on the table myTable with the fields myField1 and myField2:</p>
<p>select * from myTable where myTable.myField1==x &amp;&amp; myTable.myField2==y;</p></td>
</tr>
<tr class="even">
<td><p>Startup model</p></td>
<td><p>Specify the model to load at startup.</p></td>
</tr>
<tr class="odd">
<td><p>Execute business operations in CIL</p></td>
<td><p>Specify whether to execute business operations in the code interop layer.</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Application object tree</p></th>
<th><p> Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Application object layer</p></td>
<td><p>Specify the layer view on elements in the tree.</p>
<ul>
<li><p><strong>Show no layers</strong> – no objects are labeled with layer indications.</p></li>
<li><p><strong>Show all layers</strong> – all objects are labeled with layer indications for all layers in which they exist.</p></li>
<li><p><strong>Show highest layer</strong> – all objects are labeled with a layer indication for the highest layer.</p></li>
<li><p><strong>Show corrected layers</strong> – only objects that have been modified in the current layer or a higher one are labeled and only with an indication for the highest layer.</p></li>
<li><p><strong>Show all from corrected layers</strong> – only objects that have been modified in the current layer or a higher one are labeled but with indications for all layers.</p></li>
</ul>
<p>To learn about application object layers, see <a href="layers.md">Layers</a>.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>Application object model</p></td>
<td><p>Specify the model view on elements in the tree.</p>
<ul>
<li><p><strong>Show no models</strong> – no model information is appended to element names.</p></li>
<li><p><strong>Show on all elements</strong> – model information is displayed on all elements.</p></li>
<li><p><strong>Show on elements in current layer only</strong> – model information is displayed only on elements that exist in the current layer.</p></li>
<li><p><strong>Show on elements in current model only</strong> – model information is displayed only on elements that exist in the current model.</p></li>
</ul>
<p>To learn about application object layers, see <a href="layers.md">Layers</a>.</p>
<p></p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Debug</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Debug mode</p></td>
<td><p>Use the Debug mode list to define when the debugger is activated.</p>
<ul>
<li><p>No: debugger is never activated.</p></li>
<li><p>When Breakpoint: debugger is activated when a breakpoint in the X++ code is encountered.</p></li>
</ul></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Auto</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Auto-update</p></td>
<td><p>Type the number of seconds of keyboard inactivity before the system should initiate a new update cycle.</p>
<p>A value of 0 (zero) disables the systems update cycle.</p></td>
</tr>
<tr class="even">
<td><p>Auto-refresh</p></td>
<td><p>Select this if you want the system to update elements automatically so that elements that are made by other users become available to all users. In addition, the system updates lock indications in the Application Object Tree (AOT).</p>
<p>You can also refresh manually by using the Refresh command in the shortcut menu, for example on the Forms or the Queries nodes.</p>

> [!note]  
> <P>Refresh is one of the three components in an update cycle, and is performed only when an update cycle interval is specified (the Auto-Update option).</P>

</td>
</tr>
<tr class="odd">
<td><p>Auto-save</p></td>
<td><p>Select this if you want the system to save elements automatically. When the Auto-Save option is enabled, the system automatically saves the unsaved objects when you exit.</p>

> [!note]  
> <P>Automatic save is one of the three components in an update cycle, and is performed only when an update cycle interval is specified (the Auto-Update option).</P>

</td>
</tr>
<tr class="even">
<td><p>Garbage collection limit</p></td>
<td><p>Specify the number of open elements before garbage collection is made.</p>
<p>The system uses memory each time an element is opened in the AOT. Unless a value is specified here, elements are never discarded from memory.</p>
<ul>
<li><p>An element is considered open when:</p>
<ul>
<li><p>The element node is expanded in the AOT, or</p></li>
<li><p>A method is open in the X++ editor, or</p></li>
<li><p>The properties are displayed, or</p></li>
<li><p>The element is displayed in the visual form editor or in the visual report editor, or</p></li>
<li><p>The element has been changed but not yet saved.</p></li>
</ul></li>
</ul>

> [!note]  
> <P>Garbage collection is one of the three components in an update cycle, and is performed only when an update cycle interval is specified (the Auto-Update option).</P>

</td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Trace</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Database trace</p></td>
<td><p>Select this if you want the system to trace to the message window whenever the database is accessed.</p></td>
</tr>
<tr class="even">
<td><p>Client/Server trace</p></td>
<td><p>Select this if you want to include information about where classes are executed.</p></td>
</tr>
<tr class="odd">
<td><p>ActiveX trace</p></td>
<td><p>Select this to enable tracing of ActiveX control events.</p>
<p>This means that all events that are fired by the ActiveX controls are logged in the message window. Different ActiveX controls fire different events, but most ActiveX controls share a common set of events, such as MouseMove, MouseDown, MouseUp, KeyDown, KeyUp, and so on.</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property sheet</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Sort alphabetically</p></td>
<td><p>Select this option to have properties sorted alphabetically when they are displayed in the property editor.</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

