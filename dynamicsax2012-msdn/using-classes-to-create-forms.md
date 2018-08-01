---
title: Using Classes to Create Forms
TOCTitle: Using Classes to Create Forms
ms:assetid: c98a159f-072c-4f2b-8f2e-3ac53bf941b3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa867829(v=AX.60)
ms:contentKeyID: 35251241
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Using Classes to Create Forms [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Use forms to display data to users. Create a form by using the [FormRun](https://msdn.microsoft.com/en-us/library/gg920249\(v=ax.60\)) and [Form](https://msdn.microsoft.com/en-us/library/gg839596\(v=ax.60\)) classes, and a variety of other classes that modify the form design and data source.

You can also create a form by using the Application Object Tree (AOT). For more information, see [Walkthrough: Creating a Form by Using the AOT](walkthrough-creating-a-form-by-using-the-aot.md).

## Example

The following example creates a form to display data that is contained in the CustTable table. Place the code into a method that is called from a main class method to view the form. The signature of a main method is static void main (Args args).

Following is information about the roles of the example's various methods and objects.

The following adds the CustTable table to the form:

  - [Form.addDataSource](https://msdn.microsoft.com/en-us/library/gg839575\(v=ax.60\)) method

  - [FormBuildDataSource](https://msdn.microsoft.com/en-us/library/gg847530\(v=ax.60\)) object

The following creates and modifies the form's design:

  - [Form.addDesign](https://msdn.microsoft.com/en-us/library/gg839577\(v=ax.60\)) method

  - [FormBuildDesign](https://msdn.microsoft.com/en-us/library/gg848126\(v=ax.60\)) object

The following objects add the tab page controls, a grid control, and string controls to the form:

  - [FormBuildTabControl](https://msdn.microsoft.com/en-us/library/gg854100\(v=ax.60\))

  - [FormBuildGridControl](https://msdn.microsoft.com/en-us/library/gg867243\(v=ax.60\))

  - [FormBuildStringControl](https://msdn.microsoft.com/en-us/library/gg869773\(v=ax.60\))

The following method associates data fields with the grid control:

  - [FormBuildGridControl.addDataField](https://msdn.microsoft.com/en-us/library/gg866954\(v=ax.60\))

The following method associates data fields with the string controls:

  - [FormBuildStringControl.dataField](https://msdn.microsoft.com/en-us/library/gg869750\(v=ax.60\))

The following method displays the form:

  - [FormRun.detach](https://msdn.microsoft.com/en-us/library/gg906251\(v=ax.60\))

<!-- end list -->
```X++  
    static void createForm(Args _args)
    {
        Args args;
        Form form;
        FormRun formRun;
        FormBuildDesign formBuildDesign;
        FormBuildDataSource formBuildDataSource;
        FormBuildGridControl formBuildGridControl;
        FormBuildStringControl formBuildStringControl;
        FormBuildStringControl formBuildStringControl2;
        FormBuildTabControl formBuildTabControl;
        FormBuildTabPageControl formBuildTabPageControl;
        FormBuildTabPageControl formBuildTabPageControl2;
        FormStringControl formStringControl;
        FormGridControl formGridControl;
        DictTable dictTable;
        int idx;
        int idx2;
        int idx3;
    
        ;
    
        // Create the form header.
        form = new Form();
    
        // Add a data source to the form. ID 77 refers to the CustTable.
        dictTable = new DictTable(tablenum(CustTable));
        formBuildDataSource = form.addDataSource(dictTable.name());
        formBuildDataSource.table(dictTable.id());
    
        // Create the form design.
        formBuildDesign = form.addDesign("Design");
        formBuildDesign.caption("myForm");
    
        // Add tabbed page controls, a grid control, and string controls.
        formBuildTabControl =
     formBuildDesign.addControl(FormControlType::Tab, "Overview");
        
        formBuildTabPageControl =
     formBuildTabControl.addControl(FormControlType::TabPage, "Overview");
        formBuildTabPageControl.caption("Overview");
        
        formBuildTabPageControl2 =
     formBuildTabControl.addControl(FormControlType::TabPage,"Details");
        formBuildTabPageControl2.caption("Details");
        
        formBuildGridControl =
     formBuildTabPageControl.addControl(FormControlType::Grid,"Table Grid");
        formBuildStringControl =
     formBuildTabPageControl2.addControl(FormControlType::String,"Table String");
        formBuildStringControl2 =
     formBuildTabPageControl2.addControl(FormControlType::String,"Table String");
    
        // Add data fields to controls.
        formBuildGridControl.addDataField
    (formBuildDataSource.id(),dictTable.fieldName2Id("AccountNum"));
        formBuildGridControl.addDataField
    (formBuildDataSource.id(),dictTable.fieldName2Id("Phone"));
        formBuildGridControl.addDataField
    (formBuildDataSource.id(),dictTable.fieldName2Id("Name"));
        formBuildGridControl.addDataField
    (formBuildDataSource.id(),dictTable.fieldName2Id("Address"));
        formBuildStringControl.dataSource(formBuildDataSource.id());
        formBuildStringControl.dataField(2);
        formBuildStringControl2.dataSource(formBuildDataSource.id());
        formBuildStringControl2.dataField(3);
    
        args = new Args();
        args.object(form);
    
        // Create the run-time form.
        formRun = classfactory.formRunClass(args);
    
        formRun.run();
        formRun.detach();
    }
```
## See also

[Methods in X++](methods-in-x.md)

[Methods on a Form](methods-on-a-form.md)

[Event Method Sequences when a Form is Opened](event-method-sequences-when-a-form-is-opened.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

