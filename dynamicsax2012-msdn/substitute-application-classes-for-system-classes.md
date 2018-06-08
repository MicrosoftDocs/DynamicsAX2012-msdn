---
title: Substitute Application Classes for System Classes
TOCTitle: Substitute Application Classes for System Classes
ms:assetid: ac0c0348-843d-4030-bc42-11910a3933fe
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa853915(v=AX.60)
ms:contentKeyID: 35249698
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Substitute Application Classes for System Classes 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You should call the substitute application classes instead of calling the system classes that they extend.

In the Application Object Tree (AOT) under **System Documentation** \> **Classes** there are several kernel or system classes whose names begin with a lowercase **x**. Examples of the **x** system classes include **xApplication** and **xVersionControl**. Some of the **x** system classes are extended by X++ application classes which are under **AOT** \> **Classes**. For example, the **Application** X++ class extends the **xApplication** system class.

The X++ classes that derive from the **x** system classes are called substitute application classes. In the AOT under the **Classes** node, the icon next to the substitute application classes differs from the standard icon.

## Special X++ Global Variables

Some of the substitute application classes that extend an **x** system class are associated with a special X++ global variable that represents an instance of the X++ class. For example, the appl variable references a pre-instantiated object from the **Application** X++ class. The advantage of the appl variable is that the system maintains the object throughout the scope of your session. It would be less efficient for your X++ code to repeatedly use the new Application() syntax to obtain an instance of the Application X++ class.

You should not use the xApplication system class. Use the Application substitute application class instead. You can reference the static members of the Application X++ class by using the standard syntax Application::checkForNewBatchJobs(). But you should reference the instance members of the Application class by using its corresponding special system variable appl, if one exists. This pattern applies to most of the **x** system classes. The Session substitute application class is one exception to this pattern, because there is no special system variable for Session.

The following table lists **x** system classes for which there is a corresponding substitute application class. The special X++ global variables are also shown for those classes that have one.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Application class</p></th>
<th><p>System class</p></th>
<th><p>Global variable</p></th>
<th><p>Runs on</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg802600(v=ax.60)">Args</a></p></td>
<td><p>xArgs</p></td>
<td><p>(none)</p></td>
<td><p>Client and server</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg801797(v=ax.60)">Application</a></p></td>
<td><p>xApplication</p></td>
<td><p>appl</p></td>
<td><p>Server</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg835446(v=ax.60)">ClassFactory</a></p></td>
<td><p>xClassFactory</p></td>
<td><p>classFactory</p></td>
<td><p>Client and server</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg835524(v=ax.60)">Company</a></p></td>
<td><p>xCompany</p></td>
<td><p>appl.company</p></td>
<td><p>Server</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg836018(v=ax.60)">Global</a></p></td>
<td><p>xGlobal</p></td>
<td><p>(none)</p></td>
<td><p>Client and server</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg836364(v=ax.60)">Info</a></p></td>
<td><p>xInfo</p></td>
<td><p>Infolog</p></td>
<td><p>Client</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg912148(v=ax.60)">MenuFunction</a></p></td>
<td><p>xMenuFunction</p></td>
<td><p>(none)</p></td>
<td><p>Client and server</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg821192(v=ax.60)">Session</a></p></td>
<td><p>xSession</p></td>
<td><p>(none)</p></td>
<td><p>Client and server</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg821219(v=ax.60)">VersionControl</a></p></td>
<td><p>xVersionControl</p></td>
<td><p>versionControl</p></td>
<td><p>Client</p></td>
</tr>
</tbody>
</table>


## Example X++ Job that Uses Special Variables

The following X++ job demonstrates the syntax for using several special X++ variables that reference instances of the substitute application classes.

    static void UseSpecialSystemVariablesForXJob(Args _a)
    {
        TreeNode treeNode2;
        Args     args3;
        FormRun  formRun4;
        
        // appl variable
        print appl.buildNo();
     
        // company variable
        appl.company().reloadRights(); // referenced through appl
     
        // Infolog variable
        treeNode2 = infolog.findNode("\\forms\\custTable");
        print treeNode2.AOTgetProperty("Name");
     
        pause; // do want to continue
        
        // classFactory variable
        args3 = new Args(formstr(vendTable));
        formRun4 = classFactory.formRunClass(args3);
        formRun4.init();
        formRun4.run();
        formRun4.detach();
     
        Global::info("Job is ending. This is a message in the Infolog.");
        pause;
    }

## See also

[Microsoft Dynamics AX Class Overview](microsoft-dynamics-ax-class-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

