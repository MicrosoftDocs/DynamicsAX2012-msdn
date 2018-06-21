---
title: 'How to: Add a Segmented Entry Control to a Form'
TOCTitle: 'How to: Add a Segmented Entry Control to a Form'
ms:assetid: 9c8193db-0d82-4fcd-a1ed-314a8cef812c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh300644(v=AX.60)
ms:contentKeyID: 36595194
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a Segmented Entry Control to a Form [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use a segmented entry control to view or update an account number from the chart of accounts. You use the LedgerDimensionAccountController class to provide the actions that are used with this kind of account. For more information about how to add multi-segment account numbers to forms, see [Segmented Entry](segmented-entry.md). The following sections describe how to add a data source for a segmented entry control, how to add the control, and then how to add actions.

### To Add the Data Source to the Form

1.  In the AOT, expand **Forms**. Find and expand the form where you want to add a financial account field. Expand the **Data Sources** node of the form.

2.  Press Ctrl + D to open a second AOT. Expand **Data Dictionary**, expand **Tables**, and then click the table that contains the field you want to appear on the form.
    

    > [!IMPORTANT]
    > <P>When you bind the field to a segmented entry control, you should verify that the <STRONG>ExtendedDataType</STRONG> property of the field is set to <STRONG>LedgerDimensionAccount</STRONG>. In addition, you should verify that the field is part of a table relation to the <STRONG>DimensionAttributeValueCombination</STRONG> table.</P>



3.  Drag the table to the **Data Sources** node of the form. The table is added to the form data sources.

### To Add the Segmented Entry Control to the Form

1.  Expand the **Designs** node of the form.

2.  Expand the **Data Sources** node of the form, expand the table, expand **Fields**, and then drag the field that represents the multi-segment account number to the **Design** node of the form. A segmented entry control is added to the form.
    
    You can also right-click **Design**, click **New Control**, click **SegmentedEntry**, and then populate the DataSource and ReferenceField properties of the control.

### To Add Actions to the Segmented Entry Control

1.  Expand the **Methods** node of the form, right-click **ClassDeclaration**, and then click **View Code**. The method opens in the code editor. Add an instance of the [LedgerDimensionAccountController](https://msdn.microsoft.com/en-us/library/gg764214\(v=ax.60\)) class to the form. The following code example adds a declaration for the class.
    
        public class FormRun extends ObjectRun
        {
            LedgerDimensionAccountController ledgerDimensionAccountController;
        }

2.  Right-click the **Methods** node of the form, click **Override method**, and then click **init**. The init method opens in the code editor. Create an instance of the LedgerDimensionAccountController class and specify the data source and field that you want to associate with the segmented entry control.
    
    The following code example instantiates the class. Notice how the parameters specify the [LedgerJournalTrans](https://msdn.microsoft.com/en-us/library/gg860017\(v=ax.60\)) table as the data source and LedgerDimension as the field.
    
        public void init()
        {
            super();
            
            ledgerDimensionAccountController = LedgerDimensionAccountController::construct(LedgerJournalTrans_DS, fieldstr(LedgerJournalTrans, LedgerDimension));
        }

3.  Expand the **Data Sources** node of the form, expand the data source table, expand **Fields**, and then expand the field that you want to appear on the form. Right-click **Methods**, click **Override method**, and then click **resolveReference**. The method opens in the code editor. Replace the existing code in the method with a call to the resolveReference method of the LedgerDimensionAccountController class.
    
    The following code example overrides the resolveReference method of the field. Notice how comments are used to remove the existing code.
    
        public Common resolveReference(FormReferenceControl _formReferenceControl)
        {
            //Common ret;
            
            //ret = super(_formReferenceControl);
            
            //return ret,
            
            return ledgerDimensionAccountController.resolveReference();
        }

4.  Expand the **Design** node of the form, expand the segmented entry control that you added, right-click **Methods**, click **Override method**, and then click **jumpRef**. The jumpRef method opens in the code editor. Add a call to the jumpRef method of the LedgerDimensionAccountController class.
    
    The following code example shows how to override the jumpRef method of the control.
    
        public void jumpRef()
        {
            ledgerDimensionAccountController.jumpRef();
            
            super();
        }

5.  Right-click **Methods** of the segmented entry control, click **Override method**, and then click **loadAutoCompleteData**. The loadAutoCompleteData method opens in the code editor. Add a call to the loadAutoCompleteData method of the LedgerDimensionAccountController class.
    
    The following code example shows how to override the loadAutoCompleteData method of the control. Notice how the loadAutoCompleteData method of the LedgerDimensionAccountController uses the input parameter of the control method.
    
        Public void loadAutoCompleteData(loadAutoCompleteDataEventArgs _e)
        {
            super(_e);
            
            ledgerDimensionAccountController.loadAutoCompleteData(_e);
        }

6.  Right-click the **Methods** node of the segmented entry control, click **Override method**, and then click **loadSegments**. The loadSegments method opens in the code editor. Add a call to the parmControl, parmDimensionAccountStorageUsage, and loadSegments methods of the LedgerDimensionAccountController class.
    
    The following code example overrides the loadSegments method of the control. Notice the use of the parmControl method. You use this method to bind the instance of the LedgerDimensionAccountController class to the segmented entry control.
    
        public void loadSegments()
        {
            super();
            
            ledgerDimensionAccountController.parmControl(this);
            ledgerDimensionAccountController.loadSegments();
        }

7.  Right-click the **Methods** node of the segmented entry control, click **Override method**, and then click **segmentValueChanged**. The segmentValueChanged method opens in the code editor. Add a call to the segmentValueChanged method of the LedgerDimensionAcccountController class.
    
    The following code example shows how to override the segmentValueChanged method of the control. Notice how the segmentValueChanged method of the LedgerDimensionAccountController class uses the input parameter of the control method.
    
        public void segmentValueChanged(SegmentValueChangedEventArgs _e)
        {
            super(_e);
            
            ledgerDimensionAccountController.segmentValueChanged(_e);
        }

8.  Right-click the **Methods** node of the segmented entry control, click **Override method**, and then click **validate**. The validate method opens in the code editor. Add a call to the validate method of the LedgerDimensionAccountController class. The following code examples shows how to override the validate method of the control.
    
        public boolean validate()
        {
            boolean ret;
            
            ret = super();
            
            ret = ledgerDimensionAccountController.validate() && ret;
            
            return ret;
        }

9.  Save the form and close the code editor.

## See also

[LedgerDimensionAccountController](https://msdn.microsoft.com/en-us/library/gg764214\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

