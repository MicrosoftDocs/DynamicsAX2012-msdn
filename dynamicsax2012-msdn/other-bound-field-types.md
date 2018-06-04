---
title: Other Bound Field Types
TOCTitle: Other Bound Field Types
ms:assetid: ebfb997b-6847-4916-bbc4-fea7a7dcdcec
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc641681(v=AX.60)
ms:contentKeyID: 28119508
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Other Bound Field Types 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Several other types of bound fields can be created in the **Dynamics AX Bound Field Designer**. These bound fields are like [AxBoundField](axboundfield.md) objects, but are displayed in a specific way in Enterprise Portal.

## AxReferenceBoundField

The AxReferenceBoundField component displays the value of a surrogate key in a form or grid. In many Microsoft Dynamics AX tables, record IDs are used as surrogate keys. The record ID of the row uniquely identifies each row in the table. Another table can store the record ID of a specific row in the first table to create a foreign key relationship to a row in that table. The surrogate key value (record ID) is never displayed to the user. Instead, surrogate foreign key replacement is used to show the values of the fields in the AutoIdentification field group for the row referenced by the surrogate foreign key. The AxReferenceBoundField uses a record ID in the field to perform the surrogate foreign key replacement and display the friendly value for the surrogate key.

When using a surrogate key, it is possible to have an ambiguous value that is displayed for the key. For example, you could have two employees with the same name. If you were to manually type in the name of the employee into a field in Enterprise Portal, and multiple employees have that name, it is impossible to determine which employee you intended. Enterprise Portal will select one of the surrogate key values based on the value you entered.

To prevent this ambiguous data situation, the user should use the lookup to select the field value. You can also set the **ResolveAmbiguousReferences** property to true for the AxReferenceBoundField control. When this property is set to true, Enterprise Portal will detect that multiple records exist that match the value that the user has entered in the field. A message in the Infolog will indicate that multiple records with this value were found. The user will then need to use the lookup for the field to select the appropriate record.

## AxBoundFieldGroup

The AxBoundFieldGroup component is used to add a group of bound fields to a form or grid. The field groups are defined in the table that is used for the data set being referenced by the form or grid.

## AxCheckBoxBoundField

The AxCheckBoxBoundField component displays Boolean data as a check box. The properties available for this component are the same as the AxBoundField component, except that there is no **LookupButtonDisplaySettings** property.

## AxDropDownBoundField

The AxDropDownBoundField component displays enumeration data as a drop-down list. The properties available for this component are the same as the AxBoundField component, except that there is no **LookupButtonDisplaySettings** property.

## AxRadioButtonBoundField

The AxRadioButtonBoundField component displays enumeration data a set of radio buttons. The properties available for this component are the same as the AxBoundField component, except that there is no **LookupButtonDisplaySettings** property.

## TemplateField

There are no specific Microsoft Dynamics AX properties for an ASP.NET template field.

