---
title: User Personalization of Forms
TOCTitle: User Personalization of Forms
ms:assetid: 3226a226-12a4-434c-9619-0b1536595021
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa635528(v=AX.60)
ms:contentKeyID: 35241990
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# User Personalization of Forms [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Users are provided with several options to personalize Microsoft Dynamics AX forms. These options allow the user to move controls, set properties on controls, and add extra fields to forms. Forms are customized at run time, and settings are saved on a per-user basis.

To enable users to make certain types of changes to a form, modify the following:

  - AllowUserSetup property on the form control (or the form design)

  - AllowAdd property on the form data source field

The following table shows the levels of personalization.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Level of user personalization allowed</p></th>
<th><p>AllowUserSetup property</p></th>
<th><p>AllowAdd property</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="disabling-user-customization-of-forms.md">No customization</a></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p><a href="enabling-user-customization-of-controls.md">Customization of controls</a></p></td>
<td><p>Restricted</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p><a href="enabling-user-customization-of-layout.md">Customization of layout</a></p></td>
<td><p>Yes</p></td>
<td><p>Restricted</p></td>
</tr>
<tr class="even">
<td><p><a href="enabling-full-user-customization-of-forms.md">Full customization</a></p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
</tr>
</tbody>
</table>


For more information about a level, click the level name.

These personalization levels also depend on how X++ code has been used in the form. For more information, see [Enabling User Personalization of Forms](enabling-user-personalization-of-forms.md).

Check the level of user personalization for a form by using the FormControl.isUserSetupEnabled method. The method takes the required level of user personalization, and then returns whether that level of user personalization has been enabled.

User setup information is saved in the SysLastValue table.

## See also

[Form Control Properties](form-control-properties.md)

[Form Design Properties](form-design-properties.md)

[Form Data Source Field Properties](form-data-source-field-properties.md)

[FormControl.isUserSetupEnabled Method](https://msdn.microsoft.com/en-us/library/gg857558\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

