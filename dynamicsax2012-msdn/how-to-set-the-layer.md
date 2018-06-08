---
title: 'How to: Set the Layer'
TOCTitle: 'How to: Set the Layer'
ms:assetid: 7232ab25-1fd6-4ac3-a644-f0369fb198a0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa673975(v=AX.60)
ms:contentKeyID: 35245846
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Set the Layer 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The default current layer that is used by Microsoft Dynamics AX is set during the client installation. By default, the current layer is set to USR. This topic describes how to change the current layer from USR to another layer when Microsoft Dynamics AX is started.

To change the current layer:

1.  Click **Start**, point to **Control Panel**, point to **Administrative Tools**, and then click Microsoft Dynamics AX 2012  **Configuration**. The Microsoft Dynamics AX  **Configuration Utility** opens.

2.  In the Microsoft Dynamics AX  **Configuration Utility**, click **Manage**, and then click **Create configuration**. The **Create Configuration** window opens.

3.  In the **Configuration name** field, enter a name for the configuration, and then click **OK**. The **Create Configuration** window closes.

4.  On the **Developer** tab, in the **Application object layer to open** field, select a new layer from the drop-down list.

5.  Click **OK** to save the configuration. The Microsoft Dynamics AX  **Configuration Utility** window closes.

6.  Close and restart the client in the new layer.

For information about how to set the current model, see [How to: Specify the Current Model](how-to-specify-the-current-model.md).

## See also

[Layers](layers.md)

[How to: Set the Layer View for Elements](how-to-set-the-layer-view-for-elements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

