---
title: Selecting Data from a Table Inheritance Hierarchy
TOCTitle: Selecting Data from a Table Inheritance Hierarchy
ms:assetid: cb99509d-3969-405e-a2a0-4367a8700ade
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg881064(v=AX.60)
ms:contentKeyID: 35251459
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Selecting Data from a Table Inheritance Hierarchy [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic explains how you can maximize the efficiency of your operations that read data from tables that are related through inheritance.

This topic describes the interaction between the following:

  - Fields that are named in the X++ select field list, and

  - Field locations within the table inheritance hierarchy.


> [!NOTE]
> <P>The physical implementation of table inheritance in the underlying Microsoft SQL Server database might vary between versions of Microsoft Dynamics AX. Direct Transact-SQL Select statements that successfully read from inheritance tables in one release might fail in the next release.</P>



## Diagram of Example Table Hierarchy

The following diagram describes the inheritance hierarchy among the example tables that are used in this topic.

The Party table is the root base table. Each arrow points from a derived table to its base table. For all of these tables, their **Abstract** property value is **No**. For example, that means that a record in the Organization table does not necessarily have a corresponding row in either of its derived tables Nonprofit and Government.

![Table inheritance from the Party base table.](images/Gg881064.Party-Org-Nonprofit_TableHierarchy(en-us,AX.60).gif "Table inheritance from the Party base table.")

 

**Table inheritance hierarchy from the Party base table**

## X++ Select Fields Specified by Asterisk

One way to specify the fields to be returned from an X++ select statement is to use the asterisk (\*) character. For example:

select \* from tabOrganzation;

### ![Gg881064.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg881064.collapse_all(en-us,AX.60).gif")Asterisk Reads All Base and Target Fields

The asterisk in select \* from tabOrganization; means that all fields from the Party table are read. If Party had a base table, all fields from that other base table would be read also.

The target table in the example is Organization. All fields from the target table are also read.

### ![Gg881064.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg881064.collapse_all(en-us,AX.60).gif")Asterisk Reads All Derived Fields

The asterisk in the select example means that all fields from any tables that derive from the target table are also read. In the present example, if a given record is a government organization, the field Government.AgencyDescription is read. But for that record the field Nonprofit.AnnualContribution is not read.


> [!NOTE]
> <P>Sometimes the asterisk is called a dynamic field list. There is a corresponding property that is named Dynamic on the <STRONG>AOT</STRONG> &gt; <STRONG>Queries</STRONG> &gt; MyQuery &gt; <STRONG>Data Sources</STRONG> &gt; MyDatasource &gt; <STRONG>Fields</STRONG> node.</P>



### ![Gg881064.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg881064.collapse_all(en-us,AX.60).gif")Downcasting is Sometimes Necessary

You must downcast the target table variable to the derived table type in order to access the value of fields on derived tables.

The downcast is also necessary in order to call any method that is declared on only the derived table.

However, suppose the target table has a method that a derived table overrides. When the current record is of that derived table type, a call to the same method name on the target table variable invokes the version of the method that is defined on the derived table.

## X++ Select Fields Specified by Name

The desired fields can be explicitly named on a select statement. For example:

select NickName, NumEmployees from tabOrganization;

This select statement does not specify any fields from the tables that derive from the Organization table. Therefore, any attempt by the code to obtain data from a field such as Government.AgencyDescription fails. It fails regardless of whether any successful downcast has occurred.

### ![Gg881064.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg881064.collapse_all(en-us,AX.60).gif")Efficiency and Performance

Explicit naming of the fields on a select statement can be much more efficient than use of an asterisk where table inheritance hierarchies are involved. An asterisk forces the system to join every derived table into the select. If you do not need fields from the derived tables, you can avoid those extra joins by explicitly naming only those base and target table fields that you know you need.

### ![Gg881064.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg881064.collapse_all(en-us,AX.60).gif")Downcasting is Possible Even if No Derived Fields are Selected

The example select statement does not return any fields from tables that derive from the Organization target table. Yet some of the selected records are probably of the Government or Nonprofit derived types. Therefore, when the current record is of type Government, you can downcast the target table variable tabOrganization to the Government type.

The downcast enables you call methods that are defined on only the Government table. But the downcast does not enable you to reference the fields of the Government table at run time and get data from them.

## X++ Select Code Example

The following code example reads from the Party table. The select statement specifies an asterisk for the field list.

The code example performs the following operations:

1.  // Declare the variables.

2.  // Discard all previous records.

3.  // Insert records.

4.  // Loop through all records.
    
      - // Read from: Party.
    
      - // Read from: Organization.
    
      - // Read from: Nonprofit.
    
      - // Read from: Government.

### ![Gg881064.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg881064.collapse_all(en-us,AX.60).gif")Typical Snippet of a Downcast

The following code snippet is from the full code example. This snippet is for the Government table, and the full code example has similar sections for the other tables. This snippet performs the following steps:

1.  Asks whether the current record is a Government record. The system can discover the answer by accessing the Party.InstanceRelationType field.

2.  If it is a Government record, a downcast to the Government type is performed.

3.  Finally the tabGovt variable is able to access the field that is on the Government table.

<!-- end list -->

``` 
        // Read from: Government.
        if (tabParty is Government)
        {
            tabGovt = tabParty as Government;

            info(strFmt("%1 == tabGovt.AgencyDescription",
                tabGovt.AgencyDescription));
        }
```

### ![Gg881064.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg881064.collapse_all(en-us,AX.60).gif")Full Code Example

Here is the full code example.

    static void GmJob2TableDowncast(Args _args)
    {
        // Declare the variables.
        Party        tabParty;
        Organization tabOrg;
        Government   tabGovt;
        Nonprofit    tabNonprofit;
    
    
        // Discard all previous records.
        delete_from tabParty;
    
    
        // Insert records.
        tabNonprofit.NickName = "Alison_NPF";
        tabNonprofit.NumEmployees = 31;
        tabNonprofit.AnnualContribution = 111.22;
        tabNonprofit.insert();
    
        tabGovt.NickName = "Ben_GOV";
        tabGovt.NumEmployees = 42;
        tabGovt.AgencyDescription = "Taxes";
        tabGovt.insert();
    
        tabOrg.NickName = "Carl_ORG";
        tabOrg.NumEmployees = 53;
        tabOrg.insert();
    
        tabParty.NickName = "David_PRY";
        tabParty.insert();
    
    
        // Loop through all records.
        while
            select
                from tabParty
                order by NickName
        {
            info("_ _ _ _ _ _ _ _ _ _ _ _");
            info(" ");
    
            // Read from: Party.
            if (tabParty is Party)
            {
                tabParty = tabParty as Party;
                // Every derived table overrides this method.
                tabParty.shoutTableNameToInfolog();
    
                info(strFmt("%1 == tabParty.NickName",
                    tabParty.NickName));
                info(strFmt("%1 == tabParty.InstanceRelationType",
                    tabParty.InstanceRelationType));
                info(strFmt("%1 == tabParty.RecId",
                    tabParty.RecId));
            }
    
            // Read from: Organization.
            if (tabParty is Organization)
            {
                tabOrg = tabParty as Organization;
    
                info(strFmt("%1 == tabOrg.NumEmployees",
                    tabOrg.NumEmployees));
                info(strFmt("%1 == tabOrg.RecId",
                    tabOrg.RecId));
            }
    
            // Read from: Nonprofit.
            if (tabParty is Nonprofit)
            {
                tabNonprofit = tabParty as Nonprofit;
    
                info(strFmt("%1 == tabNonprofit.AnnualContribution",
                    tabNonprofit.AnnualContribution));
            }
    
            // Read from: Government.
            if (tabParty is Government)
            {
                tabGovt = tabParty as Government;
    
                info(strFmt("%1 == tabGovt.AgencyDescription",
                    tabGovt.AgencyDescription));
            }
        }
    
    /*** Output to Infolog
    Message_@SYS14327 (07:00:44 pm)
    _ _ _ _ _ _ _ _ _ _ _ _
    
    shout Nonprofit
    Alison_NPF == tabParty.NickName
    50003 == tabParty.InstanceRelationType
    5637144664 == tabParty.RecId
    31 == tabOrg.NumEmployees
    5637144664 == tabOrg.RecId
    111.22 == tabNonprofit.AnnualContribution
    _ _ _ _ _ _ _ _ _ _ _ _
    
    shout Government
    Ben_GOV == tabParty.NickName
    50004 == tabParty.InstanceRelationType
    5637144665 == tabParty.RecId
    42 == tabOrg.NumEmployees
    5637144665 == tabOrg.RecId
    Taxes == tabGovt.AgencyDescription
    _ _ _ _ _ _ _ _ _ _ _ _
    
    shout Organization
    Carl_ORG == tabParty.NickName
    50002 == tabParty.InstanceRelationType
    5637144666 == tabParty.RecId
    53 == tabOrg.NumEmployees
    5637144666 == tabOrg.RecId
    _ _ _ _ _ _ _ _ _ _ _ _
    
    shout Party
    David_PRY == tabParty.NickName
    50001 == tabParty.InstanceRelationType
    5637144667 == tabParty.RecId
    ***/
    }

### ![Gg881064.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg881064.collapse_all(en-us,AX.60).gif")Accessing Method Overrides with a Base Table Variable

The following line of code is in the previous full code example:

tabParty.shoutTableNameToInfolog();

The Party root base class defines this method, and every derived table overrides the method. Each time this line is called, the current record type controls which version of this method is invoked. This means that the tabParty variable is used sometimes to call the method version that is on the Government table.

## AOT Query and the Dynamic Property on the Fields Node

The behavior difference between select \* versus select NickName also applies to queries in the AOT.

The **AOT** \> **Queries** \> MyQuery \> **Data Sources** \> MyDataSource \> **Fields** node has the **Dynamic** property. The **Dynamic** property must be set to **Yes** or **No**.

For the **Dynamic** property, the **Yes** value corresponds to the select \* behavior.

## See also

[Table Inheritance Overview](table-inheritance-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

