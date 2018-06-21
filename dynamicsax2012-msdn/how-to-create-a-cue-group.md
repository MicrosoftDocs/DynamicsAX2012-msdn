---
title: 'How to: Create a Cue Group'
TOCTitle: 'How to: Create a Cue Group'
ms:assetid: 4e7cf2ea-3ddd-4c81-b242-6aa156380a21
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg840467(v=AX.60)
ms:contentKeyID: 35243470
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Cue Group [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A cue group is a part that contains one or more cues. You use a cue group to list the names of the cues and the number of records retrieved by each cue. The cue group appears in the FactBox pane of a form. This topic describes how to create a cue group and how to add cues to that cue group. For information about how to create a cue, see [How to: Create a Cue](how-to-create-a-cue.md).

### To Create a Cue Group

1.  In the AOT, expand **Parts**, right-click **Cue Groups**, and then click **New Cue Group**.

2.  Click the new cue group. In the property sheet, click **Name** and specify a name the uniquely identifies the cue group.

3.  Click **Label** and select the label you want to appear in the title bar of the cue group part.

### To Add a Cue Reference to a Cue Group

1.  Right-click the cue group, and then click **New Cue Reference**. You must add a cue reference for each cue that you want to appear in the cue group.
    

    > [!NOTE]
    > <P>You can also add cues to a cue group by dragging each cue onto the cue group part in the AOT. If you drag cues to the cue group, the <STRONG>Name</STRONG> and <STRONG>Cue</STRONG> properties are automatically set.</P>



2.  To complete the cue reference for each cue you added to the cue group, click the cue reference and supply values for the following properties:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name that uniquely identifies the cue reference.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Cue</strong></p></td>
    <td><p>Select the cue that you want to add to the group.</p></td>
    </tr>
    </tbody>
    </table>


3.  Right-click the cue group and then click **Save**.

## See also

[Cues and Cue Groups](cues-and-cue-groups.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

