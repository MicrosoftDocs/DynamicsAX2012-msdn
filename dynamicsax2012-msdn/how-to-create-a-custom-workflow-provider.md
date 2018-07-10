---
title: 'How to: Create a Custom Workflow Provider'
TOCTitle: 'How to: Create a Custom Workflow Provider'
ms:assetid: 9fae733b-dfe5-4ca6-a3ef-38961a272096
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc633997(v=AX.60)
ms:contentKeyID: 35248264
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Custom Workflow Provider 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, there are four workflow provider types. In some cases, the instances of these providers may not meet your application requirements. The following procedure describes the steps to implement a custom workflow provider.

You create a custom workflow provider by implementing a workflow provider interface. See [Workflow Provider Interfaces](workflow-provider-interfaces.md) for more information about the interface for each provider type. Choose the appropriate interface type for your custom provider, and implement the methods in a class using the following procedure.

### To create a custom workflow provider

1.  In the AOT, expand the **Classes** node.

2.  Right-click the **Classes** node, and then select **New Class**. A new class group displays under the **Classes** node.

3.  Expand the new class, right-click **classDeclaration**, and then click **View Code**.

4.  Enter the code in the class declaration to indicate which workflow provider interface the class is implementing. The following example shows the class declaration for a workflow provider that implements the WorkflowParticipantProvider interface.
    ```X++  
        public class <MyCustomWorkflowProviderClassName> implements WorkflowParticipantProvider
        {
        }
    ```
5.  Right-click in the **Editor** window, click **New**, and then enter the following code for one of the methods in the interface that you are implementing. For example, the following code shows the getParticipantTokens method that is part of the WorkflowParticipantProvider interface.
    ```X++  
        public WorkflowParticipantTokenList getParticipantTokens()
        {
            // Constructs the new user group list.
            WorkflowParticipantTokenList userGroups = WorkflowParticipantTokenList::construct();
        
            // ToDo Define your user groups here.
        
            return userGroups;
        }
    ```
6.  Right-click in the **Editor** window, click **New**, and then create the next method for the workflow provider interface. The following code example shows the resolve method that is part of the WorkflowParticipantProvider interface.
    ```X++  
        public WorkflowUserList resolve(WorkflowContext _context,
            WorkflowParticipantToken _participantTokenName)
        {
            // Declare the variables.
            UserGroupList userGroupList;
            WorkflowUserList userList = WorkflowUserList::construct();
            ;
            
            // Verify that the participant token is set or throw an error.
            if (!_participantTokenName)
                throw error("@SYS105453");
        
            // ToDo Enter code to add users to the user list.
           
            {
                userList.add(userGroupList.UserId);
            }
        
            return userList;
        }
    ```
7.  Continue implementing the methods for the workflow provider interface.

8.  Close the **Editor** window and then click **Yes** to save changes.

9.  In the AOT, expand the **Workflow** \> **Providers** node.

10. Right-click the node for the provider type for which you are creating a custom provider and then choose to create a new provider. For example, right-click the **ParticipantAssignment** node and then click **New Participant Assignment Provider**.

11. Right-click the node for the new customer provider and then click **Properties**.

12. Supply the following properties for the custom provider.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Name</p></td>
    <td><p>The name for the custom provider.</p></td>
    </tr>
    <tr class="even">
    <td><p>Label</p></td>
    <td><p>The label for the custom provider.</p></td>
    </tr>
    <tr class="odd">
    <td><p>HelpText</p></td>
    <td><p>A description for the custom provider.</p></td>
    </tr>
    <tr class="even">
    <td><p>AssociationType</p></td>
    <td><p>Specifies whether the workflow provider is used at the company or global level.</p></td>
    </tr>
    <tr class="odd">
    <td><p>AvailableForAllWorkflowTypes</p></td>
    <td><p>Specifies whether the workflow provider can be used for all workflow types.</p></td>
    </tr>
    <tr class="even">
    <td><p>ProviderClass</p></td>
    <td><p>The custom workflow provider class that defines the behavior of the custom provider. You created this class earlier in this procedure.</p></td>
    </tr>
    </tbody>
    </table>


13. If you set the **AvailableForAllWorkflowTypes** property to **No**, then you should specify which workflow types the custom provider can be used with. Expand the node for the custom provider.

14. Right-click the **Workflow Types** node and then click **New Workflow Type**.

15. Select the new node. In the Properties list, set the WorkflowType property to the name of the workflow type that the custom workflow provider will be used with.

16. Save the changes for the custom provider.

## See also

[Workflow Providers Overview](workflow-providers-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

