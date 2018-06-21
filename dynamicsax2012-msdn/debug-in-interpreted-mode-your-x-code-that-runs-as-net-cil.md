---
title: Debug in Interpreted Mode Your X++ Code that Runs as .NET CIL
TOCTitle: Debug in Interpreted Mode Your X++ Code that Runs as .NET CIL
ms:assetid: c65a068a-35b3-468a-8757-931a398db0b5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh528509(v=AX.60)
ms:contentKeyID: 37835256
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Debug in Interpreted Mode Your X++ Code that Runs as .NET CIL [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In some cases you can debug your X++ code in interpreted mode even where the code is typically compiled to run as .NET Framework CIL. To activate this option, you clear a check box in the **Options** window of the Microsoft Dynamics AX development workspace.

During development when you are frequently making code changes and retesting, it is sometimes more convenient to debug X++ in interpreted mode. This option is convenient in the following ways:

  - You can avoid regenerating the CIL after each X++ code change.

  - You can debug by using the Microsoft Dynamics AX debugger, instead of attaching the Microsoft Visual Studio debugger to the Application Object Server (AOS). This is important when multiple developers are sharing one AOS.

## Configuration Check Box

The option to debug X++ in interpreted mode is found here in the development workspace:

**Tools** \> **Options** \> **Development** \> **General** \> **Execute business operations in CIL**

Initially the check box is selected. You clear the check box to debug in interpreted mode.

## Applicable Scenarios

In some cases you can debug your X++ code in interpreted mode even where the code is typically compiled to run as .NET Framework CIL. But in other cases you cannot, and you can only debug in CIL mode. The following table lists some cases in each category.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Option available?</p></th>
<th><p>Cases</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Yes, the <strong>Execute business operations in CIL</strong> setting has an effect. You can debug X++ code in interpreted mode.</p></td>
<td><ul>
<li><p>Your code runs under the Business Operations Framework (BOF).</p></li>
<li><p>Your code is invoked by a utility method that runs your code as CIL, such as:</p>
<ul>
<li><p>SysDictClass::invokeStaticMethodIL</p></li>
<li><p>SysDictTable::invokeStaticMethodIL</p></li>
<li><p>Global::runClassMethodIL</p></li>
<li><p>Global::runTableMethodIL</p></li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td><p>No, the <strong>Execute business operations in CIL</strong> setting is ignored. You must debug in CIL mode.</p></td>
<td><ul>
<li><p>Your code is run on the AOS by a batch job.</p></li>
<li><p>Your code is run by the runAs function of the X++ language.</p></li>
<li><p>Your code is run on the client.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## See also

[Microsoft Dynamics AX IDE](microsoft-dynamics-ax-ide.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

