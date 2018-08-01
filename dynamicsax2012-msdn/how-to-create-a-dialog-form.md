---
title: 'How to: Create a Dialog Form'
TOCTitle: 'How to: Create a Dialog Form'
ms:assetid: b9a303f9-8fbb-49f3-9a6f-892640d14609
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh812103(v=AX.60)
ms:contentKeyID: 44089902
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Dialog Form [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to use the AOT and a template to create a dialog or drop dialog form. The steps that you use to create the two types of dialog forms are very similar. You will find the difference between creating a dialog form and a drop dialog form is the number of buttons that appear on the form. For more information about differences between dialog and drop dialog forms, see [Dialog Forms Overview](dialog-forms-overview.md).

To create either type of dialog form, you should start with a template. The following steps use the **Dialog** or **DropDialog** template to create a dialog form.

### To create the dialog form

1.  In the AOT, right-click **Forms**, click **New Form from template**, and then click **Dialog** or **DropDialog**. A form is added to the AOT.

2.  Right-click the form, and then click **Properties**. The property sheet for the form appears. In the property sheet, click **Name** and then type a unique name for the form.

3.  Expand the form node, expand **Designs**, and then click **Design**. In the property sheet, find the **Style** property and verify that it is set to **Dialog** or **DropDialog**.

4.  Click **Caption** and then select a label that represents the name that you want to appear in the title of the form window.

### To add task instructions to the form

1.  Expand the **Design** node of the form. Notice that the template added two group controls to the form. The first group is named **DialogContent**.

2.  Click the **DialogContent** group control. In the property sheet, verify the following properties have the specified values:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p><strong>DialogContent</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>DialogContent</strong></p></td>
    </tr>
    </tbody>
    </table>


3.  Expand the **DialogContent** group. Notice that the template added two static text controls to the group. The controls are named **MainInstruction** and **SupplementalInstruction**.

4.  Click the **MainInstruction** static text control. In the property sheet, verify the following properties have the specified values.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p><strong>MainInstruction</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>MainInstruction</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Text</strong></p></td>
    <td><p>Specify the instruction you want to appear at the top of the content pane section of the form. You can select a label or type the text you want to appear.</p></td>
    </tr>
    </tbody>
    </table>


5.  Click the **SupplementalInstruction** static text control. The supplemental instruction is optional and you can decide not to use the **SupplementalInstruction** static text control on the form. To add a supplemental instruction, verify the following properties in the property sheet have the specified values.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>DisplayHeight</strong></p></td>
    <td><p><strong>2</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>DisplayLength</strong></p></td>
    <td><p><strong>80</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p><strong>SupplementalInstruction</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>Auto</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Text</strong></p></td>
    <td><p>Specify the instruction you want to appear under the main instruction. You can select a label or type the text that you want to appear.</p>
    <p>If you leave this property empty, the supplemental instruction does not appear on the form.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Width</strong></p></td>
    <td><p><strong>Column width</strong></p></td>
    </tr>
    </tbody>
    </table>


### To add fields to the content area

1.  Right-click the **DialogContent** group, click **New Control**, and then click **Group**. A group control is added to the form.

2.  Click the new group control. To change the location of the new group in the **DialogContent** group, press Alt+Up Arrow or Alt+Down Arrow.
    
    In the property sheet, specify values for the following properties:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>FrameType</strong></p></td>
    <td><p><strong>None</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name that uniquely identifies the group.</p></td>
    </tr>
    </tbody>
    </table>
    
    For example, the **HcmPositionWorkerAssignmentDialog** form includes several groups in the **DialogContent** section. The first group is a named **Detail**.

3.  Right-click the group that you added in the previous step, click **New Control**, and then click the type of control you want to use. The specified control is added to the group. Repeat this step for each field you want to appear on the form.
    

    > [!NOTE]
    > <P>The following steps show you how to use Extended Data Types (EDT) with the controls on the form. You can use EDTs to specify the field values that you use to populate the fields of the dialog form. If you do not want to use EDTs, you can add a table to the <STRONG>Data Sources</STRONG> node of the form. You can then drag fields and field groups from the data source table onto the <STRONG>DialogContent</STRONG> group of the form. For more information about how to use a table as a form data source, see <A href="how-to-add-a-field-group-to-a-form.md">How to: Add a Field Group to a Form</A>.</P>

    
    For example, the **CustCollectionsNewActivityAppointment** form adds several **StringEdit** and **UtcDateTimeEdit** controls.

4.  Click the control you want to associate with an EDT. If you want to move a field or field group, click the control and then press Alt+Up Arrow or Alt+Down Arrow.
    
    In the property sheet, specify values for the following properties:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>AutoDeclaration</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ExtendedDataType</strong></p></td>
    <td><p>Click the name of the EDT that specifies the values that you want to appear in the control.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Mandatory</strong></p></td>
    <td><p>Click <strong>Yes</strong> if you want the field to be a required field.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p>Type a name that uniquely identifies the control.</p></td>
    </tr>
    </tbody>
    </table>
    
    For example, the **CustCollectionsNewActivityAppointment** form includes a **StringEdit** control named **smmActivities\_TypeId**. The **ExtendedDataType** property of that control specifies that the control show values specified by the **smmActivityTypeId** EDT.

5.  Repeat the previous step for each control that you added to the form.

6.  To complete the action that is initiated by a dialog form, you add code to the **closeOk** method of the dialog form. The code you add to the method depends on the action or activity you want the dialog form to finish.
    
    For example, the **closeOk** method of the **CustCollectionsNewActivityAppointment** form uses the field values from the drop dialog form to create an appointment activity. The appointment is associated with the selected record in the Accounts Receivable Collections list page. The following code example shows how to use the **closeOk** method to create an activity using field values from the drop dialog form. Notice how the values of the smmActivities\_TypeId, smmActivities\_Purpose, smmActivities\_UserMemo, smmActivities\_StartDateTime, and smmActivities\_EndDateTime controls are used to populate the property values of the activity record.
    ```X++  
        public void closeOk()
        {
            RefRecId custRecId = element.args().record().RecId;
            RefRecId caseRecId;
            smmActivities activity;
        
            activity.initValue(smmActivityCategory::Appointment);
            activity.setActivityNum();
            activity.Closed = NoYes::No;
            activity.modifiedField(fieldnum(smmActivities, Closed));
            activity.TypeId = smmActivities_TypeId.text();
            activity.Purpose = smmActivities_Purpose.text();
            activity.UserMemo = smmActivities_UserMemo.text();
            activity.insertParentLink(smmActivityParentType::Customer, custRecId, true);
            activity.insertParentLink(smmActivityParentType::Collections, custRecId);
            if(formHasMethod(element.args().caller(), ‘parmSelectedCaseRecId’))
            {
                caseRecId = element.args().caller().parmSelectedCaseRecId();
                if(caseRecId)
                {
                    activity.insertParentLink(smmActivityParentType::Case, caseRecId);
                }
            }
            activity.StartDateTime = DateTimeUtil::removeTimeZoneOffset(smmActivities_StartDateTime.dateTimeValue(), DateTimeUtil::getUserPreferredTimeZone());
            activity.EndDateTime = DateTimeUtil::removeTimeZoneOffset(smmActivities_EndDateTime.dateTimeValue(), DateTimeUtil::getUserPreferredTimeZone());
            activity.insert();
        
            if(formHasMethod(element.args().caller(), identifierstr('setTouched')))
            {
                element.args().caller().setTouched();
            }
        
            super();
        
            element.saveLastValues();
        }
    ```
### To add the cancel and commit buttons

1.  In the **Design** node of the form, find and then click the **DialogCommit** group control. In the property sheet, verify the following properties have the specified values:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>AlignChild</strong></p></td>
    <td><p><strong>No</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p><strong>DialogCommit</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>DialogCommit</strong></p></td>
    </tr>
    </tbody>
    </table>


2.  Expand the **DialogCommit** group. Notice how the template includes a button group control named **ButtonGroup**.

3.  Click the **ButtonGroup** control. In the property sheet, verify the following properties have the specified values:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p><strong>ButtonGroup</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>DialogCommitContainer</strong></p></td>
    </tr>
    </tbody>
    </table>


4.  Expand the **ButtonGroup** node. Notice how the template includes a command button control named **OKButton**.

5.  Click the **OKButton** button control. In the property sheet, verify the following properties have the specified values:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Command</strong></p></td>
    <td><p><strong>OK</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>DefaultButton</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p><strong>OKButton</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ShowShortCut</strong></p></td>
    <td><p><strong>No</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Text</strong></p></td>
    <td><p>If you leave this property empty, the button shows <strong>OK</strong> as a label.</p>
    <p>You can customize the button label. To change the button text, select a label or type the text that you want to appear.</p></td>
    </tr>
    </tbody>
    </table>


6.  If you use the **Dialog** template to create the form, **ButtonGroup** includes a second command button named **CancelButton**.
    
    If you use the **DropDialog** template to create the form, a cancel button is not used. As a result, the control does not appear in the button group and you can skip the following step.

7.  If you have a **CancelButton** on the form, click the button control. In the property sheet, verify the following properties have the specified values:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Command</strong></p></td>
    <td><p><strong>Cancel</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p><strong>CancelButton</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>SaveRecord</strong></p></td>
    <td><p><strong>No</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Text</strong></p></td>
    <td><p>If you leave this property empty, the button shows <strong>Cancel</strong> as a label.</p>
    <p>You can customize the button label. To change the button text, select a label or type the text that you want to appear.</p></td>
    </tr>
    </tbody>
    </table>


8.  Right-click the form and then click **Save**.

To view the form, right-click the form and then click **Open**. The form appears in a separate window.

If you expand the **DialogCommit** group, you will see the group includes another group control named **Footnote**. You can use the footnote are to show messages or additional instructions. To learn how to add information to the footnote area of a dialog form, see [How to: Add a Footnote Section to a Dialog Form](how-to-add-a-footnote-section-to-a-dialog-form.md).

A dialog form can include a collection of fields or controls that are at first hidden from view. To learn how to add hidden fields and how you can use a button to make them visible, see [How to: Hide fields on a Dialog Form](how-to-hide-fields-on-a-dialog-form.md).

If you use a button on a form to open the dialog, you might want to update that form when the dialog closes. To learn how to refresh the calling form, see [How to: Refresh the Calling Form](how-to-refresh-the-calling-form.md).

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

