---
title: Parameter System Design Pattern
TOCTitle: Parameter System
ms:assetid: 9bcc224b-393d-437d-beed-8ad5b87f14cb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa846438(v=AX.60)
ms:contentKeyID: 35248198
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Parameter System Design Pattern [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The parameter system design pattern holds static setup information for the modules in a company, such as information on the national currency, the posting method, and so on. There is one instantiation of this pattern per module.

The parameter system should be set up as described in this topic. The parameter record is automatically created by the system and has the following:

  - A parameter table

  - A parameter form

  - A parameter menu item

## Parameter Table

There should be one parameter table per module.

Parameter tables have a single record per company, holding the required parameters for the module. The record is cached. To enable the Found-cache, a key is defined.

The following table shows the property setup of the table.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Value</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>MyModuleParameters</p></td>
<td><p>Module name (prefix) + &quot;Parameters&quot;.</p></td>
</tr>
<tr class="even">
<td><p>Label</p></td>
<td><p>@....</p></td>
<td><p>Mandatory.</p></td>
</tr>
<tr class="odd">
<td><p>FormRef</p></td>
<td><p></p></td>
<td><p>Form and Menu Item should have the same name as table.</p></td>
</tr>
<tr class="even">
<td><p>TitleField1</p></td>
<td><p></p></td>
<td><p>Not mandatory for parameter tables.</p></td>
</tr>
<tr class="odd">
<td><p>TitleField2</p></td>
<td><p></p></td>
<td><p>Not mandatory for parameter tables.</p></td>
</tr>
<tr class="even">
<td><p>Temporary</p></td>
<td><p>No</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>ConfigurationKey</p></td>
<td><p></p></td>
<td><p>Mandatory.</p></td>
</tr>
<tr class="even">
<td><p>MaxAccessMode</p></td>
<td><p>Edit</p></td>
<td><p>No add or delete.</p></td>
</tr>
<tr class="odd">
<td><p>CacheLookup</p></td>
<td><p>Found</p></td>
<td><p>Found cache activated.</p></td>
</tr>
<tr class="even">
<td><p>CreateRecordIDIndex</p></td>
<td><p>No</p></td>
<td><p>Not needed.</p></td>
</tr>
<tr class="odd">
<td><p>SaveDataPerCompany</p></td>
<td><p>Yes</p></td>
<td><p>Parameters are set up per company.</p></td>
</tr>
<tr class="even">
<td><p>TableContents</p></td>
<td><p></p></td>
<td><p>Set according to the contents of the table. Outcome should be default data.</p></td>
</tr>
<tr class="odd">
<td><p>Primary Index</p></td>
<td><p>KeyIdx</p></td>
<td><p>See following description of indexes.</p></td>
</tr>
<tr class="even">
<td><p>Cluster Index</p></td>
<td><p>KeyIdx</p></td>
<td><p>See following description of indexes.</p></td>
</tr>
<tr class="odd">
<td><p>TableGroup</p></td>
<td><p>Parameter</p></td>
<td><p>Mandatory: Parameter.</p></td>
</tr>
</tbody>
</table>


### ![Aa846438.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa846438.collapse_all(en-us,AX.60).gif")Table Fields

Add an integer field that is named key. It should have the Visible property set to No, and the Mandatory property set to No (because it holds the value 0).

Add any other fields for the parameters needed for the module.

### ![Aa846438.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa846438.collapse_all(en-us,AX.60).gif")Table Index

Create a unique index called keyIdx, that consists of the field key.

### ![Aa846438.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa846438.collapse_all(en-us,AX.60).gif")Table Methods

The following code example illustrates how to create a static find method:

    client server static MyModuleParameters find()
    {
        MyModuleParameters parameter;
        ;
        select firstOnly parameter
            index Key
            where parameter.key == 0;
     
        if (!parameter)
        {
            Company::createParameter(parameter);
            NumberSeqReference::construct(MyParameters::numberSeqModule()).load();
        }
        return parameter;
    }

The following code example illustrates how to create a delete method:

    void delete()
    {
        throw error("@SYS23721");
    }

The following code example illustrates how to create an update method:

    void update()
    {
        super();
        flush MyModuleParameters; 
    }

Create a validateWrite method, if necessary.

Create an initValue method for initializing the table (record) with relevant parameters, even if they have not been set up manually.

### ![Aa846438.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa846438.collapse_all(en-us,AX.60).gif")Call the find Method in the Company Class

Place a call to the find method on your parameter table in the Company.selectParameters method (internal development) or, if you are developing in the higher layers, place the call in the Company.selectParametersPost method.

The selectParametersPost method is at first an empty [partner hook](partner-hooks-design-pattern.md). It is called by the standard application after the selectParameters method and is a good option for partners and others to add their extensions to the standard application. This helps make the upgrade process more straightforward.

## Parameter Forms

Do not set the TitleDatasource property in the design properties. There is only one record and no identifying key.

Add a tab with number sequences. For more information about how to create a number sequence for a new module, see [Number Sequence Framework](number-sequence-framework.md).

## See also

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

