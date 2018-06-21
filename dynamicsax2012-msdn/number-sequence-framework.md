---
title: Number Sequence Framework
TOCTitle: Number Sequence Framework
ms:assetid: 60fea4ba-c4c0-421e-ad1e-88e3df363c1b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa608474(v=AX.60)
ms:contentKeyID: 35244500
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Number Sequence Framework [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX has a number sequence framework to generate alphanumeric number sequences that are used to identify transaction documents such as sales orders. This topic describes how to implement the number sequence framework for a new module in Microsoft Dynamics AX. The topic will show how a number sequence was implemented for the Facility Management (FCM) sample module. (Some of the following steps might be irrelevant if they have been previously performed for other purposes in your new Microsoft Dynamics AX module.)

For additional information about the number sequence framework for Microsoft Dynamics AX 2012, see the [Number Sequence Framework Whitepaper](http://go.microsoft.com/fwlink/?linkid=213124&clcid=0x409) on the Microsoft Download Center.

## Creating a Parameter Table and a Number Sequence Module Class

The first step to implementing number sequences for a new module is to create a parameter table and a number sequence module class.

1.  Create a parameter table for the new module: MyModuleParameters. For the Facility Management module, this table is named FCMParameters. The table must, at a minimum, contain a Key field and a find method. The delete and update methods must be overridden. These methods can be copied from one of the other parameter tables, such as BOMParameters.

2.  Create an enumerated value that represents all of the number sequences for the module by adding a new element to the NumberSeqModule base enum. For the Facility Management module, the FCM element was added to the base enum.
    

    > [!NOTE]
    > <P>Configuration keys are used to detect the active number sequence references in your Microsoft Dynamics AX installation. If the configuration key is not enabled, the module’s number sequence references are not displayed in the general References form. The user cannot see references from modules that are not enabled.</P>



3.  Create a new number sequence class named NumberSeqModule MyModule. This class must extend the NumberSeqApplicationModule class. For the Facility Management module, this class is named NumberSeqModuleFacilityManagement.

4.  Add the numberSeqModule method to the new number sequence class. This method must return the element for your module from the NumberSeqModule base enum. The following code shows how this is done for the Facility Management module.
    
        public NumberSeqModule numberSeqModule()
        {
           return NumberSeqModule::FCM;
        }

5.  Implement the numberSeqModule method for the parameters table.
    
    Copy this method from one of the other parameter tables such as BOMParameters. Change the return value of the numberSeqModule method so that it references the number sequence for your module.
    
    For example, the numberSeqModule method from the FCMParameters table returns NumberSeqModule::FCM (the FCM element of NumberSeqModule).

6.  Create a form to display the new parameter table.
    
    It is important that the functionality of number sequence references is copied exactly from one of the other parameter forms (for example, CustParameters). Remember to change the names of the called methods.

7.  The new number sequence framework is now established.

## Making Number Sequence Data Types

Next, you will make number sequence data types for the number sequences you are creating for your new module.

1.  In your number sequence module class, override the loadModule method.

2.  In this new method, specify the characteristics of each number sequence data type that you need in the new module. For example, the following code is from the loadModule method of the NumberSeqModuleFacilityManagement class. It defines a number sequence that is used by the Facility Management module to provide work order numbers.
    
        protected void loadModule()
        {
            NumberSeqDatatype datatype = NumberSeqDatatype::construct();
        
            /* Work Order Number */
            datatype.parmDatatypeId(extendedTypeNum(WorkOrderNum));
            datatype.parmReferenceHelp("Unique identifier for work orders");
            datatype.parmWizardIsContinuous(false);
            datatype.parmWizardIsManual(NoYes::No);
            datatype.parmWizardIsChangeDownAllowed(NoYes::No);
            datatype.parmWizardIsChangeUpAllowed(NoYes::No);
            datatype.parmSortField(1);
            datatype.parmWizardHighest(999999);
        
            datatype.addParameterType(NumberSeqParameterType::DataArea, true, false);
            this.create(datatype);
        }


> [!TIP]
> <P>For details about how to set the properties for a data type, see the descriptions of the methods for the <A href="https://msdn.microsoft.com/en-us/library/gg745013(v=ax.60)">NumberSeqDatatype Class</A>.</P>



## Loading Number Sequence Information for a Module

After you create the number sequence module class and define the number sequence data types for your module, you must load the number sequence information into Microsoft Dynamics AX. This must be done only one time. Typically, this is a step that is performed when the module is installed.

A simple way to load the number sequence information for a module is to create a job in the AOT that creates an instance of the number sequence module and runs the loadModule() method. The following example is the InstallFacilityManagement job in the AOT. It creates an instance of the NumberSeqModuleFacilityManagement class, and then calls the loadModule() method. The job must be run only one time by the person who is installing the Facility Management module.

    static void InstallFacilityManagement(Args _args)
    {
        NumberSeqModuleFacilityManagement n = new NumberSeqModuleFacilityManagement();
    
        n.loadModule();
    }

## Generating Number Sequences

After the number sequence information has been loaded for the module, you must use the **Set up number sequences** wizard to generate the number sequences that you defined.

1.  In the Microsoft Dynamics AX client, choose **Organization administration** \> **Common** \> **Number sequences** \> **Number sequences**.

2.  Click **Generate** to open the **Set up number sequences** wizard.

3.  Complete the wizard to create the number sequences for your new module.

## Accessing Your New Number Sequence Data Types

For each data type specified in NumberSeqModule MyModule .loadModule, you must create a static method on your parameter table. Create the MyModule Parameters::numRef MyDataType method.

1.  Copy a numRef method from one of the other parameter tables.

2.  Change the name of the method to numRef MyDataType.

3.  Add code that will return a number sequence reference object for that specific data type. For example, the following method retrieves the number sequence reference object that is used for the WorkOrderNum field. This is the number sequence that is defined for the Facility Management sample application.
    
        client server static NumberSequenceReference numRefWorkOrderNum()
        {
            NumberSeqScope scope = NumberSeqScopeFactory::createDataAreaScope(curext());
            return NumberSeqReference::findReference(extendedtypenum(WorkOrderNum), scope);
        }

## Using Number Sequences in an Application

To use the number sequence for a form in Microsoft Dynamics AX or in Enterprise Portal, you will typically add code to the data source for the form or data set. You can also retrieve a number sequence value directly in code. For example, the following example retrieves the next available work order number from the number sequence used for the WorkOrderNum field and displays it in the Infolog.

    Info(NumberSeq::newGetNum(FCMParameters::numRefWorkOrderNum()).num());

### ![Aa608474.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa608474.collapse_all(en-us,AX.60).gif") Forms

To use a number sequence for a form in Microsoft Dynamics AX, follow these steps.

1.  In the classDeclaration method of the form that will be accessing data, add a variable declaration for the number sequence handler. The following example shows the variable definition for a number sequence handler.
    
        public class FormRun extends ObjectRun
        {
            NumberSeqFormHandler numberSeqFormHandler;
        }

2.  Add the NumberSeqFormHandler method to the form. The code in this method will create an instance of the number sequence form handler and return it. The following example shows the code that returns the number sequence form handler for the FCMWorkOrders form of the Facility Management sample module.
    
        NumberSeqFormHandler numberSeqFormHandler()
        {
            if (!numberSeqFormHandler)
            {
                numberSeqFormHandler = NumberSeqFormHandler::newForm(
                    FCMParameters::numRefWorkOrderNum().NumberSequenceId,
                     element,
                     FCMWorkOrders_DS,
                     fieldnum(FCMWorkOrders, WorkOrderNum)); 
            }
            return numberSeqFormHandler;
        }

3.  Add create, delete, and write methods to the data source of the table that contains the field for which the number sequence is being used. The following code examples show these methods that are added to the data source for the FCMWorkOrders table to support the number sequence for the WorkOrderNum field.
    
        public void create(boolean _append = false)
        {
            element.numberSeqFormHandler().formMethodDataSourceCreatePre();
            super(_append);
            element.numberSeqFormHandler().formMethodDataSourceCreate();
        }
        
        public void delete()
        {
            element.numberSeqFormHandler().formMethodDataSourceDelete();
            super();
        }
        
        public void write()
        {
            super();
            element.numberSeqFormHandler().formMethodDataSourceWrite();
        }

### ![Aa608474.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa608474.collapse_all(en-us,AX.60).gif")Enterprise Portal

To use a number sequence for a form in Enterprise Portal, follow these steps.

1.  In the classDeclaration method of the data set that will be accessing data, add a variable declaration for the number sequence handler. The following example shows the variable definition for a number sequence handler.
    
        public class DatSetRun extends ObjectRun
        {
            NumberSeqFormHandler numberSeqFormHandler;
        }

2.  Add the NumberSeqFormHandler method to the data set. The code in this method will create an instance of the number sequence form handler and return it. The following example shows the code that returns the number sequence form handler for the FCMWorkOrderAddEdit data set of the Facility Management sample module.
    
        NumberSeqFormHandler numberSeqFormHandler()
        {
            if (!numberSeqFormHandler)
            {
                numberSeqFormHandler = NumberSeqFormHandler::newForm(
                    FCMWorkOrders::numRefFCMWorkOrders().NumberSequenceId,
                    element,
                    FCMWorkOrders_DS,
                    fieldnum(FCMWorkOrders, WorkOrderNum));
            }
            return numberSeqFormHandler;
        }

3.  Add create, delete, and write methods to the data source for the data set that contains the field for which the number sequence is being used. The following code examples show these methods that are added to the data source for the FCMWorkOrders table to support the number sequence for the WorkOrderNum field.
    
        public void create(boolean _append = false)
        {
            element.numberSeqFormHandler().formMethodDataSourceCreatePre();
            super(_append);
            element.numberSeqFormHandler().formMethodDataSourceCreate();
        }
        
        public void delete()
        {
            element.numberSeqFormHandler().formMethodDataSourceDelete();
            super();
        }
        
        public void write()
        {
            element.numberSeqFormHandler().formMethodDataSourceWrite();
            super();
        }

## See also

[Number sequences in Microsoft Dynamics AX](https://msdn.microsoft.com/en-us/library/hh209291\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

