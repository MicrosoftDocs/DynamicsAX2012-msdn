---
title: Patch Layers
TOCTitle: Patch Layers
ms:assetid: f997e40c-c614-426d-8a93-06e72fbbce53
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa891248(v=AX.60)
ms:contentKeyID: 35254189
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Patch Layers [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Each layer in Microsoft Dynamics AX has a corresponding patch layer that can be used to incorporate updates to your application or to store conflicts when you import [models](models.md) into a layer. The following table shows the layers along with the corresponding patch layers:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Layer</p></th>
<th><p>Patch Layer</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>USR</p></td>
<td><p>USP</p></td>
</tr>
<tr class="even">
<td><p>CUS</p></td>
<td><p>CUP</p></td>
</tr>
<tr class="odd">
<td><p>VAR</p></td>
<td><p>VAP</p></td>
</tr>
<tr class="even">
<td><p>ISV</p></td>
<td><p>ISP</p></td>
</tr>
<tr class="odd">
<td><p>SLN</p></td>
<td><p>SLP</p></td>
</tr>
<tr class="even">
<td><p>FPK</p></td>
<td><p>FPP</p></td>
</tr>
<tr class="odd">
<td><p>GLS</p></td>
<td><p>GLP</p></td>
</tr>
<tr class="even">
<td><p>SYS</p></td>
<td><p>SYP</p></td>
</tr>
</tbody>
</table>


## Providing Updates

The patch layers are designed to make it easy to incorporate updates in your application. The basic idea is that when a minor update or correction is made, it is distributed in a patch file. Modified objects in the patch file are automatically used because they take precedence over the regular application objects.

## Storing Conflicts

By default, each layer contains a model that corresponds to the name of the layer. You can add additional models to layers that you have access to, depending on your license configuration. You can have different versions of the same element in models that are in different layers, but each element within any one layer must be unique.

If the same element exists in two models, and you try to import both models into the same layer, the element that exists in both models will cause a conflict. To mitigate the conflict, you can choose one of three options:

  - Abort the operation and leave the model store unchanged.

  - Overwrite existing definitions with the definitions in the new model.

  - Create a new model in the patch layer that contains the conflicts.

If you choose the third option, a conflict model is created in the patch layer that corresponds to the layer you are importing the model into. The conflicting elements are moved to this model. You can then decide how to resolve the conflicts. For more information about conflict models in a patch layer, see [How to: Resolve Conflicts After Importing a Model](how-to-resolve-conflicts-after-importing-a-model.md).

## See also

[Layers](layers.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

