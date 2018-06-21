---
title: Overview of Context in Enterprise Portal
TOCTitle: Overview of Context in Enterprise Portal
ms:assetid: b44a6937-5fd8-4850-afc7-9d71a0789381
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Ee330231(v=AX.60)
ms:contentKeyID: 35589489
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Overview of Context in Enterprise Portal [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Context is the way that Enterprise Portal passes information about the currently-selected or displayed record, so that another web page or web part can display related information. For example, assume you select a customer from a list page in Enterprise Portal, and then choose an action pane command to display details for that customer. Context information for the customer is passed to the new page so that the data for the selected customer is displayed.

A context object contains the key information that uniquely identifies an element in Microsoft Dynamics AX. For instance, a context object could identify a specific customer.

Web parts and the User Controls in them can consume a context object to determine what data to display. They can also act as providers of context information, creating a context object based on the record that is being displayed or selected. The context object created can be passed to other web pages, web parts, or User Controls so they can display the appropriate corresponding information.

The Enterprise Portal framework has built-in functionality to manage context. In most cases, you will not need to write any code to manage context for your pages. Context can be configured using the properties for web parts and User Controls, and the web part communication that is set up within web pages. Context can be created and accessed from code for User Controls.

## Web Pages

For web pages, the context is passed into the page as a parameter on the URL. This context information is encrypted. When navigating to other pages in Enterprise Portal, the context information can be passed to the page being opened. The Action Pane, Toolbar, and Hyperlink Bound Field components of Enterprise Portal can pass the context information when they are used to navigate to other pages.

## Web Parts on Pages

The web parts on a web page can retrieve the context that was passed into to the page through the URL. To retrieve the context from the page, the WebPartRole property of the web part must be set to Provider. This setting allows the web part to automatically access any context information passed to the page through the URL, and also makes that context information available to send to other web parts on the page.

Connections between the web parts determine how the context is passed between web parts on a page. A web part can get the context from another web part or send the context to another web part. The connection choices available will depend on the web part role settings and how the User Control components for the web parts are configured. For more information about connecting web parts, see [Web Part Communication](web-part-communication.md).

## User Control Components

The User Control components within a User Control web part play a significant part in managing the context information. The [AxDataSource](axdatasource.md) component has functionality built in that allows it to work with context. The Role property of the AxDataSource component determines how it interacts with the web part to manage context. This property can have the following values:

  - None – No context behavior

  - Provider – The AxDataSource component will provide context to other web parts, based on the current row for the AxDataSource. Only one AxDataSource component in a User Control can be the provider.

  - Consumer – The AxDataSource component will receive context information from the web part. It will set the current row of the AxDataSource based on the context.

  - ProviderConsumer – The AxDataSource component will receive context information from the web part. It will also provide context to other web parts, based on the current row for the AxDataSource.

The DataMember and DataKeyNames properties of the [AxGridView](axgridview.md) and [AxForm](axform.md) User Control components must also be set to reference the AxDataSource so that context can be used by those components.

