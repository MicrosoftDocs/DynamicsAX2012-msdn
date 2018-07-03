---
title: 'How to: Enable Workflow Submission'
TOCTitle: 'How to: Enable Workflow Submission'
ms:assetid: 5c85db91-af09-45b9-b2bb-0ac4c37b4b6d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh330384(v=AX.60)
ms:contentKeyID: 36806197
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Enable Workflow Submission 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The main table that stores the documents controlled by the workflow must have a canSubmitToWorkflow method. This method runs before the **Submit** button is enabled to verify that the workflow document is in a valid state to submit to workflow. When this method returns true, the **Submit** button is enabled.

## How to: Enable Workflow Submission

The canSubmitToWorkflow method for a table controls whether a document in the table can be submitted to workflow.

### To create a canSubmitToWorkflow method on a table

1.  In the AOT, expand the table that you want to create a canSubmitToWorkflow method for.

2.  Right-click the **Method** node, point to **Override Method**, and then click **canSubmitToWorkflow**.

3.  A method node named **canSubmitToWorkflow** displays under the **Methods** node and the **Editor** window opens.

4.  In the **Editor** window, enter code to examine the current record and determine whether to enable the display of the **Submit** button. For example, the following code is the canSubmitToWorkflow method for the work order approval workflow. It examines the workflow state for the current record. If it is in the NotSubmitted state, the Submit button is enabled.
    ```X++  
        public boolean canSubmitToWorkflow(str _workflowType = '')
        {
            boolean ret;
        
            if (_workflowType == workFlowTypeStr(FCMWorkOrderApproval))
            {
                if(this.WorkflowState== FCMWorkOrderWorkflowState::NotSubmitted)
                {
                    ret = true;
                }
            }
            else
            {
                ret = super(_workflowType);
            }
        
            return ret;
        }
    ```
5.  Close the **Editor** window and then click **Yes** to save changes.

## See also

[Requirements for Enabling Workflow in an Application Module](requirements-for-enabling-workflow-in-an-application-module.md)

[How to: Enable a State Model for a Workflow Document](how-to-enable-a-state-model-for-a-workflow-document.md)

[How to: Enable a Form or List for Workflow](how-to-enable-a-form-or-list-for-workflow.md)

[How to: Create a Workflow Document Class](how-to-create-a-workflow-document-class.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

