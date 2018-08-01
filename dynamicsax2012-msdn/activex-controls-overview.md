---
title: ActiveX Controls Overview
TOCTitle: ActiveX Controls Overview
ms:assetid: 31083f13-859e-4f78-b468-51dcb1a68371
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa635219(v=AX.60)
ms:contentKeyID: 35241988
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ActiveX Controls Overview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

If you want the features of an ActiveX control in a Microsoft Dynamics AX form, you can use the control when you create the form.


> [!NOTE]
> <P>ActiveX controls can be security threats. Note the following security issues:</P>
> <P>ActiveX controls run in the same security context as the Microsoft Dynamics AX Client.</P>
> <P>ActiveX controls that are used by Microsoft Dynamics AX should not be marked as safe for scripting.</P>
> <P>If an ActiveX control in Microsoft Dynamics AX has a method with a signature and a name that are equal to a public method that is exposed by the ActiveX control, the X++ method is always called when it is referenced from X++ code.</P>
> <P>For more information about ActiveX controls and security, see http://msdn.microsoft.com/workshop/components/activex/sec_activex.asp.</P>



An ActiveX control is a COM object that can be used as a graphical control inside an application. ActiveX controls have a wide range of diverse functionality, and can be purchased from many vendors. The software available as ActiveX components ranges from simple components (such as check boxes and combo boxes) to larger, more complex components (such as spreadsheets, calendars, Internet browsers, and communication programs).

When you install software such as Microsoft Office or Microsoft Internet Explorer, many COM objects and ActiveX controls are added to your computer. Before a COM object can be used, it must be registered in the registry. The installation program normally completes this as part of the installation process.

For more information about adding an ActiveX control to a form, see [How to: Add ActiveX Controls to Forms](how-to-add-activex-controls-to-forms.md).

## See also

[.NET Controls](net-controls.md)

[Forms Best Practices](forms-best-practices.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

