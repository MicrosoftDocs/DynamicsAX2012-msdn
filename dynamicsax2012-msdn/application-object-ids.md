---
title: Application Object IDs
TOCTitle: Application Object IDs
ms:assetid: 2951f194-4362-460e-8607-7f9fc0022449
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa601997(v=AX.60)
ms:contentKeyID: 35241732
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Application Object IDs [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, elements are referenced by installation-specific IDs. These IDs are assigned at installation time. This means the model file that contains the elements does not contain any element IDs. The IDs are assigned when the model is imported by the AxUtil tool. The same class will have different IDs on different installations.


> [!WARNING]
> <P>If you delete a model and import it again, IDs will become randomized and you may encounter data integrity issues. When you upgrade a model, do not delete the model. Instead, import the new model over the existing model.</P>


  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

