---
title: 'How to: Connect to an External Database from X++ Code'
TOCTitle: 'How to: Connect to an External Database from X++ Code'
ms:assetid: d6421989-9a3e-44a4-9070-dd0b884cb7b7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Ee677510(v=AX.60)
ms:contentKeyID: 35252035
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Connect to an External Database from X++ Code 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to connect directly to an external database from Microsoft Dynamics AX X++ code. This is achieved by using the Open Database Connection (ODBC) protocol through the OdbcConnection class. This is useful when an external system that is implemented without Microsoft Dynamics AX has important information stored in its database.

Before you can use ODBC, you must create a Data Source Name (DSN) in the Windows operating system. A DSN acts as a thin client to the database and includes all the authentication information such as username and password.


> [!WARNING]
> <P>If you use ODBC to directly access data that is stored in an installation of Microsoft Dynamics AX, you must ensure that your code contains the proper restrictions to partition and company. For more information, see <A href="how-to-include-a-filter-for-partition-in-direct-transact-sql.md">How to: Include a Filter for Partition in Direct Transact-SQL</A>.</P>



## Create a DSN

To create a Data Source Name (DSN) go to **Administrative Tools** \> **Data Sources (ODBC)**.

Create the DSN on the tier where the X++ code will call the DSN from. This will be either on the client computer or on the Application Object Server (AOS) computer.


> [!NOTE]
> <P>Ongoing maintenance is simpler if the DSN is created on the AOS tier.</P>



## X++ Code Example with ODBC

The following X++ code example uses ODBC to connect to an external database. The code example assumes that you have already created the DSN in Windows.

    // X++, Main method in a class.
    static public void Main(Args _args)
    {
        LoginProperty loginProperty;
        OdbcConnection odbcConnection;
        Statement statement;
        ResultSet resultSet;
        str sql, criteria;
        SqlStatementExecutePermission perm;
        ;
    
        // Set the information on the ODBC.
        loginProperty = new LoginProperty();
        loginProperty.setDSN("dsnName");
        loginProperty.setDatabase("databaseName");
    
        //Create a connection to external database.
        odbcConnection = new OdbcConnection(loginProperty);
    
        if (odbcConnection)
        {
            sql = "SELECT * FROM MYTABLE WHERE FIELD = "
                + criteria
                + " ORDER BY FIELD1, FIELD2 ASC ;";
    
            //Assert permission for executing the sql string.
            perm = new SqlStatementExecutePermission(sql);
            perm.assert();
    
            //Prepare the sql statement.
            statement = odbcConnection.createStatement();
            resultSet = statement.executeQuery(sql);
    
            //Cause the sql statement to run,
            //then loop through each row in the result.
            while (resultSet.next())
            {
                //It is not possible to get field 3 and then 1.
                //Always get fields in numerical order, such as 1 then 2 the 3 etc.
                print resultSet.getString(1);
                print resultSet.getString(3);
            }
    
            //Close the connection.
            resultSet.close();
            statement.close();
        }
        else
        {
            error("Failed to log on to the database through ODBC.");
        }
    }

### ![Ee677510.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Ee677510.collapse_all(en-us,AX.60).gif")32 Bit and 64 Bit Windows Operating System

The preceding code example can run on either the client tier or the server tier. The following table shows how the operating system architecture affects the choice of tier.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p> </p></td>
<td><p><strong>32 bit Windows</strong></p></td>
<td><p><strong>64 bit Windows</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Client tier (MorphX)</strong></p></td>
<td><p>Runnable.</p></td>
<td><p>Not runnable.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Server tier (AOS)</strong></p></td>
<td><p>Runnable.</p></td>
<td><p>Runnable.</p>
<p>Consider adding the server keyword to the declaration of the Main method.</p></td>
</tr>
</tbody>
</table>


## See also

[Queries in the AOT for Data Access](queries-in-the-aot-for-data-access.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

