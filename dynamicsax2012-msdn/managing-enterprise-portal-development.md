---
title: Managing Enterprise Portal Development
TOCTitle: Managing Enterprise Portal Development
ms:assetid: b06f2e3c-8df7-4156-afde-2fd46c9b29d2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc617398(v=AX.60)
ms:contentKeyID: 35245630
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Managing Enterprise Portal Development [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When making modifications in Enterprise Portal, you may want to make your changes on a test site first. After the changes have been tested, you can deploy them to the live Enterprise Portal site.

## Enterprise Portal Test Site

After Enterprise Portal is installed, you can create another Enterprise Portal site that you can use for development and testing. The process of creating an Enterprise Portal site is described in [Create an Enterprise Portal site](https://msdn.microsoft.com/en-us/library/dd362092\(v=ax.60\)). This site is on the same server as the live Enterprise Portal site, but has a different URL.

## AOT

The resources used by an Enterprise Portal site are stored in the Application Object Server. These resources are managed by using the AOT. The AOT can interact with only one Enterprise Portal site at a time. If you make modifications in the Enterprise Portal test site and then deploy the tested results to a live site, you must be able to switch which Enterprise Portal site the AOT is interacting with. Do this using the **Administration of Web sites** form in Microsoft Dynamics AX. To open this form, click **System administration**. In the **Setup** group, expand **Enterprise Portal**. Click **Web sites**.

At the bottom of this form is a field labeled **Default Enterprise Portal site**. The URL in this field indicates which Enterprise Portal site the AOT will interact with.

## Development Process

When you use a test site for Enterprise Portal development, the basic development process is as follows:

1.  The AOT is configured to point to the Enterprise Portal test site.

2.  Development activities are performed, such as modifying pages or navigation. All of the changes are tested using the Enterprise Portal test site.

3.  Some resources created or modified in the AOT, such as Web Menus, are automatically updated in the AOS. These resources are used in all the Enterprise Portal sites on the virtual server. Be aware that some of the changes that you make to these resources for the test site will also affect the live site.

4.  Other resources that you have created or changed, such as web pages, are updated only on the Enterprise Portal site that you are working with. These changes and additions must be imported into the AOT.

5.  The AOT is configured to point to the live Enterprise Portal site.

6.  The new and changed resources are deployed to the live Enterprise Portal site. You can deploy the resource manually, or you can use the AxUpdatePortal utility to deploy the resources. Some of the resources from the AOT that you will need to deploy are:
    
      - Web pages
    
      - Web controls
    
      - Web modules

If you deploy Enterprise Portal to a new site, this new Enterprise Portal site will contain all of the changes that you made to or imported into the AOT.

## See also

[AxUpdatePortal Utility](axupdateportal-utility.md)

