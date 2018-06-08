---
title: 'How to: Add Data'
TOCTitle: 'How to: Add Data'
ms:assetid: bc16ccf4-7f25-434a-9966-16faf88b7315
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa861546(v=AX.60)
ms:contentKeyID: 35249975
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add Data 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can add data to Microsoft Dynamics AX. You can also modify data when you import and export the data.

Use the **Table browser** form to update data in individual tables. To access the form, in the AOT right-click a table, click **Add-Ins**, and then click **Table browser**.

## Add Data

This section describes how to use table definition groups to export and import data.

1.  Create a table definition group by doing the following:
    
    1.  Click **Administration** \> **Periodic** \> **Data export/import** \> **Definition groups**.
    
    2.  Press CTRL+N, or click the **New** menu button.  
        This displays the **Create table definition group** form.
    
    3.  In the **General** tab, type a unique name for the definition group in the **Definition group** text box.
    
    4.  Enter a short description into the **Description** text box.
    
    5.  Select your preferred check boxes on the **Options** tab.
    
    6.  On the **Include table groups** tab you can make other definition groups be a part of your new definition group.
    
    7.  Click the **OK** button to create your definition group.  
        The **Definition groups** form is displayed.

2.  On the **Definition groups** form, select the check box next to your definition group.

3.  Click the **Select tables** menu.

4.  Select a check box for every table that you want in your definition group.

5.  On the row for each table you select, you can also select check boxes for applying criteria or specifying related tables.

6.  Click the **Close** button. A **Tables** form is displayed in which you can see all the tables that are associated with your definition group.  
    You can use the **Tables** form to choose which fields you want involved in exports and imports.

7.  Back at the **Definition groups** form, you can click menus for export or import.

## Modify Data During Import and Export

1.  Create an X++ class that extends the [SysDataTableCtrl Class](https://msdn.microsoft.com/en-us/library/gg925945\(v=ax.60\)) class, as shown in the following example.
    
    public class SysDataTableCtrl\_Address   
     extends SysDataTableCtrl   
     {}

2.  Override the [SysDataTableCtrl.mustCtrlExport](https://msdn.microsoft.com/en-us/library/gg925946\(v=ax.60\)) and [SysDataTableCtrl.mustCtrlImport](https://msdn.microsoft.com/en-us/library/gg925947\(v=ax.60\)) methods to return true, as shown in the following example.
    
    public boolean mustCtrlExport()   
     { return true; }

3.  Override other methods as needed.

4.  Add the class you created in step 1 to the [SysDataTableCtrl::construct](https://msdn.microsoft.com/en-us/library/gg925940\(v=ax.60\)) method, as shown in the following example.
    
        client server static SysDataTableCtrl construct(DictTable dt)
        {
            switch (dt.id())
            {
                case tablenum(UserInfo):
                    return new SysDataTableCtrl_UserInfo(dt);
                case tablenum(SysUserInfo):
                    return new SysDataTableCtrl_SysUserInfo(dt);
                case tablenum(Address):
                    return new SysDataTableCtrl_Address(dt);
            }
            return new SysDataTableCtrl(dt);
        }

## See also

[Manipulation of Data in Tables](manipulation-of-data-in-tables.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

