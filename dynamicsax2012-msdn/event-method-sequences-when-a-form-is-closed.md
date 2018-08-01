---
title: Event Method Sequences when a Form is Closed
TOCTitle: Event Method Sequences when a Form is Closed
ms:assetid: 2b671f06-0d3d-414f-a574-68f92eb0013c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa602745(v=AX.60)
ms:contentKeyID: 35241799
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Event Method Sequences when a Form is Closed [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Most forms in Microsoft Dynamics AX are closed when a user clicks the **Close** button (the standard button in the upper-right corner of most windows). Some forms can be closed by clicking either an **OK** or a **Cancel** button. When the form is closed, event methods are executed.

## Close the Form by Using the Cancel Button

When a user closes a form by clicking the **Cancel** button, event methods are executed in the following sequence:

1.  closeCancel on the form.

2.  canClose on the form.

3.  close on the form.


> [!NOTE]
> <P>The FormRun class has the closed method and the closedCancel method. These event methods are not executed when the <STRONG>Cancel</STRONG> button is clicked.</P>



When a form is closed with the closeCancel event method, the user's changes are not saved.

## Scenario

This scenario uses a form that contains one CheckBox control as its only control. Assume that the CheckBox control is bound to a form's data source and that the control can update the data source.

### ![Aa602745.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa602745.collapse_all(en-us,AX.60).gif")Close the Form by Using the Close Button

When a user closes a form by clicking the **Close** button, event methods are executed in the sequence shown in the following lists. These lists are based on the previous scenario.

Following is the sequence of event methods when the form is closed—without the user clicking the check box.

1.  canClose on the form.

2.  leave on the check box.

3.  leave on the check box.

4.  leave on the data source.

5.  leaveValidate on the data source.

6.  leave on the check box.

7.  leave on the check box.

8.  close on the form.

9.  saveUserSetting on the form.

Following is the sequence of event methods when the form is closed—after the user has clicked a check box.

1.  canClose on the form.

2.  leave on the check box.

3.  leave on the check box.

4.  validateWrite on the data source.

5.  Write on the data source.

6.  update on the table.

7.  leaveRecord on the data source.

8.  leave on the data source.

9.  leaveRecord on the data source.

10. leave on the check box.

11. leave on the check box.

12. close on the form.

13. saveUserSetting on the form.

### ![Aa602745.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa602745.collapse_all(en-us,AX.60).gif")Close the Form by Using the OK Button

Some forms can be closed by clicking an **OK** button. This leads to almost the same event method sequence as shown in the Close the Form by Using the Close Button section. The only difference is that clicking the **OK** button causes the Form.closeOK event method to be executed first.

## See also

[Event Method Sequences in Form Scenarios](event-method-sequences-in-form-scenarios.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

