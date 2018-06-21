---
title: 'Walkthrough: Creating a Form by Using the AOT'
TOCTitle: 'Walkthrough: Creating a Form by Using the AOT'
ms:assetid: c13ff73a-9512-4441-9257-dfe163a6aece
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg879955(v=AX.60)
ms:contentKeyID: 35250083
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Creating a Form by Using the AOT [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the AOT to create a form. This topic describes how to create a form that lists assets from the **AssetTable** table.

## Create the Form

1.  In the AOT, right-click **Forms**, and then click **New Form**. A form is added to the **Forms** node.

2.  Right-click the new form and then click **Properties**. In the **Properties** window, click **Name** and then type **MyNewForm**.

## Add a Data Source to the Form

1.  Expand **MyNewForm** so that the **Data Sources** and **Designs** nodes are visible.

2.  Press **Ctrl + D** to open a second AOT.

3.  In the second AOT, expand **AOT** \> **Data Dictionary** \> **Tables** to see the list of tables.

4.  From the second AOT, drag **AssetTable** onto the **Data Sources** node of the form.
    

    > [!NOTE]
    > <P>You can also create a form data source by right-clicking the <STRONG>Data Sources</STRONG> node of <STRONG>MyNewForm</STRONG>, and then clicking <STRONG>New DataSource</STRONG>. Use the <STRONG>Table</STRONG> property to select <STRONG>AssetTable</STRONG>.</P>



5.  Click the data source for the form. In the **Properties** window, click **Name** and type **DataSourceAssetTable**.

## Add a Grid and Fields to the Form

1.  Expand the **Designs** and the **Design** node of **MyNewForm**. In the properties window, click **Caption** and type **Assets**. The value in the **Caption** property appears in the titlebar of the form.

2.  Click **TitleDatasource** and select **DataSourceAssetTable** from the drop-down list.

3.  Right-click **Design**, click **New Control**, and then click **Grid**.

4.  Click the grid in the **Design** node. In the **Properties** window, click **Width** and select **Column width**. Click **Height** and select **Column height**.

5.  Expand the **Data Sources** \> **DataSourceAssetTable** \> **Fields** node of **MyNewForm**. Right-click **Fields** and then click **Open New Window**. The field list opens in a new AOT window.

6.  In the AOT window that list fields, press Ctrl and then click **AssetId**, **Name**, **SerialNum**, and **Model**. Drag the highlighted fields to the **Grid** in the **Design** node of **MyNewForm**.

## Add a Button to the Form

In this section you add a button control to the form. The button shows a list of assets based on the insured value of the asset. To create and show the list, you override the **clicked** method of the button control.

1.  Right-click **Design**, click **New Control**, and then click **Button**.

2.  In the **Properties** window, click **Text** and type **Display Assets**.

3.  Expand the node for the new button, right-click **Methods**, click **Override method**, and then click **clicked**.

4.  Right-click the **clicked** node, and then click **View Code**. The clicked method opens in the code editor.

5.  Copy the following example code, paste the code into the **Editor** window.
    
        void clicked()
        {
            AssetTable assetTable;
            while select assetTable order by AssetId
                where assetTable.InsuredValue < 1000000
                    && assetTable.InsuredValue >= 800
            {
                info(strFmt("%1 %2", assetTable.AssetId, assetTable.Name));
            }
        
            super();
        }

6.  Click the **Save** button and then close the editor.

7.  To save your changes, right-click the form, and then click **Save**.

## Test the Form

1.  Verify that the **Data Sources** and **Design** nodes of the form match what is shown in the following screen shot.
    
    ![Create form](images/Gg879955.AOTFormsCreate(en-us,AX.60).jpg "Create form")
    
    **MyNewForm in the AOT**

2.  To view the form, right-click the **MyNewForm**, and then click **Open**. Click the **Display assets** button on the form. The form and the code output to the **Infolog** are shown in the following image.
    
    ![Running form](images/Gg879955.AOTFormsCreateCode(en-us,AX.60).jpg "Running form")
    
    **The form with output**

## See also

[Customizing Forms by Using the AOT](customizing-forms-by-using-the-aot.md)

[Forms Best Practices](forms-best-practices.md)

[Query Framework in the AOT](query-framework-in-the-aot.md)

[Navigation Forms](navigation-forms.md)

[How to: Add a Part to the FactBox Pane](how-to-add-a-part-to-the-factbox-pane.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

