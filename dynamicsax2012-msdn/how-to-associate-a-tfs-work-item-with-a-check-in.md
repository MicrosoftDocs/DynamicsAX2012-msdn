---
title: 'How to: Associate a TFS Work Item with a Check-in'
TOCTitle: 'How to: Associate a TFS Work Item with a Check-in'
ms:assetid: 775bf598-f3f9-41bf-a57e-3f8308a1f289
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh337199(v=AX.60)
ms:contentKeyID: 36806623
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Associate a TFS Work Item with a Check-in 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

If you use Team Foundation Server (TFS) for version control, you can associate TFS work items with the code that you check in.

## Using Work Items

A work item is a generic object that has types. For example, a work item could be a requirement, task, bug, scenario, or test case. You can use work item types that are available with Microsoft Team System or you can create new work item types. For more information about work items, see [Working with Team Foundation Work Items](http://go.microsoft.com/fwlink/?linkid=223295).

### To associate a work item with a check-in

1.  Check in your code. Right-click each element you want to check in and then click **Check In**.

2.  Click **Version Control** \> **Pending Objects**.

3.  Select the elements you want to check in, and then click **Check in**.

4.  In **Description**, provide a meaningful summary of the code you are checking in.

5.  Click the **Work items** tab.

6.  The grid lists work items that are assigned to you. Select the work items that you want to associate with the check-in.

7.  If the work item you want to associate with the check-in is not in the list, add it. In the **ID** field, type the ID of the work item, and then click **Add work item**.

8.  Select a check-in action. For example, if you select **Resolve** for a bug work item type, the associated bug will be resolved.

9.  Click **OK**.

## See also

[Version Control System](version-control-system.md)

[Working with Team Foundation Work Items](http://go.microsoft.com/fwlink/?linkid=223295)

