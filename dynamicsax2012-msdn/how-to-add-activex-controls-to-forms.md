---
title: 'How to: Add ActiveX Controls to Forms'
TOCTitle: 'How to: Add ActiveX Controls to Forms'
ms:assetid: 0451cc66-647e-47a0-99ec-400958a80b6a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa551694(v=AX.60)
ms:contentKeyID: 35240250
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add ActiveX Controls to Forms [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can insert an ActiveX control in a form in Microsoft Dynamics AX by using the Application Object Tree (AOT), as you would for any other type of control.


> [!NOTE]
> <P>ActiveX controls can be security threats. Note the following security issues:</P>
> <P>ActiveX controls run in the same security context as the Microsoft Dynamics AX Client.</P>
> <P>ActiveX controls that are used by Microsoft Dynamics AX should not be marked as safe for scripting.</P>
> <P>If an ActiveX control in Microsoft Dynamics AX has a method with a signature and a name that are equal to a public method that is exposed by the ActiveX control, the X++ method is always called when it is referenced from X++ code.</P>
> <P>For more information about ActiveX and security, see http://msdn.microsoft.com/workshop/components/activex/sec_activex.asp.</P>



## Add an ActiveX Control to a Form

1.  Right-click the **Design** node for the form, and then select **New Control**.

2.  Select **ActiveX** from the submenu.

3.  Choose the control that you want to insert, for example, the **Microsoft Calendar** control (mscal.ocx, part of Microsoft Office), which is shown in the following figure.
    
    ![Microsoft Calendar control](images/Aa551694.formcal(en-us,AX.60).gif "Microsoft Calendar control")
    
    **Calendar control**

4.  Right-click the ActiveX control in the AOT, and start the **ActiveX Explorer** (to communicate with the control). The following figure shows the **ActiveX Explorer**.
    
    ![ActiveX Explorer](images/Aa551694.formExpl(en-us,AX.60).gif "ActiveX Explorer")
    
    **ActiveX Explorer**
    
    The ActiveX Explorer displays a list of all the events that can be started by the ActiveX control, and a list of all the methods that can be executed on the control. The list of methods is read from the object's type library, which provides information about how to call the methods. The list of events is also retrieved from the object's type library. Before Microsoft Dynamics AX can handle any of the events that the ActiveX control can start, however, you need to add event handlers (methods) for them.
    

    > [!NOTE]
    > <P>If a method name is more than 40 characters, Microsoft Dynamics AX truncates the name after 31 characters and appends it with a unique number.</P>



5.  Select the events that you want your form to handle, and then click the **Add Event Handler** button.
    
    This creates a number of methods. By adding X++ code to these event handler methods, you can control how Microsoft Dynamics AX reacts to specific events.
    
    Most ActiveX controls offer specific ActiveX properties. You can set them from your X++ code. The **Methods** tab page of the ActiveX Explorer shows the available property methods that the ActiveX control provides for modifying properties as well as other ActiveX-specific methods. For example, the Microsoft Calendar control offers a Day property method. It is used to set and get the day that is selected in the ActiveX control.

## See and Set ActiveX Properties

1.  Open the visual form designer.

2.  Right-click the form's **Design** node to open a shortcut menu.

3.  Select **Edit**, or double-click the form's **Design** node.

4.  Right-click the ActiveX control, and then click **Properties** on the shortcut menu.

5.  Click the **Custom** property's lookup button to access the ActiveX control's properties. The following figure shows the **Calendar Properties** property sheet.
    
    ![Active X Form example](images/Aa551694.FormActiveXProp(en-us,AX.60).gif "Active X Form example")
    
    **ActiveX control properties**

## See also

[Forms Best Practices](forms-best-practices.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

