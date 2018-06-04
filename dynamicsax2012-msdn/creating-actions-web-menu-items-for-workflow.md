---
title: Creating Actions Web Menu Items for Workflow
TOCTitle: Creating Actions Web Menu Items for Workflow
ms:assetid: 88a00d4e-aa43-4cbf-a37c-7af10b800a7e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Ee677502(v=AX.60)
ms:contentKeyID: 35245479
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Creating Actions Web Menu Items for Workflow 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You must create an Actions web menu item for each action that can be performed in the workflow you are implementing in Enterprise Portal. These web menu items correspond to the Action menu items that you created when you implemented the workflow for the Microsoft Dynamics AX client. When setting the properties for each of these Actions web menu items, make sure that you set the properties listed in the following table:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Setting</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Label</p></td>
<td><p>The text to display for the workflow action in Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>RunOn</p></td>
<td><p>Called from</p></td>
</tr>
<tr class="odd">
<td><p>Object</p></td>
<td><p>For the <strong>submit</strong> web menu item, it should be your class that handles the workflow submit action. For the other web menu items, it must be set to EPWorkflowWorkItemActionManager.</p>

> [!IMPORTANT]
> <P>This is a different object than the one used for the Microsoft Dynamics AX client.</P>


</td>
</tr>
</tbody>
</table>

