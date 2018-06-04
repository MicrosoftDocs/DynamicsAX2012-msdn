---
title: 'How to: Add Custom Actions UI for Alerts'
TOCTitle: 'How to: Add Custom Actions UI for Alerts'
ms:assetid: cab1ea84-a94c-46b4-83ab-17dd709ea57d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa868367(v=AX.60)
ms:contentKeyID: 35251320
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add Custom Actions UI for Alerts 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The EventCreateRule form is divided into function groups.

In the **Send email alerts for job status changes** group, the user can define the type of event that is monitored by the rule.

In the **Alert me for** group, the user can, among other things, set up filters on records that are monitored.

In the **Other alerts** group, the user can define how to receive alerts.

If you need to expose UI to configure your own custom actions, it is recommended that you create further groups on this form and on the EventRule form. The following procedure shows how to do this.

## Add UI for Custom Actions on the Create Alert Rule and Manage Alert Rules Forms

1.  Add your custom fields that need to be set on the EventCreateRule and EventRule forms to the EventRule table.

2.  To modify the EventCreateRule form, add a new group and drag your custom fields from the EventRule data source.

3.  Set the **Caption** for the group, set the FrameOptionButton property to false, set the AutoDeclaration property to true, and set the width to **Column width**.

4.  Make sure that your custom group can be expanded/collapsed like the other groups on the form, and that the state of the group (expanded or collapsed) is sustained between multiple invocations of the EventCreateRule form. This can be achieved as follows:
    
    1.  Add a Boolean member variable holding the state of your group to the [EventCreateRule Class](https://msdn.microsoft.com/en-us/library/gg771216\(v=ax.60\)), and also add the variable to the CurrentList macro. Create a corresponding parmExpandMyGroup method on the class.
    
    2.  Add the following code to the initFormControls method on the EventCreateRule form:
        
            myGroup.expand(element.runBase().parmExpandMyGroup());
                if (!MyGroup.expand())
                    MyGroup.clicked();
    
    3.  Add the following code to the close method on the EventCreateRule form:
        
            element.runBase().parmExpandMyGroup(MyGroup.expand());

5.  To modify the EventRule form, create a new group and drag your custom fields from the EventRule data source. Then, you can reference your custom fields in the EventRule table from your custom action classes and modify the grid by adding new fields.

6.  Optionally, you can record the values of your custom fields according to each alert. To do this, add the fields to the EventInbox table and modify the EventAlertInbox form, as you did with the EventRule form.

## Example of Forms with Custom Field

Consider the example of the custom action (alert logging) in [How to: Add Custom Actions for Alerts](how-to-add-custom-actions-for-alerts.md). When you have added your isLogged custom field to the EventRule table and have displayed it by means of the Alert logging group in both forms, the Log into database check box is available in the EventCreateRule and EventRule forms.

![Selecting the Alert logging option](images/Aa868367.ManageAlertRules(en-us,AX.60).gif "Selecting the Alert logging option")

**Manage alert rules form with the Alert logging option selected**

You might also want to add custom code to your forms to hide the Alert Logging section, unless an alert rule is set up on a table for which alerts are logged.

Add the following code to the initFormControls method of the EventCreateRule form, and to the setControlsActive method on the EventRule data source of the EventRule form.

    //alertLog is the name of your custom group control.
    
    if (element.eventRuleFormHandler().parmPrimTableId() == tableNum(LedgerTable))
          // element.eventRuleFormHandler().parmPrimTableId() == tableNum(Table2) ||
          // element.eventRuleFormHandler().parmPrimTableId() == tableNum(Table3)
            alertLog.visible(true);
       else
            alertLog.visible(false);
    ….

## See also

[How to: Add Custom Actions for Alerts](how-to-add-custom-actions-for-alerts.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

