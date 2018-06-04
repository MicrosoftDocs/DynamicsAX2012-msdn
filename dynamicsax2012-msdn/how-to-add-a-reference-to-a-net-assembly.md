---
title: 'How to: Add a Reference to a .NET Assembly'
TOCTitle: 'How to: Add a Reference to a .NET Assembly'
ms:assetid: d39b1e33-cc7f-4bca-bce7-370c4ec23559
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg881320(v=AX.60)
ms:contentKeyID: 35251966
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a Reference to a .NET Assembly 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to add a .NET assembly that contains a Windows Form or Windows Presentation Foundation (WPF) control to the **References** node of the Application Object Tree (AOT). To use a control from a .NET assembly on a Microsoft Dynamics AX form, the .NET assembly must be in the **References** node list of assemblies. You use these procedures when you want to add an assembly to the **References** node of the AOT. Typically, the **References** node includes assemblies that contain many Windows Form and WPF controls. However, you might have to add an assembly when one of the following events occurs:

  - You create or obtain an assembly that contains a .NET control that you want to add to a form.

  - While adding a .NET control to a form, you find that the assembly that contains the .NET control is not in the list of referenced assemblies.

## Adding an Assembly to the References Node of the AOT

The following procedure shows how to add a .NET assembly to the **References** node of the AOT. Use these steps when you create or obtain an assembly that contains a .NET control you want to add to a form. For information about how to add a .NET assembly to the Application Object Server (AOS), see [How to: Compile and Run X++ that Calls CLR Managed Assemblies](how-to-compile-and-run-x-that-calls-clr-managed-assemblies.md).

### To use the Add Reference window

1.  In the AOT, right-click **References**, and then click **Add reference**. The **Add reference** window opens. Review the top list to locate the assembly that contains the control you want to use. Click the assembly name and then click the **Select** button. The specified assembly is added to the bottom list of assemblies.

2.  If the assembly that contains the control you want to use is not included in the top list, click the **Browse** button, open the folder that contains the assembly, click the assembly, and then click the **Open** button. The assembly is added to the bottom list of assemblies in the **Add reference** window.

3.  To add a reference to the assembly or assemblies shown in the bottom list of the **Add reference** window, click **OK**. The **Add reference** window closes. The specified assembly or assemblies are added to the list of assemblies in the **References** node of the AOT.

## Adding an Assembly from the Managed Control Selector

The following procedure shows how to add a reference to an assembly from the **Managed Control Selector** window. Typically, you follow these steps when a .NET control that you want to add to a form is not included in the list of assemblies in the **Managed Control Selector**. For information about how to use the **Managed Control Selector**, see [How to: Add a .NET Control to a Form](how-to-add-a-net-control-to-a-form.md).

### To add a reference from the Managed Control Selector

1.  In the AOT, expand the **Forms** node. Find and expand the form where you will add the .NET control.

2.  Expand **Designs**. Right-click **Design**, click **New Control**, and then click **ManagedHost**. The **Managed Control Selector** opens.

3.  To add an assembly, click the **Add Reference** button. The **Add reference** window opens. Review the top list to locate the assembly that contains the control you want to use. Click the assembly name and then click the **Select** button. The specified assembly is added to the bottom list of assemblies.

4.  If the assembly that contains the control you want to use is not included in the top list, click the **Browse** button, open the folder that contains the assembly, click the assembly, and then click the **Open** button. The assembly is added to the bottom list of assemblies in the **Add reference** window.

5.  To add a reference to the assembly or assemblies listed in the bottom list of the **Add reference** window, click **OK**. The **Add reference** window closes. The specified assembly or assemblies are added to the list of assemblies in the **Managed Control Selector**.

## See also

[How to: Add a .NET Control to a Form](how-to-add-a-net-control-to-a-form.md)

[How to: Add a .NET Control at Runtime](how-to-add-a-net-control-at-runtime.md)

[How to: Compile and Run X++ that Calls CLR Managed Assemblies](how-to-compile-and-run-x-that-calls-clr-managed-assemblies.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

