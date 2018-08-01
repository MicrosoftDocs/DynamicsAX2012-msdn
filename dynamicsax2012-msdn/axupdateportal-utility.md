---
title: AxUpdatePortal Utility
TOCTitle: AxUpdatePortal Utility
ms:assetid: 4b4d70de-250a-4dae-8809-bd79018ce367
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dd261467(v=AX.60)
ms:contentKeyID: 35245311
ms.date: 01/08/2014
mtps_version: v=AX.60
---

# AxUpdatePortal Utility [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The AxUpdatePortal utility, installed with Microsoft Dynamics AX, can be used to deploy Enterprise Portal sites. It can also be used to deploy modifications or additions you have made to existing Enterprise Portal Sites. The utility makes deployment easier, because it can deploy web-related changes to an Enterprise Portal site on an IIS site (virtual server) in just one step. It can also be used to deploy or update specific resources for an Enterprise Portal site.

## Common Deployment Scenarios

You can have multiple Enterprise Portal sites on an IIS site (virtual server). For example, you could have a "development" site and a "live" site. You would make modifications in the development site. After the modifications have been tested, you would deploy them to the live site. Typically, you do this by pointing the AOT to the Enterprise Portal site to which you want to deploy the changes. In the AOT, you will deploy the web-related items to the Enterprise Portal site. You would repeat this procedure for each Enterprise Portal site where you want to deploy the changes. The AxUpdatePortal utility can make this process easier, by allowing you to deploy updated resources to each of the sites in just one step.


> [!IMPORTANT]
> <P>If you have multiple front-end web servers in your Enterprise Portal installation, you must deploy the resources to each front-end server separately.</P>



Another common scenario is installing a new application for Enterprise Portal. To do this, you would import the resources for the new application from an .xpo file or an .axmodel file into the AOT. Then you would point the AOT to each Enterprise Portal web site and deploy the web-related items for the new application to each site. The action to import the new resources into the AOT has to be performed only one time. However, the deployment to the Enterprise Portal web site must be performed for each separate site and often involves multiple steps. The AxUpdatePortal utility can make this process easier. With it, you can deploy the new application to each specific Enterprise Portal site.

## Using AxUpdatePortal

AxUpdatePortal.exe is a command-line utility that is installed with Microsoft Dynamics AX. The AxUpdatePortal utility is found in the following location on the IIS server on which Enterprise Portal is installed:

C:\\Program Files\\Microsoft Dynamics AX\\60\\Setup

On each Microsoft Dynamics AX client, the AxUpdatePortal utility is found in the following location:

C:\\Program Files\\Microsoft Dynamics AX\\60\\EnterprisePortalTools


> [!TIP]
> <P>You can use the AxUpdatePortal utility from any system that is running Microsoft Dynamics AX. The utility uses a web service to connect to the IIS server that is running Enterprise Portal.</P>




> [!IMPORTANT]
> <P>The account specified in Microsoft Dynamics AX to use for the Business Connector Proxy must be the same account that is used to run the application pool for the SharePoint site that is used for Enterprise Portal. If two different accounts are used, the AxUpdatePortal utility operations will not complete successfully.</P>
> <P>To successfully deploy Enterprise Portal resources, you must have the following roles and permissions:</P>
> <UL>
> <LI>
> <P>Administrator role in Microsoft Dynamics AX.</P>
> <LI>
> <P>Administrator for SharePoint. To verify this, open SharePoint Central Administration on the Enterprise Portal server. If you cannot access SharePoint Central Administration, a SharePoint administrator must open <STRONG>SharePoint Central Administration</STRONG> &gt; <STRONG>Security</STRONG> &gt; <STRONG>Manage the farm administrators group</STRONG> and add you as an administrator.</P>
> <LI>
> <P>Site collection administrator for the Enterprise Portal site. To verify this, open <STRONG>SharePoint Central Administration</STRONG> &gt; <STRONG>Application Management</STRONG>. Click <STRONG>Site Collections</STRONG> &gt; <STRONG>Change site collection administrators</STRONG>. Verify that you are listed as the primary or secondary site collection administrator.</P>
> <LI>
> <P>Privileges to access the file locations on the Enterprise Portal server where files will be put. One way to guarantee this is by running the command prompt that is used to call AxUpdatePortal.exe with administrative privileges.</P></LI></UL>



To see details of the commands that can be performed, type the following command:

AxUpdatePortal.exe

If you include the -iisreset parameter for the command, IIS will be reset after the update operation has been completed.

## Examples

The following examples show common ways that AxUpdatePortal is used.

## Listing virtual servers

A virtual server is an IIS web site that has been extended with SharePoint. To list the virtual servers and IIS web sites for the current computer, use the following command:

AxUpdatePortal -listvirtualservers

This command may not be supported for some configurations of Enterprise Portal and Microsoft Dynamics AX. If you encounter an error when using this command, consider using the **Get-SPWebApplication** cmdlet to list the virtual servers. This cmdlet is part of the PowerShell cmdlets included with SharePoint.

## Deploying a new virtual server site

To deploy a new virtual server site to an IIS web server that already has Enterprise Portal installed, use the following command:

AxUpdatePortal –deploy –websiteurl http:// *ServerName*\[:port\]/Sites/*SiteName*

*ServerName* - The name of the server on which Enterprise Portal is running.

*SiteName* – The name of the new virtual server site.

For example, the following command creates a new virtual server site that is to be used for Enterprise Portal development. The site is named DynamicsAXDev and it is created on the server named DEVEP.

AxUpdatePortal –deploy –websiteurl http://DEVEP/Sites/DynamicsAXDev

## Creating a site for a virtual server

If you deployed a new virtual server site, but did not include the –createsite parameter, you can use the following command to create the Enterprise Portal site for that virtual server site:

AxUpdatePortal –createsite –websiteurl http:// *serverName*\[:port\]/Sites/*SiteName*

*ServerName* - The name of the server on which Enterprise Portal is running.

*SiteName* – The name of the virtual server site for which the Enterprise Portal site is being created.

For example, the following command creates an Enterprise Portal site for the DynamicsAXDev virtual server site that was created in the previous example.

AxUpdatePortal –createsite –websiteurl http://DEVEP/Sites/DynamicsAXDev

## Updating the web components on an Enterprise Portal site

To update the web components on an Enterprise Portal site, use the following command:

AxUpdatePortal –updateall –websiteurl http:// *serverName*\[:port\]/Sites/*SiteName*

*ServerName* - The name of the server on which Enterprise Portal is running.

*SiteName* – The name of the virtual server site for which the web components are to be updated.

The following table lists the web components that are updated:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>AOT Location</p></th>
<th><p>Items Deployed</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>\Web\Web Files\Web Parts</p></td>
<td><p>Any SharePoint web parts that have been added to the AOT.</p></td>
</tr>
<tr class="even">
<td><p>\Web\Web Files\Page Definitions</p></td>
<td><p>All page definitions</p></td>
</tr>
<tr class="odd">
<td><p>\Web\Web Files\List Definitions</p></td>
<td><p>All list definitions</p></td>
</tr>
<tr class="even">
<td><p>\Web\Web Files\Static Files</p></td>
<td><p>Static files such as cascading style sheets and features.</p></td>
</tr>
<tr class="odd">
<td><p>\Web\Web Files\Web Controls</p></td>
<td><p>All User controls.</p></td>
</tr>
<tr class="even">
<td><p>\Web\Web Modules</p></td>
<td><p>All web modules</p></td>
</tr>
</tbody>
</table>


For example, the following command updates all of the web components for the DynamicsAXDev site on the DEVEP server.

AxUpdatePortal –updateall –websiteurl http://DEVEP/Sites/DynamicsAXDev

## Updating proxies on an Enterprise Portal site

To update all of the proxies on an Enterprise Portal site, use the following command:

AxUpdatePortal –proxies –websiteurl http:// *serverName*\[:port\]/Sites/*SiteName*

*ServerName* - The name of the server on which Enterprise Portal is running.

*SiteName* – The name of the virtual server site for which all of the proxies are to be updated.

This command deploys the proxies for the Visual Studio projects from the AOT that have the **Deploy To EP** property set to **Proxies**.

For example, the following command updates all of the proxies for the DynamicsAXDev site on the DEVEP server.

AxUpdatePortal –proxies –websiteurl http://DEVEP/Sites/DynamicsAXDev

## Updating the images on an Enterprise Portal site

To update all of the images on an Enterprise Portal site, use the following command:

AxUpdatePortal –images –websiteurl http:// *serverName*\[:port\]/Sites/*SiteName*

*ServerName* - The name of the server on which Enterprise Portal is running.

*SiteName* – The name of the virtual server site for which all of the images are to be updated.

Images from the CompanyImage, ECPPresentation, and EcoResProductImage tables are deployed to each Enterprise Portal site. Product catalog images are deployed as well.

For example, the following command updates all of the images for the DynamicsAXDev site on the DEVEP server.

AxUpdatePortal –images –websiteurl http://DEVEP/Sites/DynamicsAXDev

## Updating a specific web component on an Enterprise Portal site

To update a specific web component for an Enterprise Portal site, use the following command:

AxUpdatePortal –updatewebcomponent –treenodepath *Path* –websiteurl http:// *ServerName*\[:port\]/Sites/*SiteName*

Path – The relative path of the web component to deploy. The path begins with the Web node. For example, the path Web\\Web Files\\Page Definitions\\FCMWorkOrdersListPage indicates the page named FCMWorkOrdersListPage.

*ServerName* - The name of the server on which Enterprise Portal is running.

*SiteName* – The name of the virtual server site to which the web component will be deployed.

For example, the following command updates the WorkOrderDetails web control for the DynamicsAXDev site on the DEVEP server.

AxUpdatePortal –updatewebcomponent –treenodepath "Web\\Web Files\\Web Controls\\WorkOrderDetails" –websiteurl http://DEVEP/Sites/DynamicsAXDev

