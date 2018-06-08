---
title: Wizard Classes
TOCTitle: Wizard Classes
ms:assetid: 149ff4e6-2cce-4636-8468-d76d0b5919af
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa598359(v=AX.60)
ms:contentKeyID: 35240605
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Wizard Classes 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you create a new wizard using the [How to: Create Wizards](how-to-create-wizards.md), the wizard class will have the same name as your wizard.

Depending on the type of wizard, your wizard class extends either the SysWizard class, or the SysDefaultDataWizard class.

## Useful methods on the SysWizard class

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Method</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>validate</p></td>
<td><p>Used to validate user input, and called before the wizard is closed.</p>
<p>It returns false if user input is invalid. This will prevent the run method from being called when the user clicks the <strong>Finish</strong> button.</p></td>
</tr>
<tr class="even">
<td><p>formRun</p></td>
<td><p>Returns a formRun, which is an instance of the form of the same name as the class.</p>
<p>This method is always overridden but should not be changed.</p></td>
</tr>
<tr class="odd">
<td><p>static void main(args args)</p></td>
<td><p>Creates a new instance of the wizard and calls wizard.run on the SysWizard class.</p>
<p>This method is always overridden, but should not be changed.</p></td>
</tr>
<tr class="even">
<td><p>run</p></td>
<td><p>Called when the user clicks the <strong>Finish</strong> button if validate returned true.</p></td>
</tr>
<tr class="odd">
<td><p>setupNavigation</p></td>
<td><p>Use this method to set up whether the <strong>Next</strong> and <strong>Back</strong> buttons should be enabled from the start.</p>
<p>All <strong>Back</strong> and <strong>Next</strong> buttons are enabled by default, except for the <strong>Back</strong> button in the first step and the <strong>Next</strong> button in the last step.</p></td>
</tr>
<tr class="even">
<td><p>skipTab</p></td>
<td><p>Allows you to skip a tab page when certain conditions are met.</p></td>
</tr>
</tbody>
</table>


## Useful methods on the SysDefaultDataWizard class

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Method</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>enabled</p></td>
<td><p>Determines whether the wizard should be displayed in the list of basic setup wizards.</p></td>
</tr>
<tr class="even">
<td><p>mustRun</p></td>
<td><p>Determines if base data exists or if it should be created by the wizard.</p></td>
</tr>
<tr class="odd">
<td><p>description</p></td>
<td><p>Returns a short description of what the wizard does.</p>
<p>The description is used in the wizard's caption if the Caption property has not been set.</p></td>
</tr>
</tbody>
</table>


## See also

[Creating a wizard](how-to-create-wizards.md)

[Wizards in Microsoft Dynamics AX](wizards-in-microsoft-dynamics-ax.md)

[Enabling Wizard Buttons Depending on User Input](enabling-wizard-buttons-depending-on-user-input.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

