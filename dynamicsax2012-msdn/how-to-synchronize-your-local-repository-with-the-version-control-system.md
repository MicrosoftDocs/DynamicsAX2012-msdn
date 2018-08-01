---
title: 'How to: Synchronize Your Local Repository with the Version Control System'
TOCTitle: 'How to: Synchronize Your Local Repository with the Version Control System'
ms:assetid: c5e31557-4794-459c-80fb-16934ca961ad
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa866044(v=AX.60)
ms:contentKeyID: 35268168
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Synchronize Your Local Repository with the Version Control System [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Synchronization enables you to update elements in your local repository folder so that they match the latest versions in the version control system.

Synchronize elements with the latest version of elements in the version control system in the following ways:

  - To synchronize a single element, right-click the element in the Application Object Tree (AOT), and then click **Get Latest**.
    

    > [!NOTE]
    > <P>If you use Microsoft Visual SourceSafe for version control, you can click <STRONG>Get Latest</STRONG> or <STRONG>Get by Label</STRONG>.</P>



  - To synchronize all elements, click **Version control** \> **Synchronize**.

Synchronization does not affect any new elements you have created or any elements you have checked out.

If a Version Control System (VCS) client that runs against the VCS server uses the same local repository folder as a Microsoft Dynamics AX client, there are some things for you to consider. If you check in changes by using the VCS client, the Microsoft Dynamics AX client will not reflect the changes because the .xpo file in the shared local repository will be up to date. To reflect the changes in the Microsoft Dynamics AX client, you must select **Force** when you synchronize the Microsoft Dynamics AX client.

If you enable version control or synchronize a new model on a layer that is not the layer the model belongs to in the VCS, the model will be created in the layer that is specified in the model.xml file. If no layer is specified in the model.xml file, the current layer is used.


> [!NOTE]
> <P>Synchronization is not supported by the MorphX version control system.</P>



## Synchronization Log

If there is a problem during synchronization (for example, if you are disconnected from the network), you can view the progress of each file in the Synchronization log. To access this log, click **Version control** \> **Synchronization log**.

If an item has not been fully synchronized, the **Processed** check box for the item is cleared. For example, an element might have been downloaded to your computer but not integrated into the AOT. To complete the synchronization for the element, click **Process**.

## See also

Synchronization Form

[Version Control System](version-control-system.md)

[How to: Create a Repository](how-to-create-a-repository.md)

