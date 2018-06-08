---
title: Enhanced Preview User Experience Guidelines
TOCTitle: Enhanced Preview
ms:assetid: d8faeb7d-6480-4b2e-8957-76c86d66a799
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886611(v=AX.60)
ms:contentKeyID: 35267975
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Enhanced Preview User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An *enhanced preview* is a quick, on demand, way for users to get additional information that they need about related data without losing their current context. Enhanced previews allow users to be more efficient by allowing them to see more details without having to navigate.

Example of an enhanced preview

  
![Enhanced preview](images/Gg886611.EnhancedPreview01(AX.60).png "Enhanced preview")Example of an enhanced preview

## Design concepts

Enhanced previews are automatically attached to fields that reference other data. For example, an enhanced preview for Customer is automatically attached to the customer account field on a sales order. The system will automatically generate an enhanced preview if no specialized enhanced preview has been defined.  

Microsoft Dynamics AX 2012 provides two types of enhanced previews:

  - System-generated

  - Custom

### System-generated enhanced previews

System-generated enhanced previews are automatically generated from metadata found in the system. Typically, this information is the ID and Description fields found in a table.

Example of a system-generated enhanced preview

  
![System-generated enhanced preview](images/Gg886611.EnhancedPreview02(AX.60).png "System-generated enhanced preview")Example of a system-generated enhanced preview

In this example, the enhanced preview shows the user the key information from the Method of payment table.

System-generated enhanced previews may also look as follows.

![Another system-generated enhanced preview](images/Hh129455.EnhancedPreview03(en-us,AX.60).png "Another system-generated enhanced preview")

### Custom enhanced previews

Custom enhanced previews are previews that have been manually created to show detailed information to the user.

Example of a custom enhanced preview

  
![Custom enhanced preview](images/Gg886611.EnhancedPreview01(AX.60).png "Custom enhanced preview")Example of a custom enhanced preview

Custom enhanced previews are created in the same way that FactBoxes are created.

## Guidelines

  - Because enhanced previews provide supplemental information, users are unlikely to view every enhanced preview on a page. Therefore, enhanced previews should contain related information that helps users understand what the data is, but not information that is essential to the page that the enhanced preview is displayed on.

  - An enhanced preview should not be used as an overflow container for essential information that does not fit on the page. Enhanced previews are not a substitute for application functionality. They are not meant to provide user assistance; tooltips should be used instead to display Help content. If the goal is to provide access to numerous actions, a drop-down menu should be placed next to an object instead of an enhanced preview.

  - Enhanced previews are generally placed on foreign key fields, but may also be placed on fields that represent a summary. For example, an enhanced preview can be used to display more information about a summary.

  - Because enhanced previews are created by using FactBoxes, the guidelines for creating FactBoxes also apply. For the guidelines for creating FactBoxes, see the *FactBoxes* section in the [List Page User Experience Guidelines](list-page-user-experience-guidelines.md) topic.

### An enhanced preview should not have

  - Scroll bars

  - An **OK** or **Close** button, or a **File** menu.

## Labels and text

Because enhanced previews are created by using FactBoxes, the label and text guidelines for FactBoxes apply. For the label and text guidelines for FactBoxes, see the *FactBoxes* section in the [List Page User Experience Guidelines](list-page-user-experience-guidelines.md) topic.

