---
title: Enabling Wizard Buttons Depending on User Input
TOCTitle: Enabling Wizard Buttons Depending on User Input
ms:assetid: f45e00bc-744b-4368-8bb2-35b5cd23ae74
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa887805(v=AX.60)
ms:contentKeyID: 35253505
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Enabling Wizard Buttons Depending on User Input [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can disable the **Next** button for a particular step in a wizard until the user has entered the required information.

Disable the Next Button

  - Set the initial state of the button by using the setupNavigation method.

  - Test for user input, and then use the nextEnabled method to enable the button if the user input has been validated.

For example, the **Next** button for the **Naming** tab page in the Wizard Wizard is disabled until there is something in the **Specify the Name of your Wizard** box.

## Setting the Initial State of the Next Button

The setupNavigation method allows you to set the initial states of the **Back** and **Next** buttons on your wizard. This method is available if you have based your wizard on the SysWizard class, for example, by [using the Wizard Wizard](how-to-create-wizards.md).

For example, the setupNavigation method for the Wizard Wizard is shown in the following example.

    void setupNavigation()
    {
    // First, complete the name.
        nextEnabled[formRun.namesTabIdx()]          =   false; 
    // Default data tabbed page.
        skipTab[formRun.defaultDataSetupTabIdx()]   = true;  
    }

## Testing the user input

You can test to discover whether the user has entered the required information, and whether the enabling of the **Next** button is performed on the relevant form control method.

For example, the code that enables the **Next** button on the **Naming** tab page in the Wizard Wizard is located in the textChange method on the StringEdit:WizardName control of the SysWizardWizard form.

    if (this.text())
    {
        if   (!sysWizard.isNextEnabled())
        {
            sysWizard.nextEnabled(true,   sysWizard.curTab(), false);
        }
    }
    else
    {
        if   (sysWizard.isNextEnabled())
            sysWizard.nextEnabled(false,   sysWizard.curTab(), false);
    }

The first line of the code tests whether text has been entered in the **Specify the Name of your Wizard** box. If it has, the **Next** button is enabled.

The second and third parameters in nextEnabled are optional. The second parameter specifies the tab page where the **Next** button should be enabled. The default is the current tab page. The third parameter indicates whether focus should be moved to the **Next** button; the default is true.

## See also

[How to: Create Wizards](how-to-create-wizards.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

