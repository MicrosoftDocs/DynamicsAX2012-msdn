---
title: Top-Layer Version of an Element
TOCTitle: Top-Layer Version of an Element
ms:assetid: e6cf6fc3-a7c0-4628-9b76-ef7a94719035
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa881527(v=AX.60)
ms:contentKeyID: 35253221
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Top-Layer Version of an Element 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, a layer system is used to manage elements. The USR layer is the top layer and the SYS layer is the bottom layer, and each layer has a corresponding patch layer above it.

You can use layering in the model store to extend a base model for localization and industry specialization. You can also use layering to support reseller and customer-specific customization.

Layers enable you to make modifications and additions without changing elements in a lower level. When you modify an element, a copy of the element with your modifications is stored in the current layer. The element on the lower layer is not affected.

For example, while working in the CUS layer, you add a field to the CustTable table, which is in the SYS layer. The new field would be saved on the CUS layer. The revised version of the CustTable table from the CUS layer will be used because the CUS layer is higher than the SYS layer. You can always return to the original version of the CustTable table in the SYS layer by removing the element from the CUS layer.

When an element is used in Microsoft Dynamics AX, the version of the element that is in the highest layer is used.

## See also

[Layers](layers.md)

[Patch Layers](patch-layers.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

