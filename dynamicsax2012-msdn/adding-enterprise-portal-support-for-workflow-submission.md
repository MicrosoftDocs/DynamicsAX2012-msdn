---
title: Adding Enterprise Portal Support for Workflow Submission
TOCTitle: Adding Enterprise Portal Support for Workflow Submission
ms:assetid: 8c2bdbf1-1a7b-4cae-b7a0-0ec38c8c253a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Ee677503(v=AX.60)
ms:contentKeyID: 35245485
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Adding Enterprise Portal Support for Workflow Submission 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When creating a new workflow for Microsoft Dynamics AX, one of the classes you implement is used to submit a document to workflow.

## Submit to Workflow class

The class that you use to submit items to workflow must support submissions from both the Microsoft Dynamics AX client and from Enterprise Portal. The main method of this class performs the submission action. This method must determine whether the submission is originating from a Microsoft Dynamics AX client or from Enterprise Portal. It does this by examining the menu item that was used to perform the submission. Based on the result, the corresponding submission code is run.

## Example

The following X++ code example is the main method of the **FCMSubmitWorkOrderToWorkflow** class from the Facility Management sample for Microsoft Dynamics AX. Notice how it examines the menu item used to start the workflow submission.
```X++  
    public static void main(Args args)
    {
        // Variable declaration.
        recId recId;
        WorkflowCorrelationId workflowCorrelationId;
    
        // Hardcoded workflow type name
        workflowTypeName workflowTypeName = workflowtypestr("FCMWorkOrderApproval");
    
        // Initial note is the information that users enter when they
        // submit the document for workflow.
        WorkflowComment initialNote = "Enter any comments here.";
        WorkflowSubmitDialog workflowSubmitDialog;
    
        // The name of the table containing the records for workflow.
        FCMWorkOrders fcmworkOrders;
        FormDataSource fcmworkorders_ds;
    
        // Workflow Control Context
        EPWorkflowControlContext workflowControlContext;
    
        // The menu item that was used to submit the trip to workflow.
        // This is used to find out whether the workflow was submitted from the
        // Microsoft Dynamics AX client or from Enterprise Portal.
        str menuItemName = args.menuItemName();
    
        if(menuItemName == menuitemactionstr(FCMWorkOrderApprovalSubmitToWorkflow))
        {
            // Workflow is starting from the Windows client. This can be determined
            // because the menu item for submitting the workflow on the Windows
            // client was chosen by the user.
    
            // Opens the submit to workflow dialog.
            workflowSubmitDialog = WorkflowSubmitDialog::construct(args.caller().getActiveWorkflowConfiguration());
            workflowSubmitDialog.run();
    
            if (workflowSubmitDialog.parmIsClosedOK())
            {
                // Find what record from the Work Orders table is being submitted to workflow.
                recId = args.record().RecId;
    
                // Get comments from the submit to workflow dialog.
                initialNote = workflowSubmitDialog.parmWorkflowComment();
    
                try
                {
                    // Update the record in the FCMWorkOrders table that is being submitted to workflow.
                    // The record is moved to the 'submitted' state.
                    fcmworkOrders = args.record();
                    fcmworkOrders.WorkflowState = FCMWorkOrderWorkflowState::Submitted;
    
                    // Activate the workflow.
                    workflowCorrelationId = Workflow::activateFromWorkflowType(workflowTypeName, recId, initialNote, NoYes::No);
    
                    // Update the table using the form datasource.
                    fcmworkorders_ds = fcmworkOrders.dataSource();
                    if (fcmworkorders_ds)
                    {
                        fcmworkorders_ds.write();
                        fcmworkorders_ds.refresh();
                    }
    
                    // Updates the workflow button to diplay Actions instead of Submit.
                    args.caller().updateWorkflowControls();
                }
    
                catch(exception::Error)
                {
                    info("Error on workflow activation.");
                }
            }
        }
        else
        {
             // Workflow is starting from Enterprise Portal.
    
             // Retrieve the workflow controller context from the arguments passed in.
             workflowControlContext = args.caller();
    
             // Find what record from the Work Orders table is being submitted to workflow.
             recId = args.record().RecId;
    
             // Get comments from the submit to workflow dialog.
             initialNote = workflowControlContext.getWorkflowComment();
    
            try
            {
                // Activate the workflow.
                workflowCorrelationId = Workflow::activateFromWorkflowType(workflowTypeName, recId, initialNote, NoYes::Yes);
    
                // Update the record in the FCMWorkOrders table that is being submitted to workflow.
                // The record is moved to the 'submitted' state.
                // This update causes the workflow bar in EP to be updated automatically.
                fcmworkOrders = args.record();
                fcmworkOrders.WorkflowState = FCMWorkOrderWorkflowState::Submitted;
                fcmworkorders_ds = fcmworkOrders.dataSource();
                if (fcmworkorders_ds)
                {
                    fcmworkorders_ds.write();
                    fcmworkorders_ds.refresh();
                }
            }
            catch(exception::Error)
            {
                info("Error on workflow activation.");
            }
        }
    }
```
