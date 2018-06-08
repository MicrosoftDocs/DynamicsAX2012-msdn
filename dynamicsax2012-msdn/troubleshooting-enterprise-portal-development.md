---
title: 'Troubleshooting: Enterprise Portal Development'
TOCTitle: 'Troubleshooting: Enterprise Portal Development'
ms:assetid: 56ba5aa3-b41e-4918-8440-61526cafb036
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc554278(v=AX.60)
ms:contentKeyID: 35245345
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Troubleshooting: Enterprise Portal Development 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You may encounter some issues when you develop for or customize Enterprise Portal. Use the following information to help resolve issues.

## Enterprise Portal

The following solutions can be helpful when you encounter problems in Enterprise Portal.

### Event Viewer

If you encounter SharePoint errors when you develop for Enterprise Portal, look in the Event Viewer for the system that is running SharePoint. The errors will be listed in the Application group. In many cases, the details of the error will help you isolate the cause of the problem.

### Refreshing Caches

Enterprise Portal caches resources from the AOT and data from tables in Microsoft Dynamics AX. If you make changes in the AOT, the changes may not be reflected immediately in Enterprise Portal. In a similar way, data that has been changed in tables for Microsoft Dynamics AX may not immediately be seen in Enterprise Portal. Stale data in these caches could cause unexpected results in Enterprise Portal. Three commands are available in the **Administration** group at the bottom of the main page for Enterprise Portal to refresh these caches. The commands are described in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Command</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Refresh AOD</p></td>
<td><p>Flushes cached application object information for all items in the AOT. Use this when changes you made in the AOT are not immediately reflected in Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>Refresh data</p></td>
<td><p>Flushes cached database records. Use this when changes in the database are not immediately reflected in Enterprise Portal.</p></td>
</tr>
<tr class="odd">
<td><p>Refresh dictionary</p></td>
<td><p>Flushes cached application object information for items in the Data Dictionary node of the AOT. Use this when you have made changes to resources in the Data Dictionary node, such as tables or extended data types, but the changes are not immediately reflected in Enterprise Portal.</p></td>
</tr>
</tbody>
</table>


### Resetting IIS

Resetting IIS may resolve unexpected behavior in Enterprise Portal when you are making significant changes during development. In some cases, cached data may be used, instead of the data that you updated. Resetting IIS causes Enterprise Portal to start with the most current data.

### Restarting the AOS

In rare cases, you may find that restarting the AOS (Application Object Server) can resolve unexpected or incorrect behavior in Enterprise Portal. If you have tried all of the other troubleshooting techniques without success, and cannot find anything that seems incorrect in your Enterprise Portal integration, try restarting the AOS.

### Non-functioning Web Parts

As you create a web part and add code to it, you may encounter cases where the page that contains the web part no longer displays because of a problem in the web part. If you cannot resolve the issue with the web part by modifying the code for it, you may have to remove the web part from the page. This may seem impossible because the page cannot be displayed. However, you can use another view of the web page that allows for you to access the web parts on it.

To use this view, add "contents=1" at the end of the URL for the web page. This will display the web page content as a list. This allows you to remove the non-functioning web part. For example, the following URL displays the Customers list page content in this list view:

http://\<server\>/sites/DynamicsAx/Sales/Enterprise%20Portal/customers.aspx?contents=1

### Turning on Debugging

If you are seeing errors in SharePoint, or web parts display an error instead of content, turn on debugging for the web site. Often, this will produce more helpful error information that you can use to resolve the problem.

To turn on debugging, open the web.config file for the site on which you are running Enterprise Portal. Typically, this will be in a location similar to the following:

C:\\Inetpub\\wwwroot\\wss\\VirtualDirectories\\80

If you are running Enterprise Portal on a different port, look in the folder for that port. Using a text editor, search the web.config file for the entry **compilation**. Set the debug attribute to true. The entry will resemble the following:

    <compilation batch="false" debug="true">

Save the changes. Use the **iisreset** command to restart Enterprise Portal.


> [!TIP]
> <P>If User Account Control (UAC) is active, you cannot edit the web.config in place. You must copy the web.config file to a location where you have editing privileges, make the change to the file, and then copy the updated file back to its original location.</P>



### Viewing URLs for Modal Dialog Pages

Many pages in Enterprise Portal are displayed as modal dialogs in SharePoint. The URLs for these pages are not displayed on the page. To view the URL that was used to access the page, right-click on a blank area of the page and then click Properties. In the Properties window, select the content for Address field. The field does not look selectable, but it is. You will need to scroll through the selection to see the full URL.

### Viewing Context Information

You may need to troubleshoot passing context information from one page to another page in Enterprise Portal. When context information is passed through the URL for the page being opened, the information is encrypted to enhance the security. To help troubleshoot context problems, you can turn off the encryption so that you can see the values being passed for the context. For information about turning off encryption for the context information, [How to: View Context in Enterprise Portal](how-to-view-context-in-enterprise-portal.md).

## Visual Studio

The following solutions can be helpful when you encounter problems when working in Visual Studio.

### Reloading the Project

If the Visual Studio project for User Controls has lost the connection to the AOT, you must restart Visual Studio and reload the project.

### Build Errors

If the project for User Controls encounters build errors, be sure that you have referenced the proxy projects that are required for the project. See [How to: Use a Predefined Proxy for a Web Application Project](how-to-use-a-predefined-proxy-for-a-web-application-project.md) for more information. Also, be sure that your code has the appropriate using statements to reference the namespaces for the objects, methods, and properties you are using.

If you have used .xpo files to import additional proxy projects, the proxies needed to compile the User Controls may be out-of-date. To regenerate the proxies for web controls, open the AOT. Right-click **Web** \> **Web Files** \> **Web Controls** and then click **Generate Proxies for Compilation**.

### Changes Not Reflected in Enterprise Portal

If changes you made to the Visual Studio project are not reflected in Enterprise Portal, be sure that you have saved the changes in Visual Studio. For instance, changes you make to the layout of a User Control will not be reflected in Enterprise Portal until you save the changes to the .ascx file for the User Control in Visual Studio.

If you save the changes to the .ascx file, but the changes are still not displayed in Enterprise Portal, you may not have permission to deploy resources to the Enterprise Portal site. If User Account Control (UAC) is active, then you must start Visual Studio with administrative privileges. This allows you to have adequate permission to deploy the updated resources to the Enterprise Portal site when you update and save them in Visual Studio.


> [!TIP]
> <P>To find out whether Visual Studio is running with administrative privileges, look at the text in the title bar. It should contain <STRONG>(Administrator)</STRONG>.</P>


