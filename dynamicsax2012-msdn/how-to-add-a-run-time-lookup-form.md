---
title: 'How to: Add a Run-Time Lookup Form'
TOCTitle: 'How to: Add a Run-Time Lookup Form'
ms:assetid: 479ab935-d903-4045-841b-dc961acc10de
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa627966(v=AX.60)
ms:contentKeyID: 35243037
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a Run-Time Lookup Form 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A run-time lookup form enables you to specify the lookup form that appears when you click the lookup button (![Lookup button](images/Aa597861.LOOKUP(en-us,AX.60).gif "Lookup button")) of a control. You use a run-time lookup form to replace the standard lookup form or extended data type (EDT) lookup form that appears when you click the lookup button. The following sections describe how to add a run-time lookup form for a field that uses a surrogate foreign key or a natural foreign key. For more information about surrogate foreign keys and natural foreign keys, see [Data Sources for Forms](data-sources-for-forms.md).

## To Add a Run-Time Lookup Form for a Surrogate Foreign Key Field

To add a run-time lookup form for a surrogate foreign key field, override the lookupReference method of the field. To use this procedure, the field must be bound to a **ReferenceGroup** control.

To see an example of a form with a run-time lookup, view the **HcmGoal** form. The **GoalHeading** field of the **HcmGoal** data source overrides the lookupReference method to create the lookup form that appears with the **Goal heading** field.

The following steps show how to override the lookupReference method of a field.

1.  In the AOT, expand **Forms**, find and expand the form, expand **Designs**, expand **Design**, and then find the control where you want to use a run-time lookup form.

2.  Note the field name in the **ReferenceField** property of the control. You will override the lookupReference method for this field in the form data source.

3.  Expand **Data Sources**, expand **Fields**, find and expand the field you identified in the previous step. Right-click **Methods**, click **Override method**, and then click **lookupReference**. The **lookupReference** method appears in the code editor.

4.  Comment out the existing contents of the method. If you do not comment out the call to the super method, the standard lookup form might appear. The following code example shows the lookupReference method for a field.
    
        public Common lookupReference(FormReferenceControl _formReferenceControl)
        {
            //Common ret;
            
            //ret = super(_formReferenceControl);
            
            //return ret;
        }

5.  Add code to the lookupReference method that specifies the table you want to use in the lookup form and creates a query object. The following code example adds the HcmWorker table and a query object named lookupQuery.
    
    ``` 
        HcmWorker worker;
        Query lookupQuery;
    ```

6.  Create an instance of the SysReferenceTableLookup class. The SysReferenceTableLookup creates the lookup form that appears when you click the lookup button.
    
    The following code example creates a SysReferenceTableLookup object. Notice how the method parameters associate the HcmWorker table and the **ReferenceGroup** control with the lookup form.
    
    ``` 
        SysReferenceTableLookup sysTableLookup = SysReferenceTableLookup::newParameters(tableNum(HcmWorker), _formReferenceControl, true);
    ```

7.  Specify the fields that appear in the lookup form. The following code examples add the **Name** and **PersonnelNumber** fields from the HcmWorker table.
    
    ``` 
        sysTableLookup.addLookupMethod(“Name”); 
        sysTableLookup.addLookupfield(fieldNum(HcmWorker, PersonnelNumber));
    ```

8.  Use a query to retrieve the records that appear in the lookup form. The following code example uses the query to retrieve a list of workers. Notice how the parmQuery method adds the list to the lookup form.
    
    ``` 
        lookupQuery = new Query();
        lookupQuery.addDataSource(tableNum(HcmWorker)); 
        
        sysTableLookup.parmQuery(lookupQuery);
    ```

9.  Use the peformFormLookup method to open the lookup form. The performFormLookup method returns the selected value from the lookup form. The following code example opens the lookup form and populates the worker object by using the selected record.
    
    ``` 
        worker = sysTableLookup.performFormLookup();
    ```

10. Use return to provide the ID of the selected record to the field in the form data source. The following code example returns the selected worker object to the field in the form data source.
    
    ``` 
        return worker;
    ```

11. Click **Save** and close the code editor.

## To Add a Run-Time Lookup Form for a Natural Foreign Key Field

To add a run-time lookup form to a field that represents a natural foreign key, override the lookup method of the field. You can add a run-time lookup form to a natural foreign key field that is bound to one of the following types of controls:

  - **DateEdit**

  - **GuidEdit**

  - **Int64Edit**

  - **IntEdit**

  - **RealEdit**

  - **StringEdit**

  - **TimeEdit**


> [!WARNING]
> <P>You can also override the lookup method of the control. However, you should only override the lookup method of the control when you want to add a lookup form to an unbound control.</P>



To open the lookup form, call the performDBLookup, performTypeLookup, or performFormLookup method of the control. Each method has parameters that enable you to specify the lookup form.

For example, the **HcmWorker** form overrides the lookup method of the **CalendarId** field of the **WorkerCalendarEmployment** data source. The method uses performFormLookup to specify the lookup form for the field.

The following steps show how to use the performTypeLookup and performFormLookup methods to open the lookup form.

1.  In the AOT, expand **Forms**, find and expand the form, expand **Designs**, expand **Design**, and then find the control where you want to add a custom lookup form.

2.  Right-click the control, click **Properties**, and confirm that the **LookupButton** property is set to **Auto**.

3.  Note the field name in the **DataField** property of the control. You will override the lookup method for this field in the form data source.

4.  Expand **Data Sources**, expand **Fields**, find and expand the field you identified in the previous step. Right-click **Methods**, click **Override method**, and then click **lookup**. The **lookup** method appears in the code editor.

5.  In the code editor, get an instance of the control that is bound to the field. To specify the custom lookup form, call the performTypeLookup method of the control. Use the parameter of the performTypeLookup method to specify the EDT for the foreign key ID that you want to appear in the field.
    

    > [!WARNING]
    > <P>Verify that the <STRONG>FormHelp</STRONG> property of the EDT specifies the form that you want to use as the lookup form for the field.</P>

    
    In the following code example, formStringControl represents a string edit control that is bound to the field. Notice how the **HcmPersonRecId** EDT is passed to the performTypeLookup method. If you view the **FormHelp** property of the **HcmPersonRecId** EDT, you will find that the EDT specifies **HcmPersonLookup** as the lookup form.
    
        public void lookup()
        {
            FormStringControl formStringControl;
            
            formStringControl = element.design().controlname("myStringEditControl");
            formStringControl.performTypeLookup(extendedtypenum(HcmPersonRecId));
        }
    
    If you want to specify a form instead of an EDT, you can use the performFormLookup method. The following code example uses the FormRun object to pass the **CustTable** form to the performFormLookup method. The **CustTable** form will appear when you click the lookup button.
    
        public void lookup()
        {
            FormRun formRun;
            Args args;
            
            args = new Args("CustTable");
            formRun = classFactory::formRunClassOnClient(args);
            formRun.init();
            this.performFormLookup(formRun);
        }

6.  Use the selected record from the lookup form to update the field. To retrieve the ID of the record, you might have to add code to the run or init method of the form that you specified as the lookup form.
    

    > [!IMPORTANT]
    > <P>To use the run method, add the call to selectMode method before the call to the super method. To use the init method, add the call to the selectMode method after the call to the super method.</P>

    
    The following code example adds the selectMode method to the run method of a form. In the example, element represents the calling form. Notice how the parameter for the selectMode method specifies the name of a control. Use the name of the control that contains the ID value that you want to return to the calling form.
    
        Public void run()
        {
            element.selectMode(myIdControl);
            
            super();
        }

7.  Click **Save** and close the code editor.

## See also

[Lookup Forms Overview](lookup-forms-overview.md)

[How to: Add a Control with a Lookup Form](how-to-add-a-control-with-a-lookup-form.md)

[How to: Add a Lookup Form to a Control](how-to-add-a-lookup-form-to-a-control.md)

[How to: Add a Control to a Form](how-to-add-a-control-to-a-form.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

