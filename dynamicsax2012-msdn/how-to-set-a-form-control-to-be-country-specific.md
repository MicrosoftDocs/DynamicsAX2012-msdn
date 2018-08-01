---
title: 'How to: Set a Form Control to be Country Specific'
TOCTitle: 'How to: Set a Form Control to be Country Specific'
ms:assetid: 9deb44dc-d763-4b30-93dc-083b66e3d9c9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh404128(v=AX.60)
ms:contentKeyID: 36956796
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Set a Form Control to be Country Specific [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You use the CountryRegionCodes property of the control to list the ISO codes of the countries where you want the control to appear. If the value of the property matches the value of the controlling party, the control will be displayed. Typically, you use legal entity, vendor, customer or bank as the controlling party. The list of ISO country and region codes can be found [here](http://www.iso.org/iso/country_codes/iso_3166_code_lists/country_names_and_code_elements.htm). For more information on controlling entities, ISO codes, and controlled entities, see [Applying Country Specific Functionality](applying-country-specific-functionality.md).

### To set the CountryRegionCodes property

1.  In the AOT, expand the **Forms** node.

2.  Find and expand the form that contains the control you wish to make country-specific. Expand **Designs**, expand **Design**, and then add or find the control.

3.  Right-click the control, and then click **Properties**. Use the **Properties** window to set the **CountryRegionCodes** property. You can add as many ISO codes as required via a comma-separated list.
    
    If the ISO code value of the **CountryRegionCodes** property does not match the ISO code value of the controlling party, the control is not displayed. If the values match, the control is displayed.

4.  Right-click the form and click **Save**.

### Example: Using a country specific menu item

1.  In the AOT, expand the **Menu Items** node and expand the **Display** node.

2.  Find and right-click the **BlackListTable\_IT** menu item to open the **Properties** window.

3.  Find the **CountryRegionCodes** property and notice that its ISO code value is set to **IT**.

4.  Open the application workspace and click **General Ledger** \> **Reports** \> **External**. If the country context of the controlling party contains the **IT** ISO code, the **Italian black list report** menu item displays on the client. If the country context of the legal entity is not set to the **IT** ISO code, the menu item will not display. The following illustration shows the menu item that appears when the country context of the legal entity matches the country context of the menu item for the **Italian blacklist report**.
    
    ![Italian black list report menu item display](images/Hh404128.Country-specificHowto(en-us,AX.60).png "Italian black list report menu item display")

## See also

[Applying Country Specific Functionality](applying-country-specific-functionality.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

