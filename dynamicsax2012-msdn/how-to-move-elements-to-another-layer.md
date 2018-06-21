---
title: 'How to: Move Elements to Another Layer'
TOCTitle: 'How to: Move Elements to Another Layer'
ms:assetid: fb6cc3fc-2897-4778-9829-f20f3d306ba7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa892084(v=AX.60)
ms:contentKeyID: 35254196
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Move Elements to Another Layer [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you might need to move elements from one layer to another.

### To move elements to another layer

1.  Right-click the elements that you want to move to another layer, and then click **Export**. For more information, see [How to: Export Application Objects by Using the AOT](how-to-export-application-objects-by-using-the-aot.md).

2.  Use the Application Object Tree (AOT) to delete the elements that you want to move.
    

    > [!WARNING]
    > <P>When you delete a table, all data in the table and ID references are lost. For information about exporting and importing data, see <A href="https://msdn.microsoft.com/en-us/library/aa834437(v=ax.60)">Data import, export and migration</A>.</P>



3.  Close Microsoft Dynamics AX.

4.  Restart Microsoft Dynamics AX in the layer to which you want to move the elements. For information about changing the current layer, see [How to: Set the Layer](how-to-set-the-layer.md).

5.  Import the .xpo file that contains the elements you want to move. For more information, see [How to: Import Application Objects by Using the AOT](how-to-import-application-objects-by-using-the-aot.md).

## See also

[Layers](layers.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

