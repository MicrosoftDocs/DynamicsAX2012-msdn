---
title: Defining Field Groups
TOCTitle: Defining Field Groups
ms:assetid: 924fcb27-4cbf-489d-9a96-8c15f8e5eaf1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb314861(v=AX.60)
ms:contentKeyID: 35247461
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Defining Field Groups [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Field groups are objects that group together fields that logically belong together. Field groups can exist on tables, maps, or views. You should define a field group when several fields participate in a single function or are related in some way and are shown together on forms and reports.

It's a best practice to put any fields that appear on the user interface into a group. For more information about field group best practices, see [Best Practices for Field Groups](best-practices-for-field-groups.md).

Field groups make it easier to create a logical layout in a form or report in a number of ways:

  - A whole group of fields can be added to a form or report in one step instead of moving them individually.

  - The field group can be given a label that is displayed on the form.

  - It's easier to update forms and reports using field groups because a change to a field group is reflected in all the forms and reports that use it.

In Microsoft Dynamics AX, field groups are found in the Application Object Tree (AOT) Data Dictionary node in the Field Groups node under the table, map, or view. A field can belong to more than one field group within the same table, map, or view.

## Example

The Customer table contains several field groups including Credit. The Credit field group contains fields that relate to credit like MandatoryCreditLimit and CreditRating.

## Default Field Groups

When a table, map, or view is created, two field groups are automatically created:

  - AutoReport - this field group is used to create the system's automatic reports. The fields placed in this group are displayed when a user clicks Print in the File menu from a form. The AutoReport field group is empty until you add fields to it.

  - AutoLookup - this field group is used in lookup forms. The fields in the field group display when the user clicks the lookup button from a form control. For more information about automatic lookup, see [How to: Add a Control with a Lookup Form](how-to-add-a-control-with-a-lookup-form.md). The AutoLookup group is empty until you add fields to it.

## Display and Edit Methods

If a table has a display or edit method the method can also be added to a field group. For more information about display or edit methods, see [Using the display Method Modifier](using-the-display-method-modifier.md).

  - A display method returns a calculated value to be displayed on a form or a report.

  - An edit method is a variant of a display method. It returns a value to be displayed on a form and accepts user input.

## Example

The LanguageTable table has a display method, languageDescription, that returns a language description, for example 'English(United States)' for 'en-us'. The languageDescription method returns a field and you will find the field that this method returns in some of the LanguageTable's field groups.

The languageDescription method is used for lookup on several forms, including the CustTable form on the General tab page. There's a field on the CustTable form that's called LanguageId and has the Extended Data Type CustLanguageId. CustLanguageId extends LanguageId, which in turn extends LanguageIdAll. LanguageIdAll has a relation to the LanguageId field in the LanguageTable.

## See also

[How to: Create a Field Group](how-to-create-a-field-group.md)

[Tables Overview](tables-overview.md)

[Best Practices for Field Groups](best-practices-for-field-groups.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

