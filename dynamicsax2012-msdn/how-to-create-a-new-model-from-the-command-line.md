---
title: 'How to: Create a New Model from the Command Line'
TOCTitle: 'How to: Create a New Model from the Command Line'
ms:assetid: e077bf7e-8895-4bdf-a1bc-72bf37971956
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh433541(v=AX.60)
ms:contentKeyID: 36941334
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- powershell
---

# How to: Create a New Model from the Command Line 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can create an empty model that has default properties. Alternatively, you can create an XML manifest file that specifies the properties of a model, and then create a model by using the manifest file.

You can use either Windows PowerShell cmdlets or the AXUtil command-line utility to perform this task.

## Preparing the system

### Validate permissions

  - Validate that you have appropriate permissions to work with the model store:
    
      - Administrative permissions on the local computer
    
      - System Administrator rights in Microsoft Dynamics AX
    
      - In Microsoft SQL Server:
        
          - Membership in the Securityadmin server role on the SQL Server instance
        
          - Membership in the db\_owner role in the Microsoft Dynamics AX database

## Creating an empty model that has default manifest properties

You can quickly create an empty model that has default manifest properties.

### Create an empty model that has default manifest properties (Windows PowerShell)

1.  On the **Start** menu, point to **All Programs**, point to **Administrative Tools**, and then click **Microsoft Dynamics AX Management Shell**.

2.  At the Windows PowerShell command prompt, PS C:\\\>, type the following command, and then press ENTER.
    
    ``` powershell
    New-AXModel -Model <Modelname> -Layer <LayerName>
    ```
    
    This command creates a new model in the specified layer, and sets the parameters of the model to the default values.
    
    For more information, see [New-AXModel](https://msdn.microsoft.com/en-us/library/jj720245\(v=ax.60\)).

### Create an empty model that has default manifest properties (AXUtil)

1.  On the **Start** menu, click **Command prompt**.

2.  Navigate to the directory for the management utilities. Typically, the location of this directory is %ProgramFiles%\\Microsoft Dynamics AX\\60\\ManagementUtilities.

3.  At the command prompt, type the following command, and then press ENTER.
    
        axutil create /model:<ModelName>/layer:<LayerName>
    
    This command creates a new model in the specified layer, and sets the parameters of the model to the default values.

## Creating a manifest file for a model

Model manifests are a group of properties that describe a model. The following XML file is the manifest from a model that is called MyModel. This model is located in the ISV layer.

    <?xml version="1.0" encoding="utf-8"?> 
    <ModelManifest SchemaVersion="1.9" ModelFileVersion="17" ElementCount="0"> 
    <Name>MyModel</Name>
    <DisplayName>MyModel</DisplayName> 
    <Description /> 
    <Publisher />
    <Signed>false</Signed> 
    <Category>Standard</Category> 
    <InstallMode>Standard</InstallMode> 
    <Version>1.0.0.0</Version> 
    <Layer>ISV</Layer> 
    <DependencyState /> 
    </ModelManifest>PS C:\Windows\system32>

### Create a manifest file for a model (Windows PowerShell)

1.  On the **Start** menu, point to **All Programs**, point to **Administrative Tools**, and then click **Microsoft Dynamics AX Management Shell**.

2.  At the Windows PowerShell command prompt, PS C:\\\>, type the following command, and then press ENTER.
    
    ``` powershell
    Get-AXModelManifest –Model <name> -XML
    ```
    
    This command creates an XML manifest file from a model. You can modify the XML file, and then use the file to create a new model.
    
    For more information, see [Get-AXModelManifest](https://msdn.microsoft.com/en-us/library/jj720291\(v=ax.60\)).

### Create a manifest file for a model (AXUtil)

1.  On the **Start** menu, click **Command prompt**.

2.  Navigate to the directory for the management utilities. Typically, the location of this directory is %ProgramFiles%\\Microsoft Dynamics AX\\60\\ManagementUtilities.

3.  At the command prompt, type the following command, and then press ENTER.
    
        axutil manifest /model:<model> /xml > <filename>
    
    This command creates an XML manifest file from a model. You can modify the XML file, and then use the file to create a new model.

## Creating a new model

Before you create a new model, modify an existing manifest file that is in XML format.

### Create a model from a manifest file (Windows PowerShell)

1.  On the **Start** menu, point to **All Programs**, point to **Administrative Tools**, and then click **Microsoft Dynamics AX Management Shell**.

2.  At the Windows PowerShell command prompt, PS C:\\\>, type the following command, and then press ENTER.
    
    ``` powershell
    New-AXModel -Model <Modelname> -Layer <LayerName> -ManifestFile <filename.xml>
    ```
    
    This command creates a new model in the specified layer, and sets the parameters of the model based on the specified XML file.
    
    For more information, see [New-AXModel](https://msdn.microsoft.com/en-us/library/jj720245\(v=ax.60\)).

### Create a model from a manifest file (AXUtil)

1.  On the **Start** menu, click **Command prompt**.

2.  Navigate to the directory for the management utilities. Typically, the location of this directory is %ProgramFiles%\\Microsoft Dynamics AX\\60\\ManagementUtilities.

3.  At the command prompt, type the following command, and then press ENTER.
    
        axutil create @manifestfilename.xml
    
    This command creates a new model in the default layer, and sets the parameters of the model based on the specified XML file.

## See also

[Models, Layers, and the Model Store](models-layers-and-the-model-store.md)

[AxUtil and Windows PowerShell Commands for Deploying Models](https://msdn.microsoft.com/en-us/library/hh456294\(v=ax.60\))

[Administering Microsoft Dynamics AX by using Windows PowerShell](https://msdn.microsoft.com/en-us/library/hh272856\(v=ax.60\))

[Windows PowerShell for Microsoft Dynamics AX](https://msdn.microsoft.com/en-us/library/hh556863\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

