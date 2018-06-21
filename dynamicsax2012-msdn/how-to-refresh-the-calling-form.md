---
title: 'How to: Refresh the Calling Form'
TOCTitle: 'How to: Refresh the Calling Form'
ms:assetid: c6d3b144-f563-4d06-945b-ac26c08d0e1d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh812104(v=AX.60)
ms:contentKeyID: 44089903
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Refresh the Calling Form [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You often open a dialog or drop dialog when you are working with another form. As a result, you might want to refresh the parent form after you finish the action on the dialog or drop dialog form. However, not every dialog form requires that you update the calling form. Typically, you refresh the parent form when the information that you provide in the dialog form appears on that form.

To follow these steps, you must first create a dialog or drop dialog form. For information about how to create a dialog or drop dialog form, see [How to: Create a Dialog Form](how-to-create-a-dialog-form.md). In addition, you may want to add button controls to the parent form that enable you to open the dialog or drop dialog form.

## Refreshing a Form with a Single Root Data Source

To refresh a parent form, you can often use a task to refresh the form. You should use a task when the form has a single root data source. For example, the **CustTableListPage**, **SalesTable**, **VendTable**, and **HcmWorker** forms all have a single root data source. When you use a task to refresh the form, you cause a call to the research method for all data source tables associated with the form.

### To update the form root data source

1.  In the AOT, expand **Forms**, find the dialog or drop dialog form that you want to work with. Expand the form node.

2.  Right-click the **Methods** node, click **Override method**, and then click **closeOK**. The method opens in the code editor.

3.  Use the FormRun class together with the \#taskF5 refresh task to refresh any form that opens this dialog or drop dialog form.
    
    The following code example shows how to get a reference to the calling form and how to refresh that form. Notice how the formRun instance is populated with a reference to the calling form. Also notice how \#taskF5 is used to force a refresh of the specified form.
    
        public void closeOk()
        {
            #Task
            FormRun formRun;
            
            super();
            
            // Get an instance of the calling form.
            formRun = element.args().caller();
            
            // If the caller is a form, refresh that form.
            if(formRun)
            {
                formRun.task(#taskF5);
            }
        }

4.  In the code editor, press the compile button. When compiling is finished, close the code editor.

5.  Right-click the form and then click **Save**.

To refresh the parent form, open the form you use to call the dialog or drop dialog form where you added the previous code. Select a record, open the dialog form, and make a change to a field that appears on the parent form. Click **OK** to close the dialog form. The parent form is refreshed and shows the value that you updated in the dialog form.

## Refreshing a Form with Multiple Root Data Sources

The form that opens your dialog or drop dialog form might have multiple root data sources. For example, the **smmActivities** form has two root data sources. If you have more than one root data source, you should refresh the data source that includes fields that were updated by using the dialog or drop dialog form.

### To find and update a specified root data source

1.  In the AOT, find the dialog or drop dialog form that you want to work with. Expand the form node.

2.  Right-click **Methods**, click **Override method**, and then click **closeOK**. The method opens in the code editor.

3.  Use the FormRun class to get a reference to the calling form. You then have to iterate the list of root data sources to find the data source table that include the fields you updated in the dialog or drop dialog form. You must know the name of the root data source table.
    
    The following code example shows how to get a reference to the calling form, how to iterate a list of root data sources, and how to use the research method to refresh a specified data source. Notice how the tableNum function specifies the root data source table you want to refresh.
    

    > [!WARNING]
    > <P>In the example, the target root data source table is named Table1. You would have to change this parameter to the name of the root data source table that contains the fields updated by the dialog or drop dialog form.</P>

    
        public void closeOk()
        {
            FormRun formRun;
            List dsList;
            ListEnumerator dsListEnumerator;
            FormDataSource formDS;
            
            super();
            
            // Get an instance of the calling form.
            formRun = element.args().caller();
            
            // If the caller is a form, find and refresh the specified root data source.
            if(formRun)
            {
                dsList = formRun.rootFormDataSources();
                
                if(dsList && dsList.elements() > 0)
                {
                    dsListEnumerator = dsList.getEnumerator();
                    
                    while(dsListEnumerator.moveNext())
                    {
                        formDS = dsListEnumerator.current();
                        if(formDS.table() == tableNum(Table1))
                        {
                            formDS.research(true);
                            break;
                        }
                    }
                }
            }
        }

4.  In the code editor, press the compile button. When compiling is finished, close the code editor.

5.  Right-click the form and then click **Save**.

To refresh the parent form, open the form you use to call the dialog or drop dialog form where you added the previous code. Select a record, open the dialog form, and make a change to a field that appears on the parent form. Click **OK** to close the dialog form. The parent form is refreshed and shows the value that you updated in the dialog form.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

