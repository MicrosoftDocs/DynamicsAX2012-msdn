---
title: 'How to: Add Elements to the Version Control System'
TOCTitle: 'How to: Add Elements to the Version Control System'
ms:assetid: fce12cdf-e387-4940-b08e-b3734f014b5b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa892734(v=AX.60)
ms:contentKeyID: 35268293
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Add Elements to the Version Control System [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

If you are using version control in Microsoft Dynamics AX, you must add elements to the version control system after you create them.

## Adding Elements to the Version Control System

### To add Elements to the version control system

1.  In the AOT, right-click the element and then click **Add to Version Control**.

2.  Select the folder in the version control system that you want to add your element to.
    

    > [!NOTE]
    > <P>This step is not required if your administrator has not defined folders. The folders available in the version control system are defined on the <STRONG>Additional subfolders</STRONG> tab of the <STRONG>System settings</STRONG> form.</P>



3.  Right-click the element and then click **Check In**. This opens the [Check in form](how-to-check-elements-into-the-version-control-system.md).

After you check in the element, it can be checked out of the version control system.

The element is added to the current model. The current model and layer are displayed in the status bar in Microsoft Dynamics AX and may also be displayed together with the element in the AOT.

You cannot have two models under version control in the same layer if elements occur in both models. You must develop outside of version control when this is the scenario. For example, during upgrade you might have fields that occur in the original table and the upgrade table.

If you add an element in a lower layer to version control and then customize the element in a higher layer, you may encounter problems when you synchronize. If you develop in multiple layers, we recommend that you create separate VCS branches for each layer.

If you cannot check in a new element, it might have failed some of the quality checks set in the system settings for the version control system. These settings are typically chosen by an administrator, and are set in the System settings form. For more information, see [How to: Add Rules for Elements](how-to-add-rules-for-elements.md)

## See also

[How to: Check Elements into the Version Control System](how-to-check-elements-into-the-version-control-system.md)

[How to: Check Elements Out of the Version Control System](how-to-check-elements-out-of-the-version-control-system.md)

[How to: Use Label Files Under Version Control](how-to-use-label-files-under-version-control.md)

[How to: Delete Elements from the Version Control System](how-to-delete-elements-from-the-version-control-system.md)

[How to: Rename Elements in the Version Control System](how-to-rename-elements-in-the-version-control-system.md)

