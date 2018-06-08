---
title: Cues Web Part
TOCTitle: Cues
ms:assetid: 162a328c-35fa-4367-9a0b-7786336278dd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc583731(v=AX.60)
ms:contentKeyID: 35244983
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Cues Web Part 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Cues web part displays a cue group. The cue group contains cues that display a pictorial representation of an important number for a business, such as the number of open sales orders. The following illustration shows a cue group displayed in the Cues web part.

![Cues](images/Cc583731.EP_Cues(AX.60).gif "Cues")

**Cues**

## Page Types Used On

Role center pages

## Microsoft Dynamics AX Properties

The following properties specific to Microsoft Dynamics AX are available for this Web part.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cue Group Name</p></td>
<td><p>The name of the cue group (an item in the <strong>Parts</strong> &gt; <strong>Cue Groups</strong> node of the AOT) that will be displayed in the Cues web part.</p></td>
</tr>
</tbody>
</table>


## Connections

None

## Comments

If you want to be able to drill down to the underlying data that the cue is based on, specify the **WebMenuItemName** property for the menu item that is used for the cue. The standard practice is to define a web menu item that directs the user to a list page in Enterprise Portal that can display the set of items being counted by the cue.

## See also

[Cues and Cue Groups](cues-and-cue-groups.md)

