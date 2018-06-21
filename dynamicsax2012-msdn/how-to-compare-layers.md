---
title: 'How to: Compare Layers'
TOCTitle: 'How to: Compare Layers'
ms:assetid: f859af7e-78a8-49d0-afa8-05ae8426a0e3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa890665(v=AX.60)
ms:contentKeyID: 35253667
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Compare Layers 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to use the **Compare layers** tool in Microsoft Dynamics AX. You can use the **Compare layers** tool to compare any two application object layers, for example, the SYP layer and the SYS layer.

The **Compare layers** tool compares a source layer to a reference layer. The compare process searches for application objects that have changed or exist only in the reference layer.

If VAR is the source layer that you want to compare to the standard application that has service packs installed, select SYP as the reference layer. The compare layers process will then compare the VAR layer with the SYP and SYS layers. The result of the comparison is a project that holds objects that do not occur in the reference layer, or occur in both layers, but are different provided that the option to **Only include elements present in both layers** is not selected.

When the reference layer is not an **old** layer, such as **old sys**, the reference layer automatically includes all lower layers. For example, if the USR layer is the source layer and it is compared to the CUS layers as a reference layer, then the reference layer includes the CUS layer and all layers underneath it.

## Procedures

### To compare application object layers

1.  Click **Tools** \> **Code Upgrade** \> **Compare layers**. The **Compare layers** tool opens.

2.  In the **Compare layers** tool, set the following properties as required.
    
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
    <td><p><strong>Project name</strong></p></td>
    <td><p>The name of the project to contain the results of the compare layers tool process.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Source layer</strong></p></td>
    <td><p>The layer used as the base layer for the comparison.</p>
    <p>The compare tool results only display differences for application objects that are contained in the source layer.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Reference layer</strong></p></td>
    <td><p>The layer that you want to compare to the source layer.</p>
    > [!note]  
    > <P>You can select <strong>old sys</strong> as the reference layer. This is useful if you want to learn what application objects have changed.</P>
    </td>
    </tr>
    <tr class="even">
    <td><p><strong>Only include elements present in both layers</strong></p></td>
    <td><p>Select to detect conflicts between layers. When selected, elements found in only one of the layers are ignored.</p></td>
    </tr>
    </tbody>
    </table>


3.  Click **OK** to begin the application object layer compare.

4.  A project holding application objects that differ is now created. The objects are presented in a tree structure and the regular Application Object Tree (AOT) shortcut menu commands are available.


> [!NOTE]
> <P>In a compare situation, it is useful to see the layer to which each object belongs. For more information, see the <A href="http://go.microsoft.com/fwlink/?linkid=134514">How to: Set the Layer View for Application Objects</A> topic in your Microsoft Dynamics AX for Developers documentation.</P>


  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

