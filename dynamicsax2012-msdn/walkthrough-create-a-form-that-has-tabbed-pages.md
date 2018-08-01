---
title: 'Walkthrough: Create a Form that Has Tabbed Pages'
TOCTitle: 'Walkthrough: Create a Form that Has Tabbed Pages'
ms:assetid: fd3e193c-ef0a-4680-838e-18aa516abd2d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg865416(v=AX.60)
ms:contentKeyID: 35254207
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Create a Form that Has Tabbed Pages [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To create a form with tabbed pages, you use the AOT to create a **Tab** control as a placeholder for the tabbed page. You then create the tab page that appears in the tab.

## Create the Form

1.  In the AOT, right-click **Forms**, and then click **New Form**. A form is added to the **Forms** node.

2.  Right-click the new form and then click **Properties**. In the **Properties** window, click **Name** and type **MyNewForm**.

## Add a Data Source to the Form

1.  Expand **MyNewForm** so that the **Data Sources** and **Designs** nodes are visible.

2.  Press **Ctrl + D** to open a second AOT.

3.  In the second AOT, expand **AOT** \> **Data Dictionary** \> **Tables** to see the list of tables.

4.  From the second AOT, drag **AssetTable** onto the **Data Sources** node of the form.
    

    > [!NOTE]
    > <P>You can also create a form data source by right-clicking the <STRONG>Data Sources</STRONG> node of <STRONG>MyNewForm</STRONG>, and then clicking <STRONG>New DataSource</STRONG>. Use the <STRONG>Table</STRONG> property to select <STRONG>AssetTable</STRONG>.</P>



5.  Click the data source for the form. In the **Properties** window, click **Name** and type **DataSourceAssetTable**.

## Add Tabs to the Form

1.  Expand the **Designs** and **Design** nodes of **MyNewForm**. Click **Caption** and type **Assets**. The value of the **Caption** property appears in the titlebar of the form.

2.  Click **TitleDatasource** and select **DataSourceAssetTable** from the drop-down list.

3.  Right-click **Design**, click **New Control**, and then click **Tab**.

4.  Click the tab that appears in the **Design** node. In the **Properties** window, click **Width** and select **Column width**. In addition, click **Height** and select **Column height**.

5.  Right-click the **Tab** you added, and then click **New Control** \> **TabPage**. Click the new tab page. In the **Properties** window click **Name** and type **TabPage1**. Click **Caption** and type **Tab Page 1**.
    
    To create a second tab page, repeat this step. Use **TabPage2** for the **Name** and **Tab Page 2** for the **Caption** of the second tab page.

## Add a Data Grid to a Tab Page

You use a grid to list the records from the AssetTable.

1.  Right-click **TabPage1**, click **New Control** and then click **Grid**. A grid appears in the tab page.

2.  Under the **TabPage1** node, click the grid. In the **Properties** window, click **Width** and select **Column width**. Click **Height** and select **Column height**.

3.  In **MyNewForm**, expand **Data Sources** \> **DataSourceAssetTable**. Right-click **Fields** and then click **Open New Window**. The field list opens in a new AOT window.

4.  In the AOT window that list fields, press **Ctrl** and then click **AssetId**, **Name**, **SerialNum**, and **Model**. Drag the highlighted fields to the **Grid** in the **Design** node of **MyNewForm**.

## Add Field Groups to a Tab Page

You use field groups to supply detailed information about the highlighted record that appears in the list on the first tab.

1.  Click **TabPage2** in the **Design** node of **MyNewForm**.

2.  In the AOT window that list fields, press **Ctrl** and then click **Description**, **Inventory**, and **Model** field groups. Drag the highlighted field groups to the **TabPage2**.

3.  To save your changes, right-click the form, and then click **Save**.

## Test the Form

1.  Verify that the **Data Sources** and **Design** nodes of the form match what is shown in the following screen shot
    
    ![Create form](images/Gg865416.AOTFormsCreateTabsForm(en-us,AX.60).jpg "Create form")
    
    **MyNewForm in the AOT**

2.  To view the form, right-click **MyNewForm**, and then click **Open**. The form you see should match the structure in the following image. Your data is probably different depending on the table that you chose for this walkthrough.
    
    ![Run form](images/Gg865416.AOTFormsCreateTabsRun(en-us,AX.60).jpg "Run form")
    
    **The form with output**

## See also

[Customizing Forms by Using the AOT](customizing-forms-by-using-the-aot.md)

[Forms Best Practices](forms-best-practices.md)

[Query Framework in the AOT](query-framework-in-the-aot.md)

[Navigation Forms](navigation-forms.md)

[How to: Add a Part to the FactBox Pane](how-to-add-a-part-to-the-factbox-pane.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

