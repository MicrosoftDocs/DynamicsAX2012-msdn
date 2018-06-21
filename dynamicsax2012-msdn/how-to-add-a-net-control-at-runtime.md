---
title: 'How to: Add a .NET Control at Runtime'
TOCTitle: 'How to: Add a .NET Control at Runtime'
ms:assetid: 6acfd7fb-17bc-4efd-ad48-9cbd9b9b14f2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg840966(v=AX.60)
ms:contentKeyID: 35244791
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a .NET Control at Runtime [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to use X++ code to add a Windows Form or Windows Presentation Foundation (WPF) control to a Microsoft Dynamics AX form. To add a .NET control at runtime, you add X++ to the methods of the form that configure the control, display the control on the form, and handle events from the control.

## Using X++ to add a .NET control to a form

The first procedure shows how to programmatically add a ManagedHost and a .NET control.

The second procedure shows how to add the event handler method to the form that handles events that orginate in the .NET control. To help illustrate how you add a .NET control, each procedure includes code samples that show how to add a WPF button to a form.

### To add the .NET control when the form opens

1.  Before you add a control, verify that the AOT includes a reference to the .NET assembly that contains the .NET control. To verify a reference, click **Reference** in the AOT and search the list of assemblies for the assembly that includes the control.
    

    > [!TIP]
    > <P>If you do not find the specified assembly, you might have to add a <STRONG>Reference</STRONG> in the AOT to a .NET assembly. For information about how to add a <STRONG>Reference</STRONG>, see <A href="how-to-add-a-reference-to-a-net-assembly.md">How to: Add a Reference to a .NET Assembly</A>.</P>

    
    To view the properties of the **Reference** that appears in the AOT, right-click the assembly name, and then click **Properties**. The **Properties** window opens.
    
    The following table specifies the property values that you need when you add a .NET control.
    
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
    <td><p><strong>AssembyName</strong></p></td>
    <td><p>The name of the .NET assembly. For example, <strong>PresentationFramework</strong> is the name of the .NET assembly that includes many WPF controls.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Version</strong></p></td>
    <td><p>The version number of the .NET assembly. For example, <strong>3.0.0.0</strong> is the version number of the <strong>PresentationFramework</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Culture</strong></p></td>
    <td><p>The culture associated with the .NET assembly. If no value is provided, use <strong>neutral</strong> for the culture property.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>PublicKeyToken</strong></p></td>
    <td><p>The public key token is a value that uniquely identifies a signed .NET assembly. For example, <strong>31bf3856ad364e35</strong> is the <strong>PublicKeyToken</strong> of the <strong>PresentationFramework</strong> assembly.</p></td>
    </tr>
    </tbody>
    </table>


2.  In the AOT, expand the **Forms** node, and then expand the form where you want to add the .NET control. Expand the **Methods** node, and then locate the **init** method. The **init** method runs every time that the form opens. If the form does not include a method named **init**, right-click **Methods**, click **Override Method**, and then click **init**.

3.  To modify the **init** method, double-click the method in the AOT. The code editor opens. Add X++ code that specifies the .NET control you want to add to the form.
    
    The following code sample shows how to add a WPF button control from the **PresentationFramework** assembly. Notice how the declaration of the button control uses the fully qualified name of that control. Also notice how the ManagedHost control is declared.
    
        public void init()
        {
           FormManagedHostControl managedHostControl;
           System.Windows.Controls.Button myButton;
        
           super();
        }

4.  Get an instance of the ManagedHost control. To get the ManagedHost instance, add X++ code that runs after the call to super() in the **init** method.
    
    The following code sample uses the **design** and **addControl** methods of the form to obtain an instance of the ManagedHost control. Notice how the parameters of the **addControl** method specify the type, and name properties of the ManagedHost control. In addition, the sample assigns the instance to the variable that was declared earlier.
    
        managedHostControl = this.design().addControl(FormControlType::ManagedHost, “ManagedButton”);

5.  Use the instance of the ManagedHost to populate the required properties of that control. Use the assemblyName and typeName properties to associate the .NET control with the ManagedHost control. Use the sizing property to specify the size of the ManagedHost control.
    
    The following code sample populates the assemblyName, sizing, and typeName properties. Notice how the values from the AOT **Reference** for the **PresentationFramework** assembly populate the assemblyName property of the ManagedHost control. Also, notice how the typeName property specifies the fully qualified typename of a WPF button control. Finally, the sizing property instructs the ManagedHost to match the display size of the WPF button control.
    
        managedHostControl.assemblyName(“PresentationFramework, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35”);
        managedHostControl.typeName(“System.Windows.Controls.Button”);
        managedHostControl.sizing(Sizing::SizeToContent);

6.  Use the ManagedHost to obtain an instance of the .NET control. Use the instance of the .NET control to set property values of the .NET control.
    
    The following code sample retrieves the WPF button control from the ManagedHost control and sets values for the Tooltip and Content properties of the button.
    

    > [!IMPORTANT]
    > <P>While the code sample uses simple text messages, you should use labels to populate the text values of any properties that are displayed by the form. The use of labels lets you more easily localize the form.</P>

    
        myButton = managedHostControl.control();
        myButton.set_ToolTip(“Press button to view the current time”);
        myButton.set_Content(“Time”);

7.  If you have made changes that affect the size or content of the .NET control, update the control.
    
    The following code sample uses the **UpdateLayout** method of the WPF button to reflect the changes that you made to the **Tooltip** and **Content** properties.
    
        myButton.UpdateLayout();

8.  Add an event handler for each .NET control event that the form supports. Use the ManagedEventHandler class to register the .NET control event with a form method.
    
    The following code sample shows how to register an event handler for a WPF button. Notice how the parameters of the ManagedEventHandler specify the form and the name of the X++ event handler method.
    
        myButton.add_Click(new ManagedEventHandler(this, “MyButton_Click”));
    

    > [!TIP]
    > <P>Make a note of the name that you provide for the event handler. You have to add a method to the form that matches the event handler name. In the procedure that follows in the next section, you will add a method named MyButton_Click.</P>



9.  To validate and save your code, click the **Compile** button of the code editor window.

### To add the event handler method

1.  To create the event handler method, click the **New** button in the code editor. Change the method name to match the event handler name that you previously specified as a parameter for the ManagedEventHandler class. In addition, add the standard event parameters.
    

    > [!WARNING]
    > <P>You must use System.Object sender and System.EventArgs args as parameters for the event handler method. If you do not include these parameters or add other parameters, the event handler will not run.</P>

    
    The following code sample adds a form method that runs when the WPF button is clicked. Notice how the method name MyButton\_Click matches the event handler name that was used in the previous section of the documentation. Also, notice how the standard Object and EventArgs parameters are added to the method.
    
        public void MyButton_Click(System.Object sender, System.EventArgs args)
        {
        }

2.  Add X++ code to the event handler method that responds to the specified .NET control event.
    
    The following code displays a window that specifies the current system time.
    
        Box::info(“The current time: “ + time2Str(timeNow(), TimeSeparator::Colon, TimeFormat::AMPM), “Current Time”);

3.  To validate and save your code, click the **Compile** button of the code editor window. When you open the form, the new control should be visible and should perform the specified actions.

## See also

[.NET Control Overview](net-control-overview.md)

[How to: Add a .NET Control to a Form](how-to-add-a-net-control-to-a-form.md)

[How to: Add a Reference to a .NET Assembly](how-to-add-a-reference-to-a-net-assembly.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

