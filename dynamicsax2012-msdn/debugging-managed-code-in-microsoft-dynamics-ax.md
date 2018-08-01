---
title: Debugging Managed Code in Microsoft Dynamics AX
TOCTitle: Debugging Managed Code
ms:assetid: 908234ea-b73c-43c7-b90a-5502b2d62374
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg889265(v=AX.60)
ms:contentKeyID: 35272159
ms.date: 11/21/2012
mtps_version: v=AX.60
---

# Debugging Managed Code in Microsoft Dynamics AX [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

After you create a project in Microsoft Visual Studio and add it to the model store, you can set the project debug properties and use Visual Studio to start debugging your code. Although you start debugging in Visual Studio, some debugging is still done in the Microsoft Dynamics AX Debugger. For more information, see [Walkthrough: Using the Debug Properties When Debugging Managed Code](walkthrough-using-the-debug-properties-when-debugging-managed-code.md).

## Debug Properties

The debug properties are properties on a managed code project. These properties work together to enable you to debug both X++ code and managed code from Visual Studio. The **Debug Target** property specifies which Microsoft Dynamics AX process Visual Studio should attach to when you are debugging. The **Startup Element** property specifies the X++ code that will be called by the debugger after it attaches to the Microsoft Dynamics AX process.

### Debug Target Property

The **Debug Target** property enables you to designate which Microsoft Dynamics AX process Visual Studio should attach to when you debug.

  - When this property is set to **Client**, the debugger attaches to the process Ax32.exe.

  - When this property is set to **Server**, the debugger attaches to the process Ax32Serv.exe.

  - When this property is set to **SSRS**, the debugger attaches to the process ReportingServicesService.exe.


> [!NOTE]
> <P>If you do not set the <STRONG>Debug Target</STRONG> property, you must manually attach Visual Studio to the correct process.</P>



### Startup Element Property

The **Startup Element** property enables you to specify a Microsoft Dynamics AX job, menu item, class, or form that will run after Visual Studio attaches to the appropriate process.

You can manually modify the **Startup Element** property by providing the path of the application element in the Application Object Tree (AOT), or you can right-click an element in Application Explorer and select **Set as startup element**.

The following table lists the elements that you can specify in the **Startup Element** property:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property Value</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Class</p></td>
<td><ul>
<li><p>When you set the property in Visual Studio, the format is as follows: <strong>\Classes\MyClass</strong>.</p></li>
<li><p>The debugger calls the main function on the specified class. The main function signature must be public static void and it must take the Args class as a parameter. The main function should resemble this:</p>
<pre><code>public static void main(Args _args)
{
}</code></pre></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Job</p></td>
<td><ul>
<li><p>When you set the property in Visual Studio, the format is as follows: <strong>\Jobs\MyJob</strong>.</p></li>
<li><p>The job signature must be public static void and take the Args class as a parameter.</p>
<pre><code>static void Job1(Args _args)
{
}</code></pre></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Menu Item</p></td>
<td><ul>
<li><p>When you set the property in Visual Studio, the format is as follows: <strong>\Menu Items\Display\MyMenuItem</strong>.</p></li>
<li><p>You can use display, action, or output menu items as a startup element.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Form</p></td>
<td><ul>
<li><p>When you set the property in Visual Studio, the format is as follows: <strong>\Forms\MyForm</strong>.</p></li>
<li><p>You cannot set the <strong>Startup Element</strong> to a form that takes parameters. When you set the <strong>Startup Element</strong> property to a form, the form opens the same way it opens when you right-click the form in the AOT and then click <strong>Open</strong>.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Debugging Considerations

When debugging Microsoft Dynamics AX managed code from Visual Studio, here are some things to consider.

  - When you manually attach Visual Studio to the Microsoft Dynamics AX process, you should select the fields **Show processes from all users** and **Show process in all sessions** to make sure that that both the client and server processes appear.

  - When you debug managed code that runs on the server, you must attach to the server process Ax32Serv.exe. To attach the Visual Studio Debugger to the Microsoft Dynamics AX server process, you must open Visual Studio with administrator credentials.

  - When you use Visual Studio to debug any code that runs in Common Intermediate Language (CIL), make sure that the **Enable Just My Code** field is cleared. To find this field in Visual Studio, click **Tools** \> **Options** \> **Debugging**.

## See also

[Walkthrough: Using the Debug Properties When Debugging Managed Code](walkthrough-using-the-debug-properties-when-debugging-managed-code.md)

[Debugging in Microsoft Dynamics AX 2012](debugging-in-microsoft-dynamics-ax-2012.md)

