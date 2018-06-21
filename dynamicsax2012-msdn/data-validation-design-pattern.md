---
title: Data Validation Design Pattern
TOCTitle: Data Validation
ms:assetid: a0dbd0c3-3b54-4535-a885-0eee1866b932
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa848817(v=AX.60)
ms:contentKeyID: 35248277
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Data Validation Design Pattern [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The data validation design principle in Microsoft Dynamics AX validates data as it is entered.

## When to Validate Data

Data can be in a state that is not acceptable. This section will provide information about the following:

  - Whether to validate data

  - Whether the data has already been validated

  - Consequences of working on non-validated or inconsistent data

## Data in the Database

Data in the database is validated and requires no further revalidation.

If data is being processed from the database, do not revalidate unless:

  - Something important has or could have been changed in related data

  - Related data has not been updated

Whether you are reading data from forms, the environment, or external files, validate the data before you save it in the database.

Do not write or call code to validate data that is already validated.

Data that will be stored in the database should be validated by using code written on the validateWrite, validateField, and validateDelete methods on the respective tables. Use the insert, update, and delete table methods to work with the data in the tables. Other validations can be written in check methods.

The implementation of validating data that is entered into the database is to write the previously mentioned methods. If you are reading and processing the data yourself, call the respective validate and check methods. Forms, by default, automatically call the validate methods.

## Data in an Inconsistent State

If data is being processed and is in an inconsistent state, try to fix the inconsistency. If you are not able to fix the issue, abort the process.

Throw an error to inform users about the problem.

Write Check & Fix jobs for your module by using the Consistency check framework. Check & Fix jobs can be run regularly to find and possibly fix inconsistencies in the database.

If data is in an inconsistent state, abort the process by throwing an error that has a description of the problem and a description of how to fix it including the location in which the fix should be made.

## See also

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

[Use the Type System Design Pattern](use-the-type-system-design-pattern.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

