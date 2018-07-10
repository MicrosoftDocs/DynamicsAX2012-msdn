---
title: Methods on a Form
TOCTitle: Methods on a Form
ms:assetid: 75a1dd66-5229-461d-9c77-77df137f7b9b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa674599(v=AX.60)
ms:contentKeyID: 35245973
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Methods on a Form 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Each form has a set of standard methods. You can override these methods to change the behavior of the form, respond to user interface events, and customize the appearance of a form.

To override a form method, expand the node for the form, right-click the **Methods** node, click **Override Method**, and then click the name of method that you want to override. Methods that have been customized appear in the **Methods** node. To view the code, double-click the method name.

You can define variables that can be used in form methods by adding them to the classDeclaration method available in the **Methods** node of the form.

There are also methods on each form data source and on each form control. For more information about these methods, see [Methods on a Form Data Source](methods-on-a-form-data-source.md) and [Methods on Form Controls](methods-on-form-controls.md).

The following table lists the methods available for forms and explains when they are executed. All the form methods are also members of the FormRun system class. For more information about each method, click the method name.


> [!NOTE]
> <P>Code written on forms cannot be re-used or inherited. If possible, write your code on the underlying table or in a class.</P>



<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Method name</p></th>
<th><p>Executed when</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920109(v=ax.60)">activate</a></p></td>
<td><p>A form receives focus.</p></td>
<td><p>Returns boolean data type that specifies whether a form has focus.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920110(v=ax.60)">addHistory</a></p></td>
<td><p>The address bar history changed.</p></td>
<td><p>Adds an entry after the list of entries that appear when you click the travel history button.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/hh337538(v=ax.60)">blockPersonalization</a></p></td>
<td><p>A personalization change is made to the form.</p></td>
<td><p>Specifies whether you can open the personalization form. Set to true when the form has been personalized and the form has to be restarted before more changes can be accepted.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920113(v=ax.60)">canClose</a></p></td>
<td><p>The form is closed.</p></td>
<td><p>Specifies whether you can close the form. The call to super in the method checks whether closing the form is a valid action.</p>
<p>The canClose method is started by the closeCancel or the closeOK methods.</p>
<p>Use this method to add your own checks that determine whether the form should close.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920114(v=ax.60)">canSubmitToWorkflow</a></p></td>
<td><p>This method is invoked in updateWorkflowControls to determine when the <strong>Submit</strong> button and context message are to be displayed.</p></td>
<td><p>Use this method to determine whether the <strong>Submit</strong> button should be displayed.</p>

> [!IMPORTANT]  
> <P>To enable workflow, you MUST override this method as the base implementation always returns False.</P>

</td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920115(v=ax.60)">close</a></p></td>
<td><p>The form is closed.</p></td>
<td><p>Closes a form. The call to super in this method closes the form window, manages database updates, and sets the closed method to true.</p>
<p>The close method is started either by the closeCancel or the closeOK methods.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920116(v=ax.60)">closeCancel</a></p></td>
<td><p>The user presses a <strong>Cancel</strong> button or the ESC key.</p></td>
<td><p>Stops a form from closing. The super call sets the Boolean flag closedCancel, and calls the close method.</p>
<p>When a form is closed with closeCancel, user modifications are not saved.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920117(v=ax.60)">closed</a></p></td>
<td><p>The form is closed.</p></td>
<td><p>Use this method to check whether the form has been closed.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920118(v=ax.60)">closedCancel</a></p></td>
<td><p>Set by closeCancel.</p></td>
<td><p>Use this method to check whether the form has been closed by a cancel action. The method is set to true if the form is closed by a cancel action (<strong>Cancel</strong> button).</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920119(v=ax.60)">closedOk</a></p></td>
<td><p>Set by closeOK.</p></td>
<td><p>Use this method to check whether the form has been closed by the <strong>OK</strong> button. The method is set to true if an <strong>OK</strong> button was used to close the form.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920120(v=ax.60)">closeOk</a></p></td>
<td><p>The user presses an <strong>OK</strong> button.</p></td>
<td><p>Specifies whether the form was closed by clicking the <strong>OK</strong> button. The call to the super method sets the Boolean flag closedOK, and calls the close method.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920121(v=ax.60)">closeSelect</a></p></td>
<td><p>A lookup form is closed following the selection in the form.</p></td>
<td><p>Use this method to close the lookup form. The closeSelect method calls the closeOK method, and it is called before the close method is called.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920122(v=ax.60)">closeSelectRecord</a></p></td>
<td><p>A lookup form is closed when a record is selected in the form.</p></td>
<td><p>Supports the use of a <strong>Reference</strong> control that is bound to and displays all of a record. Handles the close and select event for the lookup form.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg906240(v=ax.60)">controlMethodOverloadObject</a></p></td>
<td><p>Not called by the system.</p></td>
<td><p>Enables you to specify that a user interface event should trigger a method on an object instead of on the form control. The object is specified in the parameter for the method. For example, you might want to call a clicked method on a class instead of on the form.</p>

> [!note]  
> <P>If you want to call an event method on the form, use the FormRun.controlMethodOverload method instead of the controlMethodOverloadObject method.</P>

</td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg906241(v=ax.60)">copy</a></p></td>
<td><p>The user performs a copy operation on the form.</p></td>
<td><p>Use this method to complete a copy operation. If the user has selected multiple records, the copy operation is handled by the call to super in this method. If only one record has been selected, the copy method on the form calls the copy method on the form control.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg906242(v=ax.60)">createRecord</a></p></td>
<td><p>The user executes the <strong>New</strong> action for the form.</p></td>
<td><p>Enables you to respond to the creation of a new record. When the method executes, the create method is called on the specified data source.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg906245(v=ax.60)">cut</a></p></td>
<td><p>The user performs a cut operation on the form.</p></td>
<td><p>Use this method to call the cut method on the form control.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg906252(v=ax.60)">doApply</a></p></td>
<td><p>The user closes a modal window.</p></td>
<td><p>Use this method to follow-up on the closing of the modal window.</p>

> [!note]  
> <P>A modal window is a secondary window that requires the user to complete an interaction within it and to close it before continuing with any interaction outside the window.</P>

</td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg906253(v=ax.60)">docCursor</a></p></td>
<td><p>Not called by the system.</p></td>
<td><p>Returns a cursor to the current data source record. This is useful when a form has more than one data source.</p>

> [!note]  
> <P>This method is used by the document management system.</P>

</td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg906255(v=ax.60)">finalize</a></p></td>
<td><p>The form is closed.</p></td>
<td><p>Destructs the form object and releases the space allocated to it.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg906256(v=ax.60)">firstField</a></p></td>
<td><p>Focus moves to the first field on the form.</p></td>
<td><p>Use an integer to specify the field flag.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920241(v=ax.60)">getActiveWorkflowConfiguration</a></p></td>
<td><p>Used by the updateWorkflowControls method to determine what controls to display.</p></td>
<td><p>Returns the active workflow configuration for the current document.</p>
<p>The method returns the workflow configuration that was originally retrieved by the loadWorkflowConfiguration method.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920242(v=ax.60)">getActiveWorkflowTrackingStatus</a></p></td>
<td><p>Used by the updateWorkflowControls method to determine what controls to display.</p></td>
<td><p>Returns the current workflow tracking status record to load with the workflow controls.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920243(v=ax.60)">getActiveWorkflowWorkItem</a></p></td>
<td><p>Used by the updateWorkflowControls method to determine what controls to display.</p></td>
<td><p>Returns the active work item for the current document.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920251(v=ax.60)">init</a></p></td>
<td><p>The form is opened.</p></td>
<td><p>Use the method to initialize a form. The init method is started immediately after the new method and creates the run-time image of the form.</p>
<p>Typical uses of init include the following:</p>
<ul>
<li><p>Modifying a form by using the FormBuild system class</p></li>
<li><p>Initializing variables for specific controls on the form.</p></li>
</ul>
<p>You must call the super method if you override this method, and you should add your code before the super call.</p>
<p>In addition to creating the form, the call to the super method constructs the data source for the form by starting the init method on the data source. The form data source init method creates the query to fetch data from the database and sets up links if the form is linked to another form.</p>
<p>For more information about how to access the active query generated by the system, see <a href="how-to-access-the-active-query-on-forms.md">How to: Access the Active Query on Forms</a>.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920252(v=ax.60)">initWorkflowControls</a></p></td>
<td><p>During initialization of the form.</p></td>
<td><p>Adds the workflow controls to the form but leaves the controls disabled.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920256(v=ax.60)">lastField</a></p></td>
<td><p>Focus moves to the last field on the form.</p></td>
<td><p>Override this method on a form to pass different bit-flag constants or to prevent the move to the last field group by preventing the call to the super method.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920257(v=ax.60)">loadUserSetting</a></p></td>
<td><p>The user settings for a form are loaded.</p></td>
<td><p>Use this method when user settings are loaded.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920258(v=ax.60)">loadWorkflowConfiguration</a></p></td>
<td><p>When a document is opened in a form.</p></td>
<td><p>Finds the workflow configuration for the current document. The method evaluates activation conditions for all workflow configurations associated with the document.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920264(v=ax.60)">nextField</a></p></td>
<td><p>Focus moves to the next field, for example, when the user presses the TAB key.</p></td>
<td><p>Use this method to focus on the first visible, editable field in the form.</p>
<p>When the nextField method is executed, the system checks the DataSource property on the container control to determine which table data should be displayed.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920265(v=ax.60)">nextGroup</a></p></td>
<td><p>Focus moves to the next group of fields, for example, when the user presses SHIFT+TAB.</p></td>
<td><p>Use this method to check the DataSource property on the container control to determine which table data should be displayed.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920268(v=ax.60)">paste</a></p></td>
<td><p>The user performs a paste operation (CTRL+V) on the form.</p></td>
<td><p>Use the paste method to call the corresponding method on the form control.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920269(v=ax.60)">prevField</a></p></td>
<td><p>Focus moves to the previous field.</p></td>
<td><p>Use this method to check the DataSource property on the container control to determine which table data should be displayed.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920270(v=ax.60)">prevGroup</a></p></td>
<td><p>Focus moves to the previous group of fields.</p></td>
<td><p>Use this method to check the DataSource property of the container control to determine which table data should be displayed.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920271(v=ax.60)">print</a></p></td>
<td><p>When the user has a form open and starts the <strong>Print</strong> command on the <strong>File</strong> menu.</p></td>
<td><p>Use this method to generate a report based on the data source fields in the <a href="implementing-automatic-reports-for-forms.md">AutoReport</a> field group. Add your own code to the print method if you want to change the layout of this report.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920272(v=ax.60)">printPreview</a></p></td>
<td><p>When the user has a form open and starts the <strong>Print Preview</strong> command from the <strong>File</strong> menu.</p></td>
<td><p>Use this method to view the automatic report for the active form. You can also call the printPreview method to initiate the view of the automatic report.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920274(v=ax.60)">reload</a></p></td>
<td><p>Reserved for future use.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920277(v=ax.60)">resize</a></p></td>
<td><p>The form opened and when it is resized.</p></td>
<td><p>Use this method to determine the new height and width of the form.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920279(v=ax.60)">run</a></p></td>
<td><p>The form is opened.</p></td>
<td><p>Call the run method immediately after the init method. The call to the super method makes the form window appear on the screen and performs a database search for the data to be displayed in the form.</p>
<p>Typical reasons for overriding this method include the following:</p>
<ul>
<li><p>Activating or de-activating some fields</p></li>
<li><p>Modifying the query</p></li>
</ul>
<p>You must call the super method if you override this method. You should add your code before the call to the super method.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920280(v=ax.60)">saveUserSetting</a></p></td>
<td><p>When the form is closed after a user makes changes to the user settings.</p></td>
<td><p>Saves the user setting for the form.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920281(v=ax.60)">selectControl</a></p></td>
<td><p>When the form is opened, or when the user selects a different control.</p></td>
<td><p>Use this method to determine the control that was selected.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920287(v=ax.60)">send</a></p></td>
<td><p>When a change to the data in a form is submitted to the database.</p></td>
<td><p>Use this method to print an automatic report from the contents of the form.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920289(v=ax.60)">setApply</a></p></td>
<td><p>Not started by the system.</p></td>
<td><p>Takes the object to be started as a parameter. This is typically a form.</p>
<p>An apply() method must be present on the form or class and is called if a command button exists on the calling form.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/hh337545(v=ax.60)">skipSaveUserSetting</a></p></td>
<td><p>When you attempt to personalize a form.</p></td>
<td><p>Specifies whether the form saves user settings when it closes. If you personalize the form and a restart is required, additional personalization information is not saved when the form closes.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920294(v=ax.60)">sysColorChanged</a></p></td>
<td><p>The form color is changed.</p></td>
<td><p>Use this method to determine when the form color is changed.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920296(v=ax.60)">task</a></p></td>
<td><p>The user performs some task in a form by using the toolbar, the menu, or the keyboard.</p></td>
<td><p>Use the call to the super method to start the relevant method for the task. For example, if the user has started the TAB key, the nextField method is called.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920300(v=ax.60)">updateWorkflowControls</a></p></td>
<td><p>Invoked by the formNotify method when the workflow data source changes. In addition, this method can be invoked when a work item is completed.</p></td>
<td><p>Refreshes the workflow controls, and determines what buttons and context messages must be displayed. The method inspects workflow configurations, work items for the current user, and then calls canSubmitToWorkflow or other methods.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920301(v=ax.60)">wait</a></p></td>
<td><p>The system is waiting for a form to finish execution.</p></td>
<td><p>Use the wait after the form prompts the user for some input. The next line of code will not be executed until the user either closes the form or presses <strong>Apply</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg922589(v=ax.60)">equal</a></p></td>
<td><p>Not activated by the system.</p></td>
<td><p>Use this method for debugging.</p>
<p>Use equal to discover whether the object supplied as a parameter is equal to the current object.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg922602(v=ax.60)">xml</a></p></td>
<td><p>Not activated by the system.</p></td>
<td><p>Use this method for debugging.</p>
<p>Retrieves an object reference for the form as an XML string.</p></td>
</tr>
</tbody>
</table>


## See also

[FormRun Class](https://msdn.microsoft.com/en-us/library/gg920249\(v=ax.60\))

[Form Classes](form-classes.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

