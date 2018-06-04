---
title: Conversion Procedure
TOCTitle: Conversion Procedure
ms:assetid: 6eb1d1c0-4bdc-4472-b757-cb3bc6b5c385
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh272126(v=AX.60)
ms:contentKeyID: 36542038
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Conversion Procedure 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following procedure is the basic process that you can follow to convert an Enterprise Portal application from an earlier version of Microsoft Dynamics AX to work on Enterprise Portal for Microsoft Dynamics AX 2012.

## Converting an Enterprise Portal Application

Before you begin this procedure, make sure that Microsoft Dynamics AX 2012 and Enterprise Portal are set up and working correctly.

### To convert an Enterprise Portal application

1.  Import the Enterprise Portal resources for your application into the Microsoft Dynamics AX 2012 installation. Typically, you will do this using a .xpo file.
    
    You may have better results by choosing not to import some resources. Instead, you should re-create them in the new version of Enterprise Portal. Examples include the MainMenu and Web Module resources. They can potentially break the navigation in Microsoft Dynamics AX 2012 when you import them. Other examples include Cues and X++ reports, because these will not work in the new version of Enterprise Portal.

2.  Make modifications to the application resources to account for database changes in Microsoft Dynamics AX 2012. See [Database Changes](database-changes.md) for detailed information about doing this.

3.  Make modifications to the application resources to account for framework changes in Microsoft Dynamics AX 2012. See [Framework Changes](framework-changes.md) for detailed information about doing this.

4.  Make changes to the data sets used for your Enterprise Portal application to accommodate the database changes.

5.  Verify the functionality for each web page in your Enterprise Portal application. You may find easier to work with one page at a time. For each page, do the following:
    
    1.  Verify the web parts on the page. See [Page Changes](page-changes.md) for information about specific issues to address.
    
    2.  Verify the User Controls on the page. See [User Control Changes](user-control-changes.md) for information about specific issues to address.

6.  Verify the navigation for your application.

7.  Implement new features for your application.

8.  Test your converted Enterprise Portal application thoroughly.

