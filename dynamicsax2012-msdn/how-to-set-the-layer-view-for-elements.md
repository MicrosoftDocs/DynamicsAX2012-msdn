---
title: 'How to: Set the Layer View for Elements'
TOCTitle: 'How to: Set the Layer View for Elements'
ms:assetid: 3582618d-caa8-469e-8907-f58127452345
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa635881(v=AX.60)
ms:contentKeyID: 35242011
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Set the Layer View for Elements [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Application Object Tree (AOT) in Microsoft Dynamics AX can display information about which layers elements are in or have been modified in. The layer information is shown in parentheses immediately following the element name in the AOT; for example, **CustTable (sys)**. This topic describes how to specify the layer information that appears with elements in the AOT.


> [!NOTE]
> <P>The status bar displays the layer that you are currently working in.</P>



### To change the layer view for elements

1.  Click **Tools** \> **Options**. The **Options** dialog box opens.

2.  In the **Development** area, expand **Application object tree**, and then set the **Application object layer** field to one of the following options.
    
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
    <td><p><strong>Show no layers</strong></p></td>
    <td><p>No layer information is appended to element names.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Show all layers</strong></p></td>
    <td><p>Elements are labeled with information about all layers in which they exist.</p>
    <p>For example, if an element from the SYS layer was modified in the FPK and VAR layers, the element would be labeled: (sys, fpk, var).</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Show highest layer</strong></p></td>
    <td><p>Elements are labeled with information about the highest layer in which they exist.</p>
    <p>For example, if an element from the SYS layer was modified in the FPK and VAR layers, the element would be labeled: (var).</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Show corrected layers</strong></p></td>
    <td><p>Only elements that have been modified in the current layer or a higher layer are labeled. Only the highest layer is shown.</p>
    <p>For example, if an element from the SYS layer was modified in the FPK and VAR layers, the element would be labeled: (var).</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Show all from corrected layers</strong></p></td>
    <td><p>Only elements that have been modified in the current layer or a higher layer are labeled. All layers in which the element has been modified are shown.</p>
    <p>For example, if a SYS element was modified in the FPK and VAR layers, the element would be labeled: (sys, fpk, var) if you are in the SYS layer.</p></td>
    </tr>
    </tbody>
    </table>


3.  Click **Apply** to change the layer view.

For information about how to set the model view, see [How to: View Model Information](how-to-view-model-information.md).

## See also

[Layers](layers.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

