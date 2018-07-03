---
title: Creating Checklists
TOCTitle: Creating Checklists
ms:assetid: a5c57d30-86d3-40a0-b34b-b7282c01ed5c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa851059(v=AX.60)
ms:contentKeyID: 35248393
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Creating Checklists 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Checklists can be used during setup and upgrade. The checklist concept provides a tool for adding items that must be part of a specific setup procedure.

## Creating a New Checklist

1.  Create a new class that inherits from the [SysCheckList](https://msdn.microsoft.com/en-us/library/gg943952\(v=ax.60\)) class. For an example of methods that can be overridden, see the [SysCheckList\_Setup](https://msdn.microsoft.com/en-us/library/gg915005\(v=ax.60\)) class.

2.  Create a new empty interface. The interface is used by items that belong to the checklist.

3.  Add the classId to the [SysCheckList::checkLists](https://msdn.microsoft.com/en-us/library/gg943723\(v=ax.60\)) static method.

4.  Create the necessary checklist items and add them to your checklist.

## Adding Items to a Checklist

1.  Create a new class that inherits from [SysCheckListItem](https://msdn.microsoft.com/en-us/library/gg924127\(v=ax.60\)) class.

2.  Override the following methods:
    
      - [SysCheckListItem.getHelpLink](https://msdn.microsoft.com/en-us/library/gg944095\(v=ax.60\))
    
      - [SysCheckListItem.getMenuItemName](https://msdn.microsoft.com/en-us/library/gg924093\(v=ax.60\))
    
      - [SysCheckListItem.getMenuItemType](https://msdn.microsoft.com/en-us/library/gg924099\(v=ax.60\))
    
      - [SysCheckListItem.new](https://msdn.microsoft.com/en-us/library/gg924157\(v=ax.60\))

3.  Set the security key for the menu items to limit access to certain users based on user permissions, by using the [Menu.securityKey](https://msdn.microsoft.com/en-us/library/gg912120\(v=ax.60\)) method.

4.  Add a dependency for a menu item by using the [SysCheckListItem.addDependency](https://msdn.microsoft.com/en-us/library/gg944070\(v=ax.60\)) method.

5.  Run the following code when the checklist tasks are completed.
    
       ```X++
        SysCheckList::finished(classnum(SysCheckListItem_MyNewItem))
       ```

6.  Add the ID for the class you created in step 1 to the [::checkListItems](https://msdn.microsoft.com/en-us/library/gg943719\(v=ax.60\)) static method.

7.  If a menu item requires restarting the system, call [SysCheckList.needReStart](https://msdn.microsoft.com/en-us/library/gg943997\(v=ax.60\)) in the [SysCheckListItem.setStatus](https://msdn.microsoft.com/en-us/library/gg924170\(v=ax.60\)) method as shown in the following example.
    
       ```X++
       if (status == SysCheckListStatus::finished &&   !this.find())
        {
            this.save();
            SysCheckList.needRestart(true);
        }
       ```

The following code shows a call to the [SysCheckListItem.placeAfter](https://msdn.microsoft.com/en-us/library/gg924163\(v=ax.60\)) method that sets the sequence in the list and a call to the [SysCheckListItem.indeterminate](https://msdn.microsoft.com/en-us/library/gg924131\(v=ax.60\)) method that indicates that a menu item can be skipped. When a user clicks the item, the status changes to finished.

The placeAfter method depends on the [SysCheckList.sortWithStatusPreference](https://msdn.microsoft.com/en-us/library/gg944034\(v=ax.60\)) method.

   ```X++
   super();
    this.indeterminate(true); // You can skip this item
    this.placeAfter(classnum(SysCheckListItem_Synchronize));
     
    // Can only run after sync
    this.addDependency(classnum(SysCheckListItem_Synchronize));   
     
    // Can only run after compile or licensecode
    this.addDependency( [classnum(SysCheckListItem_Compile),   classnum(SysCheckListItem_LicenseCode)} ); 
   ```

## See also

[Upgrading to a New Version of Microsoft Dynamics AX](upgrading-to-a-new-version-of-microsoft-dynamics-ax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

