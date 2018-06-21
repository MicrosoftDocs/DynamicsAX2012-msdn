---
title: 'How to: Compare Two Application Objects'
TOCTitle: 'How to: Compare Two Application Objects'
ms:assetid: 4a0370d8-ad20-4cf1-95b7-96b6f820184f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb190057(v=AX.60)
ms:contentKeyID: 35243191
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Compare Two Application Objects [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you can compare two application objects in the same or different layers by using the **Compare** tool. For example, you can compare a table in the CUS layer with the same table in the SYS layer. The **Compare** tool identifies the differences between the two application objects and provides action buttons to copy, move, or delete the differences. This topic describes how to compare two application objects in the Application Object Tree (AOT).

## Procedures

### To compare two application objects

1.  In the AOT, select the application objects that you want to compare.

2.  Right-click the selected application objects, and then click **Compare**. The **Comparison** formopens.

3.  Click the **Advanced** tab, and then set the following options as needed.
    
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
    <td><p><strong>Show differences only</strong></p></td>
    <td><p>Select this option to view only the differences. When this option is cleared, matching results are displayed as black check marks.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Suppress whitespace</strong></p></td>
    <td><p>Select this option to show differences in spaces in X++ code.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Case sensitive</strong></p></td>
    <td><p>Select this option to view upper and lowercase differences. By using this option, MyName and Myname would be displayed as a difference.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Show line numbers</strong></p></td>
    <td><p>Select this option to enable line numbers in X++ code.</p></td>
    </tr>
    </tbody>
    </table>


4.  Click **Compare** to begin the comparison of the two application objects.

The differences are displayed in the results window on the **Comparison** form. For more information about the results, see [Compare Tool](compare-tool.md).

## See also

[How to: Compare Versions of an Object](how-to-compare-versions-of-an-object.md)

[How to: Compare Layers](how-to-compare-layers.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

