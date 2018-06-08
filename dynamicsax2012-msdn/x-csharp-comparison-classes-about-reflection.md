---
title: 'X++, C# Comparison: Classes about Reflection'
TOCTitle: 'X++, C# Comparison: Classes about Reflection'
ms:assetid: 0a4f2567-9a8a-46de-a2c3-f76feeddba74
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967359(v=AX.60)
ms:contentKeyID: 35240349
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++, C\# Comparison: Classes about Reflection 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In X++ the TreeNode class provides access to the Application Object Tree (AOT). The TreeNode class is the center of reflection functionality in X++. The TreeNode class and its methods can be compared to the System.Reflection namespace in the .NET Framework that C\# uses.

## Table of Class Comparisons

The following table lists several classes that are available to you when you write C\# code. These are .NET Framework classes. For this table, all C\# classes are in the System.Reflection namespace unless otherwise specified.

Each row shows the corresponding Microsoft Dynamics AX class, or class member, that is available to you when your write X++ code.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++</p></th>
<th><p>C#</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TreeNode</p></td>
<td><p>System .Assembly</p></td>
<td><p>Assembly is the first class to use when a C# program must gather reflection information. Static methods on the X++ class TreeNode are the starting point for reflection in X++.</p></td>
</tr>
<tr class="even">
<td><p>TreeNode</p></td>
<td><p>System .Type</p></td>
<td><p>Instance methods on TreeNode correspond to instance methods on System.Type.</p></td>
</tr>
<tr class="odd">
<td><p>TreeNode .AOTgetSource</p></td>
<td><p>MethodInfo</p></td>
<td><p>The AOTgetSource method returns several pieces of information together in one string. This includes the X++ source code in the method.</p>
<p>In contrast, MethodInfo has a separate member for each piece of information.</p></td>
</tr>
<tr class="even">
<td><p>TreeNode .AOTfirstChild</p>
<p></p>
<p>TreeNode .AOTnextSibling</p>
<p></p>
<p>TreeNode .AOTiterator</p>
<p></p>
<p>AOTiterator</p></td>
<td><p>MethodInfo[] (an array)</p></td>
<td><p>In C#, the GetMethods method on System.Type returns an array of MethodInfo objects. You can loop through the array by the common technique of incrementing an indexer.</p>
<p>In contrast, the X++ model is to navigate the tree control of the AOT. The TreeNode methods of AOTfirstChild and AOTnextSibling accomplish the navigation.</p>
<p>As an equivalent alternative, the X++ AOTiterator class is designed to navigate the tree control of the AOT. A class node is the parent over several method nodes. The AOTiterator steps through child nodes, returning each as another TreeNode instance.</p>
<p>See also the TreeNode methods that are named AOTparent and AOTprevious.</p></td>
</tr>
<tr class="odd">
<td><p>TreeNode .AOTgetProperty</p>
<p></p>
<p>TreeNode .AOTgetProperties</p>
<p></p>
<p>TreeNode .AOTname</p></td>
<td><p>PropertyInfo</p></td>
<td><p>In X++, the AOTgetProperties method returns a long string that contains name-value pairs for all the properties of the TreeNode. The AOTname method returns a string that contains only the value for the name property.</p></td>
</tr>
<tr class="even">
<td><p>TreeNode .AOTsave</p>
<p></p>
<p>TreeNode .AOTinsert</p></td>
<td><p>System .Reflection .Emit (namespace of classes)</p></td>
<td><p>The AOTsave method applies changes from a TreeNode object in your X++ code to the AOT, and the changes are persisted.</p>
<p>For a large code sample, see <a href="https://msdn.microsoft.com/en-us/library/gg947384(v=ax.60)">TreeNode.AOTsave Method</a>.</p></td>
</tr>
</tbody>
</table>


## See also

[X++, C\# Comparison: Classes](x-csharp-comparison-classes.md)

[TreeNode Class](https://msdn.microsoft.com/en-us/library/gg958198\(v=ax.60\))

[TreeNode.AOTsave Method](https://msdn.microsoft.com/en-us/library/gg947384\(v=ax.60\))

[Performing Reflection with the TreeNode Class](performing-reflection-with-the-treenode-class.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

