---
title: .NET Control Overview
TOCTitle: .NET Control Overview
ms:assetid: e10ff1fb-aeb7-423b-adcb-938cca8dce3e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg864879(v=AX.60)
ms:contentKeyID: 35253078
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# .NET Control Overview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic provides information about the components you use to add a Windows Form Control or a Windows Presentation Foundation (WPF) control to a Microsoft Dynamics AX form. These types of controls are generically referred to as just .NET controls. When you add a .NET control to a form, you also add a Microsoft Dynamics AX ManagedHost control to that form.

## ManagedHost Control

The ManagedHost is a Microsoft Dynamics AX control that hosts a .NET control on a form. The ManagedHost supports access to the properties, methods, and events of the specified .NET control. To provide access to these members of the .NET control, the ManagedHost uses the CLR interop feature of X++. For information about CLR interop, see [.NET Interop from X++](net-interop-from-x.md). If you add more than one .NET control to a form, you also add a separate ManagedHost control for each .NET control.

The use of CLR interop is important because it supports the implicit conversion of several X++ data types to the corresponding .NET CLR data types. Implicit conversion simplifies how you set property, and parameter values, and view return values from many .NET controls. For more information about implicit conversions, see [How to: Marshal Between X++ and CLR Primitive Types](how-to-marshal-between-x-and-clr-primitive-types.md). If the .NET control uses a more complex type like an array or enumeration, you might have to perform some conversion work. For an example of how to use X++ and .NET arrays, see [How to: Use X++ Syntax for CLR Arrays](how-to-use-x-syntax-for-clr-arrays.md).

## .NET Control

A .NET control is a component that was developed by using the .NET Framework and executes in the managed environment of the .NET Common Language Runtime (CLR). A typical .NET control encapsulates user interface functionality for a client-side Windows-based application. The following table lists the types of .NET controls.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Form Control</p></td>
<td><p>A control from the <strong>System.Windows.Forms</strong> namespace or any control that derives from the Windows Control class or UserControl class. The ManagedHost control supports the use of a Windows Form Control.</p></td>
</tr>
<tr class="even">
<td><p>Windows Presentation Foundation (WPF) Control</p></td>
<td><p>A control from the <strong>System.Windows.Controls</strong> namespace or any control constructed and hosted using the WPF framework. The ManagedHost control supports the use of a WPF control.</p></td>
</tr>
</tbody>
</table>


The ability to add a .NET control to a form gives you access to many controls that support data or activities that existing Microsoft Dynamics AX controls do not easily support. In addition, you can create or customize .NET controls that add specific types of functionality to the form. The SDK for the .NET Famework provides information about how to create or customize Windows Form controls and WPF controls.


> [!IMPORTANT]
> <P>Microsoft Dynamics AX does not support the use of a Microsoft Silverlight™ control on a form. While Silverlight includes a collection of controls for user interface (UI) development, the ManagedHost does not support the Silverlight framework and runtime.</P>



The following list specifies the ways you can add a .NET control to a form:

  - Add and configure the .NET control in the AOT by using the **Design** node of the form. For information about how to use the **Design** node of the form to add a .NET control, see [How to: Add a .NET Control to a Form](how-to-add-a-net-control-to-a-form.md).

  - Add X++ to a form method that dynamically adds and configures the.NET controls. For information about how to use X++ to add a .NET control to a form, see [How to: Add a .NET Control at Runtime](how-to-add-a-net-control-at-runtime.md).


> [!WARNING]
> <P>You cannot add a .NET control to a grid on an AX form.</P>



### ![Gg864879.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg864879.collapse_all(en-us,AX.60).gif")Properties

To add a .NET control to a form, you use the following properties:

  - You use the properties of the .NET control to configure that control or to obtain information from the control. To set a property value, assign a value to the set\_\<property name\> property of the .NET control. To retrieve a value from a .NET control, use the get\_\<property name\> property of the .NET control.

  - You might also have to set the properties of the ManagedHost control.
    
    For example, you use properties of the ManagedHost to specify the .NET control and identify the assembly that contains the control. In addition, you can use the properties of the ManagedHost to configure how the .NET control appears on the form.

To set or retrieve the property values of the .NET control, add X++ code to one or more form methods.

For example, use the **init** method of the form to set the initial value of the properties of the .NET control. The **init** method runs every time that the form opens and sets the .NET control to a default configuration.

### ![Gg864879.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg864879.collapse_all(en-us,AX.60).gif")Methods

To use a hosted .NET control to perform actions, you use the following methods:

  - You call a .NET control method when you want to have the .NET control perform a specific action. Typically, you add X++ to a form method that calls the .NET control method and evaluates the return value.

  - You might also have to call the methods of the ManagedHost control.
    
    For example, you can use the **control** method of the ManagedHost to obtain an instance of the hosted .NET control. You then use the instance of the .NET control to set properties, call methods, and register events.

For example, you add a WPF button control to a form. To access the button control, you use the **control** method of the ManagedHost control to obtain an instance of the WPF button control. You then use that control instance to call a method of the button control. As an example, you might use the **UpdateLayout** method of a button control after you make property changes that affect the appearance of that button.

### ![Gg864879.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg864879.collapse_all(en-us,AX.60).gif")Events

To integrate the actions of a .NET control with a Microsoft Dynamics AX form, you add event handlers to the form. An event handler is a registered form method that runs every time that the .NET control performs a specified event. To register an event handler, use the following methods and classes:

  - An event handler requires a form method. Typically, you add a new method to the form that serves as the event handler for the .NET control event.

  - To identify the form method as an event handler, you use the ManagedEventHandler class. The ManagedEventHandler requires that you specify the form and the name of the method.

  - To register a form method as an event handler, supply your ManagedEventHandler as a parameter to the add\_\<event name\> method of the .NET control. To access the add\_\<event name\>methods of the .NET control, you might have to use the ManagedHost control to obtain an instance of the .NET control.

  - To perform actions when the .NET control event occurs, add X++ code to the form method that you registered as the event handler. The code in this method will run every time that the specified event occurs


> [!NOTE]
> <P>If there is more than one registered event handler for a .NET control event, there is no specified order of execution. You should not assume one event handler will always complete before another starts.</P>



Typically, you use the form **Design** node in the AOT to add event handlers at the same time that you add the ManagedHost and .NET control to the form. When you use the AOT, the event handler registration is automatically added to the **init** method of the form. In addition, the method for the event handler is automatically added to the form. To complete the event handler, open the method and add X++ code that performs the actions for that event.

You can also use X++ to dynamically register an event handler. Typically, you use X++ to register an event handler when you use X++ to add the .NET control to a form. You can also use X++ to remove an event handler. To unregister an event handler, use the remove\_\<event name\> method of the .NET control.

### ![Gg864879.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg864879.collapse_all(en-us,AX.60).gif")Exception handling

When you assign values to a property or call a method on the .NET control, you might encounter an exception from the .NET control. CLR interop lets you handle exceptions originated by the .NET control by using standard X++ exception handling techniques. For information about how to handle exceptions, see [Exception Handling with try and catch Keywords](exception-handling-with-try-and-catch-keywords.md).

## .NET Assembly

To use a .NET control with a Microsoft Dynamics AX form, you must have a reference in the AOT to the .NET assembly that contains the control. The **Reference** node of the AOT lists the assemblies that are currently available. To add new .NET controls, add the assembly or assemblies that contain the controls to the AOT **Reference** node. For information about how to add reference, see [How to: Add a Reference to a .NET Assembly](how-to-add-a-reference-to-a-net-assembly.md).

To use a .NET control, the .NET assembly that contains the control must be installed on each client computer that will use the form. If you add a reference to an assembly that contains a custom control in a new assembly, you have to install that assembly on each client computer. In addition, the assembly must be signed. For more information about how to add assemblies to the Application Object Server (AOS) and each client computer, see [How to: Compile and Run X++ that Calls CLR Managed Assemblies](how-to-compile-and-run-x-that-calls-clr-managed-assemblies.md).

## See also

[How to: Add a .NET Control to a Form](how-to-add-a-net-control-to-a-form.md)

[How to: Add a .NET Control at Runtime](how-to-add-a-net-control-at-runtime.md)

[ActiveX Controls](activex-controls.md)

[Form Control Properties](form-control-properties.md)

[Methods on Form Controls](methods-on-form-controls.md)

[Form Control Classes](form-control-classes.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

