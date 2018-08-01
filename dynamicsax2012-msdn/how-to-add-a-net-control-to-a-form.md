---
title: 'How to: Add a .NET Control to a Form'
TOCTitle: 'How to: Add a .NET Control to a Form'
ms:assetid: 4bd4db98-5e20-4c4e-b94b-7b6d7b093b07
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg840386(v=AX.60)
ms:contentKeyID: 35243382
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a .NET Control to a Form [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you want to add a .NET control to a form that you are designing in the AOT, follow the procedures in this topic. The procedures describe how to add a Windows Form or Windows Presentation Foundation (WPF) control to a Microsoft Dynamics AX form.

## Adding a .NET Control

This section of the documentation describes how to add a .NET control to the design of a form. When you add a .NET control to a form, you typically complete the following tasks:

  - Open the AOT and use the **Design** node of the form to add a ManagedHost control to that form.

  - Use form methods to initialize the .NET control and respond to events that originate with the .NET control.

To help illustrate how you add a .NET control to a form, the following procedures include example property values and code samples that add a LinkLabel control from the .NET System.Windows.Forms assembly.


> [!TIP]
> <P>Before you add a .NET control, you must know the .NET assembly and namespace of that control.</P>



### To add the .NET control

1.  In the AOT, expand the **Forms** node. Find and expand the form where you will add the .NET control.

2.  Expand **Designs**. Right-click **Design**, click **New Control**, and then click **ManagedHost**. The **Managed Control Selector** opens.

3.  Use the top list to find the assembly that contains the control you want to add. Notice that when you click a name in the top list, the botton list changes to show the controls that are contained in that assembly.
    
    For example, find and then click System.Windows.Forms in the top list. The bottom list shows the controls that are contained in that assembly together with the namespace of the control.
    
    To add a control, click the control name in the bottom list and then click **OK**.
    
    For example, click **LinkLabel** and then click **OK**. The **Managed Control Selector** closes.
    

    > [!TIP]
    > <P>If you cannot find the namespace or control, you might have to add a reference to the assembly that contains the specified control. For information about how to add a reference from the <STRONG>Managed Control Selector</STRONG>, see <A href="how-to-add-a-reference-to-a-net-assembly.md">How to: Add a Reference to a .NET Assembly</A>.</P>



4.  The AOT adds the **ManagedHost** control to the **Design** node of the form. Right-click **ManagedHost** and then click **Properties**. The **Properties** window lists the **ManagedHost** properties and the default value of each property.

5.  Review the list of properties. You customize the **ManagedHost** control by replacing the default property values with a new value. The following table specifies the properties that are required to initialize a ManagedHost control.
    
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
    <td><p>The default property value is <strong>ManagedHost</strong>. Use this property to uniquely identify the control. For example, enter <strong>LinkLabelManagedHost</strong> for a .NET LinkLabel control</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>AutoDeclaration</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>TypeName</strong></p></td>
    <td><p>Displays the fully qualified name of the .NET control. For example, a .NET LinkLabel control is identified as <strong>System.Windows.Forms.LinkLabel</strong>. The property value is automatically populated when you add the .NET control by using the <strong>Managed Control Selector</strong>. Typically, you would not change the default value. However, you can update this property if you have to reflect a change to the name of the .NET control.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>AssemblyName</strong></p></td>
    <td><p>Displays the name of the assembly that contains the specified control. The property value is automatically populated when you add the .NET control by using the <strong>Managed Control Selector</strong> and cannot be changed.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Sizing</strong></p></td>
    <td><p>Specifies how the .NET control appears on the form. If you use the <strong>Height</strong> and <strong>Width</strong> properties to specify the size of the ManagedHost, use <strong>SizeToHost</strong> to fill the ManagedHost with the specified .NET control. If you want the ManagedHost to match the size of the .NET control, set the property value to <strong>SizeToContent</strong>. For example, use <strong>SizeToContent</strong> with a .NET LinkLabel control.</p></td>
    </tr>
    </tbody>
    </table>


The .NET and ManagedHost control are added to the form. To integrate the .NET control with the form, complete the steps in the following procedure.

### To intialize the .NET control and add eventhandlers

1.  In the AOT, expand the form where you added the ManagedHost control. Expand the **Designs** and **Design** nodes, right-click the **ManagedHost** control, and then click **Events**. The **Events** window opens.

2.  Use the list of **Events** to identify the .NET control event or events where you want the form to perform an action based on that event. To add an event handler for an event, click the event name in the **Events** list, and then click **Add**. Notice how a method name is added to the **X++ Methods** column. When you have finished creating X++ methods for.NET control events, click **Close**.
    
    For example, create an event handler for the **LinkClicked** event of a .NET LinkLabel control by opening the **Events** list, clicking the **LinkClicked** event, clicking **Add**, and then clicking **Close**.

3.  In the AOT, expand the **Methods** node under the form. Notice that a method named **init** was added. Also notice that a method was added for each method added to the **X++ Methods** list in the **Events** window.
    
    For example, if you add an event handler for the **LinkClicked** event for the .NET LinkLabel control, you will see a form method named **LinkLabelManagedHost\_LinkClicked**.

4.  To populate the initial property values of the .NET control, double-click the **init** method. The method opens in the code editor. Use the code editor to add code that populates the required properties of the .NET control. Add your initialization code after the code that declares the control and adds the event handlers.
    
    The following code example shows how to add code to the **init** method that populates the **Text** property of a LinkLabel control named **\_LinkLabelManagedHost\_Control**. The **Text** property specifies the text message that the LinkLabel displays on the form.
    ```X++  
        public void init()
        {
           super();
        
           // The following code is automatically added to the init method. 
           // The code initializes the managed host control, and adds the specified event handlers.
           _LinkLabelManagedHost_Control = LinkLabelManagedHost.control();
           _LinkLabelManagedHost_Control.add_LinkClicked(new ManagedEventHander(this, ‘LinkLabelManagedHost_LinkClicked’));
        
           // The following code initializes the Text property of the .NET LinkLabel control.
           _LinkLabelManagedHost_Control.set_Text(“Go to MSDN”);
        }
    ```
5.  To customize the actions that occur when a .NET control event occurs, return to the AOT and double-click the name of the event handler method that was created earlier. The specified method opens in the code editor. Add code that performs actions for that event.
    
    The following code example shows the event handler method for a .NET LinkLabel control. The method opens the specified web site when the text in the control is clicked.
    ```X++  
        void ManagedHost_LinkClicked(System.Object sender, System.Windows.Forms.LinkLabelLinkClickedEventArgs e)
        {
           WINAPI::shellExecute(“iexplore.exe”, “MSDN.Microsoft.com”);
        }
    ```
6.  To validate and save your code changes, click the **Compile** button of the code editor window.

## See also

[.NET Control Overview](net-control-overview.md)

[How to: Add a .NET Control at Runtime](how-to-add-a-net-control-at-runtime.md)

[How to: Add a Reference to a .NET Assembly](how-to-add-a-reference-to-a-net-assembly.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

