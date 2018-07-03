---
title: 'How to: Create Queries by Using X++'
TOCTitle: 'How to: Create Queries by Using X++'
ms:assetid: 4f29029a-b39b-4d04-b19f-9524cbcea906
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa638454(v=AX.60)
ms:contentKeyID: 35243499
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create Queries by Using X++ 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you can create a query to retrieve data by using the query classes. For more information, see [Query Object Model](query-object-model.md). In addition, by using X++ code, you can create a query and then save that query to the Application Object Tree (AOT).

You can also create a query by using the AOT. For more information, see [How to: Create Queries by using the AOT](how-to-create-queries-by-using-the-aot.md).

## Create a Query by Using X++

1.  Add a class to the AOT. For more information about adding a class, see [Declaration of Classes](declaration-of-classes.md).

2.  Add a class method that creates a query by using the Query system classes.
    
    In the following example, the QueryRun class runs the query specified by the **q** object. The addDataSource method specifies **CustTable** as the data source for the query. The addRange and value methods specify account numbers between 4000 and 4022. The addSortField method specifies that data is sorted on the **DlvMode** field.
    ```X++  
        public void runMyDynamicQuery2()
        {
            Query q;
            QueryRun qr;
            QueryBuildDataSource qbd;
            QueryBuildRange qbr;
        
            q = new Query();
            qbd = q.addDataSource(TableNum(CustTable));
        
            qbr = qbd.addRange(FieldNum(CustTable, AccountNum));
            qbr.value(">=4000"); // Default operator is ==.
        
            qbr = qbd.addRange(FieldNum(CustTable, AccountNum));
            qbr.value("<=4022");
        
            qbd.addSortField(FieldNum(CustTable, DlvMode));
        
            qr = new QueryRun(q);
            qr.prompt();
        
            pause;
        }
    ```
## Access the Query by Using a Menu Item

1.  Add a main method to the class, and call the method that you created in step 2.

2.  Create an action menu item to reference the class by clicking **Menu Items**, right-clicking **Action**, and then clicking **New Menu Item** in the AOT.

3.  Right-click the menu item, click **Properties**, and set **ObjectType** to **Class**. Then select the class that you created in step 1 from the **Object** property list.
    
    You can include the menu item in forms and reports by configuring form and report controls to reference the menu item. For more information, see [Form Control Properties](form-control-properties.md).

4.  Add your menu item to a menu.  
    For example, expand **AOT** \> **Menus** \> **SystemAdministration** \> **Common**, and then right-click **New** \> **Menu item**. Fill in the properties of the new menu item node.

## Create a Query in the AOT by Using X++

The following procedure is a job that you can run in the AOT to create a query called MyQuery1, provided MyQuery1 does not already exist in the **Queries** node.

1.  In the AOT, right-click **Jobs**, and then click **New Job**. The **Code editor** window opens.

2.  In the **Code editor** window, copy the following code, and then paste it in the **Code editor**.
    ```X++  
        static void CreateQuery6Job(Args _args)
        {
            TreeNode                treeNodeObj;
            Query                   queryObj; // Extends TreeNode class.
            QueryBuildDataSource    qbds;
            QueryBuildRange         qbr;
            QueryRun                qr;
            CustTable               xrecCustTable;
            str                     queryName = "MyQuery1";
            
            // Macro.
            #AOT
        
            // Delete the query from the AOT, if the query exists.
            treeNodeObj = TreeNode::findNode(#QueriesPath);
            treeNodeObj = treeNodeObj.AOTfindChild(queryName);
            if (treeNodeObj) { treeNodeObj.AOTdelete(); }
        
            // Add the query to the AOT.
            treeNodeObj = TreeNode::findNode(#QueriesPath);
            treeNodeObj.AOTadd(queryName);
            queryObj = treeNodeObj.AOTfindChild(queryName);
            
            // Further define the query.
            qbds  = queryObj.addDataSource(tablenum(CustTable));
            qbr   = qbds.addRange(fieldnum(CustTable, DlvMode));
            qbr.value(">10");
        
            // Compile the query.
            queryObj.AOTcompile(1);
            queryObj.AOTsave();
        
            // Run the query.
            qr = new QueryRun("MyQuery1");
            while ( qr.next() )
            {
                xrecCustTable = qr.GetNo(1); // 1 means first data source.
                Global::info(strFmt("%1 , %2",
                    xrecCustTable.AccountNum, xrecCustTable.DlvMode));
            }        
        
            // Delete the query from the AOT.
            treeNodeObj = TreeNode::findNode(#QueriesPath);
            treeNodeObj = treeNodeObj.AOTfindChild(queryName);
            treeNodeObj.AOTdelete();
        }
    ```
3.  Press F7 to compile, and then press F5 to run the job. A query named MyQuery1 is created in the **Queries** node. The query is run, and then is deleted.

## SysQueryRangeUtil Class has Incompatibilities with .NET CIL

In your X++ code, you can use certain methods of the SysQueryRangeUtil class to build query range values that are resolved during run time. One such method is SysQueryRangeUtil::currentWorker(), which is shown in the following code snippet.

  
 QueryBuildRange myQueryBuildRange;   
 //... (More X++ code here) ...   
 myQueryBuildRange.value(queryValue(SysQueryRangeUtil::currentWorker()));   

However, if your X++ code is compiled to .NET Framework CIL, and is then run as CIL, your code might cause an error.

## See also

[Accessing Data](accessing-data.md)

[Customizing the Query Form](customizing-the-query-form.md)

[Using Expressions in Query Ranges](using-expressions-in-query-ranges.md)

[How to: Link Two Forms by Using Dynamic Links](how-to-link-two-forms-by-using-dynamic-links.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

