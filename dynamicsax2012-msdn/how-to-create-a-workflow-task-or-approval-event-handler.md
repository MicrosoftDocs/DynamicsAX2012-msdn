---
title: 'How to: Create a Workflow Task or Approval Event Handler'
TOCTitle: 'How to: Create a Workflow Task or Approval Event Handler'
ms:assetid: f32f896f-78a2-4d14-b160-d252fe56e612
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc623606(v=AX.60)
ms:contentKeyID: 35253429
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Workflow Task or Approval Event Handler 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The event handlers for a Microsoft Dynamics AX workflow are provided on a workflow and workflow element level. This topic describes how to create and implement event handlers on the workflow element level. For more information about workflow event handlers, see [How to: Create a Workflow Event Handler](how-to-create-a-workflow-event-handler.md).

Workflow element event handlers provide notification of events that occur during execution of individual workflow elements, for example, when a task, automated task, or approval starts. For description of the workflow element level event handlers available in Microsoft Dynamics AX, see [Workflow Events Overview](workflow-events-overview.md).

Typically, the class and methods for a workflow element event handler are created by the **Workflow wizard** when you create a new workflow approval or workflow task. You just need to supply the code for each event. Use the following procedure if you need to create the workflow element event handler manually.

### To create event handlers for an approval

1.  In the AOT, expand the **Classes** node.

2.  Right-click the **Classes** node, and then select **New Class**. A new class group displays under the **Classes** node.

3.  Right-click the new class, click **Rename**, and enter a name for the class.

4.  Expand the new class, select **classDeclaration**, right-click the class declaration and then click **Edit**.

5.  Enter code similar to the following in the class declaration. Include only the event handlers that you are going to implement.
    
       ```X++
       public class <event handler class name> implements
            WorkflowElementCompletedEventhandler,
            WorkflowElementCanceledEventHandler,
            WorkflowElementReturnedEventHandler,
            WorkflowElemChangeRequestedEventHandler,
            WorkflowElementStartedEventHandler
        {
        }
       ```

6.  Right-click the new class and then click **New Method**. A new method node displays under the **Classes** node.

7.  Right-click the new method and then click **Edit**. Enter the following code for the started event method.
    
       ```X++
       public void started(WorkflowElementEventArgs _workflowElementEventArgs)
        {
            <insert method here>
        }
       ```

8.  Repeat steps 6 and 7 for the remaining events that you are going to implement.

9.  Right-click the node for the new class and select **Save**.

10. To compile your application, in the AOT, right-click **AOT**, select **Add-Ins**, and then select **Incremental CIL generation from X++**.

## Example

The following code example shows a basic implementation of a workflow element event handler for the started event in a workflow that tracks issues. The class declaration is shown first, followed by the implementation of the started method. The IssueStateChangeManager.start method updates the workflow state to Started based on the RecId parameter passed in by the workflowContext variable. For more information, see [WorkflowEventArgs Class](https://msdn.microsoft.com/en-us/library/gg831514\(v=ax.60\)) and [WorkflowContext Class](https://msdn.microsoft.com/en-us/library/gg798325\(v=ax.60\)).

   ```X++
   // Class Declaration
    public class IssueWorkflowEventHandler implements
        WorkflowElementStartedEventHandler
    {
    }
    // WorkflowStarted method
    public void started(WorkflowElementEventArgs _workflowElementEventArgs)
    {
        // This is the variable declaration.
        WorkflowContext workflowContext;
     
        // Gets the workflow context from _workflowElementEventArgs.
        workflowContext = _workflowElementEventArgs.parmWorkflowContext();
     
        // Sets the workflow state to Started.
        IssueStateChangeManager::start(workflowContext.parmRecId());
    }
   ```

You can implement the remaining workflow element event handlers by using the same code syntax shown earlier.

## See also

[Workflow Events Overview](workflow-events-overview.md)

[How to: Create a Workflow Event Handler](how-to-create-a-workflow-event-handler.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

