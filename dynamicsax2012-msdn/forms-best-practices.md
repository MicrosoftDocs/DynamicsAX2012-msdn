---
title: Forms Best Practices
TOCTitle: Forms
ms:assetid: 5892c84e-bf82-40e3-b943-0097cf631f75
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa640643(v=AX.60)
ms:contentKeyID: 35244336
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Forms Best Practices 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes the best practices for standard view and data-entry forms. [Best practices for lookup forms](best-practices-for-lookup-forms.md) are described separately. For user experience information, see [Form User Experience Guidelines](form-user-experience-guidelines.md). Best practices for form properties are described in the topics that are listed in the See Also section.

## Form Name

The name of a form should be identical to the name of the table that is used as its data source.

## Tabbed Pages

All data entry and view forms that use tables with the table groups—group, main, or transaction—must have two tabbed pages ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon"):

  - **Overview** with a grid, (@SYS9039)

  - **General** with non-grid table data groups, (@SYS2952)

These tabbed pages enable the user to choose between the spreadsheet style of the grid, and the form style of the non-grid view. If you do not use the previous labels for the first two tabs of a data entry form, a best practices warning appears. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

A form should open on the first tabbed page. The Tab property for the **Tab** control in your form design must be set to **Auto**. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

Do not set the HelpText property for a TabPage form or a group on a tabbed page unless the form is a wizard, or unless the group has the FrameOptionButton property set. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

## Keep Default Settings

When you design forms, their properties should retain their **Auto** or **Default** settings. This is the primary form-design rule.

Many aspects of form design are defined in the data source table. They shouldn't (usually) be overridden in the form. These form-design aspects include the following:

  - Relations

  - Delete actions

  - TitleField1 and TitleField2 properties that are used by the caption method

  - Labels used as captions on field groups, on controls, or on the table field group controls

  - Order of the fields in field groups is reflected when the field groups are displayed on the forms

  - AutoReport field group that specifies the initial print layout

The first index is used for sorting in the form, unless this behavior is overridden.

## Enable IntelliMorph Features

You should enable all IntelliMorph features in forms. Following are examples of how to enable these features:

  - Construct the form by using a menu item and a MenuFunction object. This is automatically done when you use menu items.

  - Prioritize your data design elements (controls) as follows:
    
      - Table field groups with the AutoDataGroup property set to **Yes**
        
        –or–
        
        Table field groups (with the AutoDataGroup property set to **No**)
        
        –or–
        
        Table fields
        
        –or–
        
        Display and/or edit methods—preferably from the data source table
        
        –or–
        
        Controls that are based on extended data types

  - Ensure that labels, and to a certain extent HelpTexts, are not overridden on the controls—especially not with the same value as the one supplied from the Field, the display and/or edit methods or the extended data type. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

Ensure that the Caption is not overridden on the Table field groups bound group controls, and especially not with the same value that is supplied from the Table field group.

## Form Size

Forms must have the ability to be resized—the Width and Height properties on the Tab control and the **Grid** control must be set to column width/column height.

A form must fit a screen that has a 1024 x 768 resolution. Because the status bar, caption, and toolbars take up about 100 pixels vertically, and the menu bar in the Navigation Pane takes up 200 pixels, the maximum size of a form should be 824 x 668. If you exceed this size, a best practices warning appears. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon") If you exceed 1080 x 924, a best practices error appears. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

## Form Initialization

If a form cannot be started (initialized) correctly, you must inform the user and end the process. For example, if the form has to be started by using certain parameters and is not, throw an error as soon as possible. Provide a straightforward, descriptive error message that states the problem. The following example shows an error being thrown.
```X++  
    void init() 
    {
        if (!element.args() 
            || element.args().dataset() 
            != tablenum(BOMCalcTable))
            throw error(Error::MissingParameter(element));
        super();
        ...
    }
```
## Printing from Forms

By default, printing is available from all forms with a data source through the Auto Report facility.

If a special report has been created to support general printing from the form, implement it on the form's user interface. Override the standard print method on the form. The range (amount) to print must by default correspond to what is on the screen. The report prints when the Print icon is activated—an explicit **Print** button should not be added to the form.

If (in rare cases) a **Print** button is needed, implement it by using a **Print CommandButton** control.

Implement the call to the report by using its menu item (depending on the functionality needed) as shown in the following example.
```X++  
    void print()
    {
        new MenuFunction(menuItemOutputStr(...),
                         MenuItemType::Output).run([...]); 
    }
```
Reports with more specialized functionality should be added to the form by using menu item buttons.

## ActiveX Control Security

ActiveX controls can be a security threat. Note the following security issues:

  - ActiveX controls run in the same security context as the Microsoft Dynamics AX client.

  - ActiveX controls that are used by Microsoft Dynamics AX should not be marked as safe for scripting.

If an ActiveX control in Microsoft Dynamics AX has a method with a signature and a name that are equal to a public method that is exposed by the ActiveX control, the X++ method is always called when it is referenced from X++ code.

For more information about ActiveX controls and security, see http://msdn.microsoft.com/workshop/components/activex/sec\_activex.asp.

## Image and Animation Files

To help prevent an attacker from modifying the contents of image and animation files that are used by the form, make sure that that access control lists are applied to the image and animation files.

## See also

[Best Practices for Form Data Source Properties](best-practices-for-form-data-source-properties.md)

[Best Practices for Form Design Properties](best-practices-for-form-design-properties.md)

[Best Practices for Form Control Properties](best-practices-for-form-control-properties.md)

[Best Practices for Lookup Forms](best-practices-for-lookup-forms.md)

[No Code in Forms](no-code-in-forms.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

