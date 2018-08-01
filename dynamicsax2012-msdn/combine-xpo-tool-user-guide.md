---
title: Combine XPO Tool User Guide
TOCTitle: Combine XPO Tool User Guide
ms:assetid: 4272f980-ad41-4187-be21-b2fcf93325e0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ225589(v=AX.60)
ms:contentKeyID: 48457366
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Combine XPO Tool User Guide [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Microsoft Dynamics AX 2012 Combine XPO Tool is a command line program that combines a set of interdependent XPO files into a single XPO. For example, if a team of developers is making code changes to different aspects of an application, they can use this tool to merge those changed files into one XPO file.

As of AX 2012 R2, the Combine XPO Tool is available in the Microsoft Dynamics AX\\60\\Management Utilities folder. (The beta version of the tool was previously available on InformationSource).

## How to use the Combine XPO tool to create a single XPO file

The Combine XPO tool generates an XPO file that is a combination of the XPO files in a given folder and any subfolders. It takes the path to the folder and the name of the resulting XPO file as input. For example, if you have XPO files in the C:\\MyApplication\\ModelA folder, you would use the following commands to create the combined XPO file:

**CombineXPOs.exe -XpoDir c:\\MyApplication\\ModelA -CombinedXpoFile c:\\MyApplication\\AXModelAFiles.xpo**

The parameter **–XpoDir** is the location of the folder that contains the xpos you want combined and imported. The **–CombinedXpoFile** parameter is the resulting directory path and filename of the newly created combination XPO file. Once the combined XPO file is successfully created, you import it into Microsoft Dynamics AX in the same manner as individual XPOs. For more information on importing XPOs, see [How to: Import Application Objects by Using the AOT](how-to-import-application-objects-by-using-the-aot.md).

## Combine XPO parameters

The following table lists the available command line parameters for CombineXPOs.exe, how they are used and if they are required. For parameters without a value listed in the argument field, no value is necessary.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Parameter</p></th>
<th><p>Argument</p></th>
<th><p>Optional?</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>-XpoDir</strong></p></td>
<td><p>&lt;directory&gt;</p></td>
<td><p>No</p></td>
<td><p>The root directory of the XPO source code.</p></td>
</tr>
<tr class="even">
<td><p><strong>-CombinedXpoFile</strong></p></td>
<td><p>&lt;path and file name&gt;</p></td>
<td><p>No</p></td>
<td><p>The path and filename for the resulting combined XPO file.</p></td>
</tr>
<tr class="odd">
<td><p><strong>-SpecifiedXpoFile</strong></p></td>
<td><p>&lt;filename&gt;</p></td>
<td><p>Yes</p></td>
<td><p>A file containing a list of XPO files to include in the combined file. The files specified must reside under the –XpoDir path. Any XPO files not in this list will not be in the combined file. The list should be formatted to show the full path to each file with one value per line. For example:</p>
<p>C:\ProgramData\myfile1.xpo</p>
<p>C:\ProgramData\myfile2.xpo.</p>
<p>All XPO files in the folder identified by the –XpoDir parameter are included in the combined file if this parameter is not passed.</p></td>
</tr>
<tr class="even">
<td><p><strong>-NoDel</strong></p></td>
<td><p>&lt;filename&gt;</p></td>
<td><p>Yes</p></td>
<td><p>A file containing a list of XPO files that contain DEL_ fields and indexes to include in the combined file. Any XPO files not in this list will have their DEL_ fields and indexes removed prior to being imported into the combined XPO file. The list should be formatted to show the full path to each file with one value per line. For example:</p>
<p>C:\ProgramData\myfile1.xpo</p>
<p>C:\ProgramData\myfile2.xpo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>-Verbose</strong></p></td>
<td><p></p></td>
<td><p>Yes</p></td>
<td><p>Enables verbose mode, which displays the name of each XPO file as it is processed</p></td>
</tr>
<tr class="even">
<td><p><strong>-utf8</strong></p></td>
<td><p></p></td>
<td><p>Yes</p></td>
<td><p>Produce a UTF-8 output file.</p></td>
</tr>
<tr class="odd">
<td><p><strong>-Threads</strong></p></td>
<td><p>&lt;count&gt;</p></td>
<td><p>Yes</p></td>
<td><p>Use this to reduce the load on the CPU if the process is negatively affecting other applications. The default is to let the Microsoft .NET Common Language Runtime automatically determine this count.</p></td>
</tr>
<tr class="even">
<td><p><strong>-ExclusionsFile</strong></p></td>
<td><p>&lt;filename&gt;</p></td>
<td><p>Yes</p></td>
<td><p>The file specified includes a list of XPO files that should be excluded from the combined file. Any XPO files in this list will not be in the combined file. The list should include the full path to the file to be excluded with one file on each line. For example:</p>
<p>C:\ProgramData\myfile1.xpo</p>
<p>C:\ProgramData\myfile2.xpo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>-ViewsOnlyOnce</strong></p></td>
<td><p></p></td>
<td><p>Yes</p></td>
<td><p>Causes any view XPOs to be included only one time each in the combined output. Otherwise, multiple copies of the view XPOs will be included because this typically improves reference resolution for queries and views during import. Using this parameter may improve the performance of loading the combined XPO file, but may also lead to reference errors when loading the XPO.</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

