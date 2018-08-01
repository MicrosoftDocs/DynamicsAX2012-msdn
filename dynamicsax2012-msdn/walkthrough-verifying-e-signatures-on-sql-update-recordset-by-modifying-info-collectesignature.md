---
title: 'Walkthrough: Verifying E-signatures on SQL update_recordset by Modifying Info .collectESignature'
TOCTitle: 'Walkthrough: Verifying E-signatures on SQL update_recordset by Modifying Info .collectESignature'
ms:assetid: 4fc538e2-8e64-4650-a105-c14fc62c42a2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc589558(v=AX.60)
ms:contentKeyID: 35243511
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Verifying E-signatures on SQL update\_recordset by Modifying Info .collectESignature [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

As a partner who builds enhancements into installations of Microsoft Dynamics AX, you can use the kernel event that calls the Info.collectESignature method. The method can be called when any kind of data modification is made to any table (such as with [insert\_recordset](insert-recordset.md)). Your code inside the collectESignature method must handle electronic signature (e-signature) processing for the data modification.

This walkthrough describes the following tasks:

  - Modifying the Info .collectESignature method

  - Inserting into the DatabaseLog table

  - Gathering information for the SysSignatureSetup table

  - Inserting into the SysSignatureSetup table

  - Raising the event by updating a table

## Prerequisites

To complete this walkthrough, you need:

  - Microsoft Dynamics AX

  - A license file that has access to the MorphX development environment

## Modifying the Info.collectESignature Method

In this procedure you override the collectESignature method. You must put in code that verifies that e-signature requirements have been met. The sample given in this procedure is placeholder logic for the demonstration.

### To modify the Info.collectESignature method

  - In the AOT, expand the **Classes** node, and then expand the **Info** node.


> [!TIP]
> <P>The node for the <STRONG>Info</STRONG> class might not be in the expected alphabetical location. It might be near the bottom of the <STRONG>Classes</STRONG> nodes.</P>



1.  Right-click the method node **collectESignature**, and then select **View Code**. This starts a code editor window.

2.  In the code editor window, write the X++ code that is shown in the sample.

3.  Save the code. Press F7 to compile the code.
    
       ```X++
       boolean collectESignature(DatabaseLogType _logType, Common _record)
        {
            DictEnum dEnum;
            ;
        
            dEnum = new DictEnum(enumNum(DatabaseLogType));
        
            info(strFmt(
                "ESignature required for table '%1' (%2) , for the '%3' (%4) operation."
                , tableid2name(_record.TableId)
                , _record.TableId
                , enum2str(_logType)
                , dEnum.name2Value(enum2Str(_logType))
                ));
        
            return true;
        }
       ```

## Inserting Into the DatabaseLog Table

In this procedure you use the **Navigation Pane** to add a row to the DatabaseLog table. This row tells Microsoft Dynamics AX to log updates to the CustTable table.

### To insert into the DatabaseLog table

1.  In the **System Administration** module, under Setup, expand **Database** and click **Database log setup**. The **Database log setup** form is displayed.

2.  In the form, press Ctrl+N or click the **New** button to add a new record. The **Logging database changes** wizard is displayed.

3.  In the wizard, click **Next**. In the page now displayed, expand **Bank**, select the **Bank Accounts** check box, and then click **Next**. In the **Bank Accounts** row, select the check box that is in the **Update** column. Click **Next**, and then click **Finish**.

4.  Close the client, and then restart the client. This refreshes the metadata in the client.

## Gathering Information for the SysSignatureSetup Table

In this procedure you must gather the following information:

  - The int value for the DatabaseLogType enum value that matches the **Update** choice you made in the DatabaseLog table wizard task.

  - The table ID of the table that is being used in this walkthrough, which is the BankAccountTable.

  - The RecId for the row you added to the DatabaseLog table in the wizard.

### ![Cc589558.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc589558.collapse_all(en-us,AX.60).gif")The DatabaseLogType Enum Value

You can find the int value for a given enum value by looking in the AOT.

### To gather the DatabaseLogType enum value

1.  In the AOT, expand **System Documentation**, expand **Enums**, and then expand the node for the **DatabaseLogType** enum.

2.  Count the list of enum values, assigning 0 (zero) to the first item (**Insert**), and increment by one as you continue through the list.


> [!NOTE]
> <P>Note the int value for <STRONG>Update</STRONG> is 2.</P>



### ![Cc589558.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc589558.collapse_all(en-us,AX.60).gif")The Table ID Value

You can use the function tableName2Id to find the table ID for the CustTable.

### To gather the table ID value

1.  In the AOT, right-click the **Jobs** node, and then select **New Job**. The code editor window appears.

2.  In the code editor, enter the following X++ code:
    
       ```X++
       static void Job1(Args _args)
        {
            ;
            Info(strFmt("%1" ,tableName2Id("BankAccountTable")));
        /***  Example Infolog output
        Message (03:13:56 pm)
        7
        ***/
        }
       ```

3.  Save the code.

4.  Press F7 to compile your job, and then press F5 to run the job.

5.  Make a note of the table ID that you find in the **Infolog** window.

### ![Cc589558.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc589558.collapse_all(en-us,AX.60).gif")The RecId Value

You can run an X++ job to find the RecId for the target row from the DatabaseLog table.

### To gather the RecId value

1.  In the AOT, right-click the **Jobs** node, and then select New Job. A code editor appears.

2.  In the code editor, enter the following X++ code:
    
       ```X++
       static void DatabaseLogTableLookups44Job(Args _args)
        {
            DatabaseLog dablogTable;
            ;
            while select * from dablogTable
                where
                dablogTable .logTable == 77 // 'CustTable'
                && dablogTable .logType == 2 // 'Update'
            {
                info(strFmt("%1 %2: %3"
                    , dablogTable.logTable
                    , dablogTable.logType
                    , dablogTable.RecId
                    ));
            }
        /********  Actual Infolog output
        Message (03:26:07 pm)
        7 Update: 5637144576
        ********/
        }
       ```

3.  If necessary, change the where clause values in the job code. For example, the VendTable has a different table ID than the 7 shown in the example.

4.  Save the code.

5.  Press F7 to compile your job, and then press F5 to run the job.

6.  Make a note of the RecId number that you find in the **Infolog** window.

## Inserting Into the SysSignatureSetup Table

In the procedure you add a row to the SysSignatureSetup table, for the RecId value that you obtained in the previous task. This row is detected by the kernel every time when the BankAccountTable is updated. It causes the kernel to call the Info.collectESignature method.

### To insert into the SysSignatureSetup table

1.  In the AOT, expand the **Data Dictionary** node, and then expand **Tables**.

2.  Right-click the **SysSignatureSetup** table node, and then select **Open**. A table browser window appears.

3.  Press Ctrl+N to create a new line entry that you can edit.

4.  Click the cell in the **LogRecRefId** column. A drop-down list box is displayed.

5.  In the **LogRedRefId** drop-down list box, select the value that matches the RecId you gathered in the previous task.

6.  Select the check box in the **SignatureControlled** column. Otherwise the kernel skips this row when it determines whether to call collectESignature.

7.  Press Ctrl+S to save the new record. Close the table browser.

8.  Close the client, and then start a new client. This repopulates the client cache from **SysSignatureSetup**.

## Raising the Event by Updating a Table

In this procedure you update the BankAccountTable. This causes the kernel to run the collectESignature method. You can view the effects in the **Infolog**.

### To raise the event by updating a table

1.  In the AOT, expand the **Data Dictionary** node, and then expand **Tables**.

2.  Right-click the **BankAccountTable** node, and then select **Open**. A table browser window appears.

3.  In the table browser, click in any non-blank cell in the **CellularPhone** column. Change any digit, and then press Ctrl+S to update the database. The **Infolog** window is displayed containing the following.
    
      
     ESignature required for table 'BankAccountTable' (7) , for the 'Update' (2) operation.   
     Transaction does not contain a required signature.

4.  Verify the information in the **Infolog** is from the collectESignature method.

## Next Steps

Only a partner or other major Microsoft Dynamics AX developer should consider editing the Info.collectESignature method. The primary purpose of an e-signature is to prevent someone from denying that they earlier took a specific action. You should research the business and legal aspects of electronic signing before you can design an e-signature subsystem.

## See also

[Data Integrity](data-integrity.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

