---
title: 'How to: Add a Lookup Form to a Control'
TOCTitle: 'How to: Add a Lookup Form to a Control'
ms:assetid: 67fa4464-b782-4c62-a09b-0124a2076b28
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh185372(v=AX.60)
ms:contentKeyID: 35589744
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a Lookup Form to a Control [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use X++ to add a lookup form to a control. To create a custom lookup form, you override the lookup method of the control. You can then create a query and lookup form you can use to populate the control. However, the lookup that appears is associated only with the specified control and is not available to any other control or form.


> [!NOTE]
> <P>To add a lookup form to a <STRONG>ReferenceGroup</STRONG> control, use the lookupReference method for the control. The lookup method of the <STRONG>ReferenceGroup</STRONG> control is not used.</P>



The following section shows how to override the lookup method of a **StringEdit** control and how to use the SysTableLookup class to create a lookup form.

## To Add a Lookup Form to a StringEdit Control

1.  In the AOT, expand **Forms**, expand the form, expand **Designs**, right-click **Design**, click **New Control**, and then click **StringEdit**. A **StringEdit** control is added to the form.

2.  Right-click the control, and then click **Properties**. Review the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>DataField</strong></p></td>
    <td><p>If you want to bind the control to a field in the form data source, select the name of the field.</p>
    
    > [!note]  
    > <P>To see a list of fields, set the <strong>DataSource</strong> property before you view the <strong>DataField</strong> list.</P>
    
    </td>
    </tr>
    <tr class="even">
    <td><p><strong>DataSource</strong></p></td>
    <td><p>If you want to bind the control to a field in the form data source, select the name of the table that contains the field.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Label</strong></p></td>
    <td><p>Select a label that describes the information that appears in the control.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name that uniquely identifies the control.</p></td>
    </tr>
    </tbody>
    </table>


3.  Expand the control, right-click **Methods**, click **Override method**, and then click **lookup**. The lookup method opens in the code editor.

4.  In the code editor, add Query, QueryBuildDataSource, and QueryBuildRange objects. The following code example adds the classes you use to construct the query for the lookup form.
    ```X++  
        public void lookup()
        {
            Query query = new Query();
            QueryBuildDataSource queryBuildDataSource;
            QueryBuildRange queryBuildRange; 
    ```
5.  Create an instance of SysTableLookup class. The following code example creates a lookup form for customers. Notice how this in the example represents the current form control.
    
    ```X++  
        SysTableLookup sysTableLookup = SysTableLookup::newParameters(tableNum(custTable), this); 
    ```

6.  Use the addLookupField method to specify the fields that appear in the lookup form. The following code example adds the **AccountNum** and **CustGroup** fields to the lookup form.
    
    ```X++  
        sysTableLookup.addLookupField(fieldNum(CustTable, AccountNum));
        sysTableLookup.addLookupField(fieldNum(CustTable, CustGroup)); 
    ```

7.  Use a query to retrieve data for the lookup form. The following code example uses a range limit so that the lookup form lists customers who have the customer group of 40.
    
    ```X++  
        queryBuildDataSource = query.addDataSource(tableNum(CustTable));
    
        queryBuildRange = queryBuildDataSource.addRange(fieldNum(CustTable, CustGroup));
        queryBuildRange.value('40');
    
        sysTableLookup.parmQuery(query);
    ```

8.  Use the performFormLookup method to open the lookup form.
    
    ```X++  
        sysTableLookup.performFormLookup();
    ```

9.  When you override the lookup method, comment out the call to super. If you do not comment out the call to super, the standard lookup form might appear.
    
    ```X++  
        //super();
    }
    ```

10. Right-click the form and then click **Save**. To see the lookup form, right-click the form and then click **Open**. Find the **StringEdit** control and then click the arrow to open the lookup form.

The following code example shows the complete lookup method for customers:
```X++  
    public void lookup()
    {
        Query query = new Query();
        QueryBuildDataSource queryBuildDataSource;
        QueryBuildRange queryBuildRange; 
    
        SysTableLookup sysTableLookup = SysTableLookup::newParameters(tableNum(custTable), this); 
    
        sysTableLookup.addLookupField(fieldNum(CustTable, AccountNum));
        sysTableLookup.addLookupField(fieldNum(CustTable, CustGroup)); 
    
        queryBuildDataSource = query.addDataSource(tableNum(CustTable));
    
        queryBuildRange = queryBuildDataSource.addRange(fieldNum(CustTable, CustGroup));
        queryBuildRange.value('40');
    
        sysTableLookup.parmQuery(query);
    
        sysTableLookup.performFormLookup();
    
        //super();
    }
```
## See also

[Lookup Forms Overview](lookup-forms-overview.md)

[How to: Add a Control with a Lookup Form](how-to-add-a-control-with-a-lookup-form.md)

[How to: Add a Run-Time Lookup Form](how-to-add-a-run-time-lookup-form.md)

[Methods on Form Controls](methods-on-form-controls.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

