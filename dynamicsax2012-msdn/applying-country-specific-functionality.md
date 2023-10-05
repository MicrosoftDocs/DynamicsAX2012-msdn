---
title: Applying Country/Region Specific Functionality
TOCTitle: Applying Country/Region Specific Functionality
ms:assetid: 8e59cd77-c092-428f-8a4b-f85ab0bd42e3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh404126(v=AX.60)
ms:contentKeyID: 36956794
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Applying Country/Region Specific Functionality 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You use country and region specific functionality to help meet the legal, regulatory, and business needs of individual geographies. A geography is any country or region that is identified by an ISO country or region code. In Microsoft Dynamics AX, you use country region context for this process. The following table highlights the key elements you use to configure country and region functionality:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Element</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Controlling party</p></td>
<td><p>The controlling party is defined by the Organization model in Microsoft Dynamics AX. Examples include legal entity, customer, vendor, bank, or worker. The controlling party’s role is to determine whether country/region-specific functionality or UI elements will be enabled on the controlled entity. If the country/region context of the controlling party matches the country/region context of the controlled entity, the functionality or UI elements will be enabled.</p>
<p>The controlling party defaults to the legal entity.</p>
<p>You set the country and region context of the controlling party. Any controlled entities that have matching country and region context will be displayed.</p></td>
</tr>
<tr class="even">
<td><p>Controlled entity</p></td>
<td><p>The controlled entity is a UI element that is hidden or made visible depending on whether its country and region context matches the controlling entity.</p>
<p>To enable hiding menus, menu items and form controls that are based on country context, a controlled entity includes a <strong>CountryRegionCodes</strong> property on some elements. You use this property to specify the country or region where the element is visible. You find the <strong>CountryRegionCodes</strong> property on the following AOT elements:</p>
<ul>
<li><p>Extended Data Type</p></li>
<li><p>Menu and menu items</p></li>
<li><p>Enum and enum value</p></li>
<li><p>Table and table field</p></li>
<li><p>View and view field</p></li>
<li><p>Map and map field</p></li>
<li><p>Form control</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Using the CountryRegionCodes property

You create country context on a controlled entity by setting the ISO code value on the **CountryRegionCodes** property. The list of ISO country and region codes can be found [here](http://www.iso.org/iso/country_codes/iso_3166_code_lists/country_names_and_code_elements.htm). Microsoft Dynamics AX compares the values of that property to the country or region context of the controlling party. If the values match, the element is displayed. Otherwise, it is hidden.


> [!TIP]
> <P>To add more than one ISO country and region codes to the <STRONG>CountryRegionCodes</STRONG> property, you use a comma-separated list.</P>



## Using the legal entity as the controlling party

The **Country/region** value in the primary address of the legal entity determines the country and region context for the controlling party. The default value of the **Country/region** field is the locale of the Microsoft Dynamics AX client. The following illustration shows how to set the primary address of the legal entity:

![Legal entity form](images/Hh404126.GDL_(en-us,AX.60).png "Legal entity form")

## Setting another party as the controlling party

You can use another party, such as a customer, bank or vendor as a controlling party. For example, you can enable targeted functionality for customers of a specific country or region or require certain validation of vendors from a specific country or region. To set the controlling party, you use the **CountryRegionContextField** property of the form, control or other element. The property enables you to select the entity that is the controlling party. The default value is the legal entity. The following illustration shows how to set the **CountryRegionContextField** property for a field.

![Setting properties on a control](images/Hh404126.GDL_SettingPropertiesOnControl(en-us,AX.60).png "Setting properties on a control")

In this example, customer becomes the controlling entity. The customer address is compared with the value of the **CountryRegionCodes** field to determine whether the **USASpecificSetting** is displayed.

## See also

[How to: Set a Form Control to be Country/region Specific](how-to-set-a-form-control-to-be-country-specific.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

