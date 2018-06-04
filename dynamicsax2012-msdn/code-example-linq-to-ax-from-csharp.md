---
title: 'Code Example: LINQ to AX from C#'
TOCTitle: 'Code Example: LINQ to AX from C#'
ms:assetid: 96f6a523-4a11-4c70-b4fa-b9fb6016dff8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ677293(v=AX.60)
ms:contentKeyID: 49384064
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Code Example: LINQ to AX from C\# 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

This topic provides C\# code examples of LINQ to Microsoft Dynamics AX. The following two LINQ formats are shown:

  - LINQ query

  - LINQ extension methods

LINQ stands for Language Integrated Query.


> [!NOTE]
> <P>Support for the LINQ to AX feature started in Microsoft Dynamics AX 2012 R2.</P>



## Prerequisites

To understand this topic, you must first have all the following:

  - Microsoft Dynamics AX 2012 R2 or later.

  - Microsoft Visual Studio 2010 or later.

  - Experience with C\# in Visual Studio.

  - Minor experience with LINQ to SQL (or LINQ to Entities) unrelated to Microsoft Dynamics AX is helpful but not essential.

## Comparison of LINQ to AX versus LINQ to SQL

C\# programmers who know LINQ to SQL already know most of what they need to program with LINQ to AX. Some differences between these two are as follows:

  - LINQ to AX does not support the Skip extension method.

  - LINQ to AX does not support the into keyword.

  - LINQ to AX does not support indexed queries.

  - LINQ to AX does not have the extension methods named InsertOnSubmit and DeleteOnSubmit that LINQ to SQL has.  
    Instead, you use the insert and delete methods that proxies for tables have.

  - LINQ to AX has its own ForUpdate extension method.  
    The C\# example later in this topic demonstrates the use of this method.

### ![JJ677293.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677293.collapse_all(en-us,AX.60).gif")C\# using Statements for LINQ to AX

If your C\# program uses every type of feature in LINQ to AX, your program needs all the following using statements:

``` csharp
//    Microsoft.Dynamics.AX.Framework.Linq.Data.DLL
using Microsoft.Dynamics.AX.Framework.Linq.Data;
using Microsoft.Dynamics.AX.Framework.Linq.Data.AxExpressions;

//    Microsoft.Dynamics.AX.Framework.Linq.Data.Interface.DLL
using Microsoft.Dynamics.AX.Framework.Linq.Data.Common;

//    Microsoft.Dynamics.AX.Framework.Linq.Data.ManagedInteropLayer.DLL
using Microsoft.Dynamics.AX.Framework.Linq.Data.ManagedInteropLayer;

//    Microsoft.Dynamics.AX.Framework.ManagedInterop.DLL
using Microsoft.Dynamics.AX.Framework.ManagedInterop;
```

## Implement the Code Example, Part 1: Dynamics AX

To implement the code example of this topic, you must first prepare your Microsoft Dynamics AX environment. Follow these steps:

1.  Start your Microsoft Dynamics AX client.

2.  Paste the XPO file content into a new file named PrivateProject\_LinkProviderSample.XPO.  
    The XPO file content is available to copy from a section later in this topic.

3.  Import your new XPO file.  
    To import, give focus to the AOT, and then click the menu **Command** \> **Import**.  
    The import action creates the following:
    
      - A private project named LinqProviderSample.
    
      - A table named Person, under **AOT** \> **Data Dictionary** \> **Tables**.
    
      - A table named Loan, under **AOT** \> **Data Dictionary** \> **Tables**.
    
      - An X++ job named LPS1CleanAllTables, under **AOT** \> **Jobs**.
    
      - An X++ job named LPS2PopulatePersonTable, under **AOT** \> **Jobs**.
    
      - An X++ job named LPS3PopulateLoanTable, under **AOT** \> **Jobs**.

4.  Run the jobs that populate the Person and Loan tables, by following these substeps.  
    You can rerun these substeps repeatedly, but it should not be necessary because the C\# code example reverses its changes as it runs:
    
    1.  Run the LPS1CleanAllTables job.
    
    2.  Run the LPS2PopulatePersonTable job.
    
    3.  Run the LPS3PopulateLoanTable job.

## Implement the Code Example, Part 2: Visual Studio

In this section you work with Visual Studio to configure a project that contains the items shown in the following image.

![Visual Studio project items for LINQ to AX](images/JJ677293.LinqProviderSample-VStudio-SolutionItems2(en-us,AX.60).png "Visual Studio project items for LINQ to AX")

To configure your project and to finish implementing the code example, you must complete the following steps:

1.  Start Visual Studio.

2.  Create a new C\# console application project named LinkProviderSample.

3.  For your project, set the target framework to exclude the client profile:  
     **LinkProviderSample** \> **Properties** \> **Application** \> **Target framework** \> **.NET Framework 4**.  
    You do not want **.NET Framework 4 Client Profile**.

4.  Edit the app.config file in your project to ensure it contains the following XML attribute:  
     \<startup useLegacyV2RuntimeActivationPolicy="true"\>

5.  Add references to the assembly DLL files that are circled in the previous project screenshot.  
    You can find these DLL files in a directory path similar to  
     C:\\Program Files (x86)\\Microsoft Dynamics AX\\6.0\\Client\\Bin\\.

6.  In the **Solution Explorer**, right-click the project node, and then click **Add \<yourProjectName\> to AOT**.

7.  Click the menu **View** \> **Application Explorer**.

8.  Create [proxy](proxy-classes-for-net-interop-to-x.md) classes, in C\#, for the Person and Loan tables.  
    To do this, navigate in the **Application Explorer** pane to the **Person** table. Right-click the **Person** table node, and then click **Add to project**. Repeat for the Loan table.

9.  Paste the C\# code into the **Program.cs** in the project.  
    The C\# code is available to copy from a section later in this topic.

10. Build LinkProviderSample.exe executable.

11. Open a console prompt to the directory where LinkProviderSample.exe is stored, and then run the executable.  
    The output is written to the console.

12. Compare the output to the output shown in a later section in this topic.

## XPO File Content for Import, to Copy and Paste

Next are the contents of file PrivateProject\_LinqProviderSample.xpo, which you can import into Microsoft Dynamics AX. During import, the XPO file performs the following actions:

  - Creates a private project to hold the two AOT items is creates next.  
    The project name is **LinqProviderSample**.

  - Creates tables named **Person** and **Loan**.

  - Creates X++ jobs with names that begin **LPS\***. These jobs populate the tables with test data.  
    The job is located under **AOT** \> **Jobs**.

<!-- end list -->

    Exportfile for AOT version 1.0 or later
    Formatversion: 1
    
    ***Element: DBT
    
    ; Microsoft Dynamics AX Table : Loan unloaded
    ; --------------------------------------------------------------------------------
      TABLEVERSION 1
      
      TABLE #Loan
        EnforceFKRelation 1
        PROPERTIES
          Name                #Loan
          CreateRecIdIndex    #Yes
          PrimaryIndex        #SurrogateKey
          ClusterIndex        #SurrogateKey
          Origin              #{1D32A734-6B00-44CB-BF06-3D1CABDA3051}
        ENDPROPERTIES
        
        FIELDS
          FIELD #Amount
            REAL
            PROPERTIES
              Name                #Amount
              Table               #Loan
              Origin              #{6FF54F05-C97B-4CC7-AF48-F7E9BAE3B2D2}
            ENDPROPERTIES
            
          FIELD #PersonID
            INT64
            PROPERTIES
              Name                #PersonID
              Table               #Loan
              Origin              #{5D1404B5-85B7-4578-9B33-EA2BD9B25121}
              ExtendedDataType    #RefRecId
            ENDPROPERTIES
            
        ENDFIELDS
        GROUPS
        ENDGROUPS
        
        INDICES
        ENDINDICES
        FULLTEXTINDICES
        ENDFULLTEXTINDICES
        REFERENCES
          REFERENCE #PersonLoan
            PROPERTIES
              Name                #PersonLoan
              Table               #Person
              UseDefaultRoleNames #Yes
            ENDPROPERTIES
            
            FIELDREFERENCES
              REFERENCETYPE PKFK
              PROPERTIES
                Field               #PersonID
                RelatedField        #RecId
              ENDPROPERTIES
              
            ENDFIELDREFERENCES
          ENDREFERENCE
        ENDREFERENCES
        
        DELETEACTIONS
        ENDDELETEACTIONS
        
        METHODS
        ENDMETHODS
      ENDTABLE
      
    
    ***Element: DBT
    
    ; Microsoft Dynamics AX Table : Person unloaded
    ; --------------------------------------------------------------------------------
      TABLEVERSION 1
      
      TABLE #Person
        EnforceFKRelation 1
        PROPERTIES
          Name                #Person
          CreateRecIdIndex    #Yes
          PrimaryIndex        #SurrogateKey
          ClusterIndex        #SurrogateKey
          Origin              #{687B3FA0-C469-4371-9D74-2A5DE72C9B09}
        ENDPROPERTIES
        
        FIELDS
          FIELD #Age
            INT
            PROPERTIES
              Name                #Age
              Table               #Person
              Origin              #{A6A4BDE1-D506-4EC9-BFEC-3399C3A335FE}
            ENDPROPERTIES
            
          FIELD #FirstName
            STRING
            PROPERTIES
              Name                #FirstName
              Table               #Person
              Origin              #{63A57AAF-11B2-4687-B17D-9D5965F001EB}
              StringSize          #20
            ENDPROPERTIES
            
          FIELD #Income
            REAL
            PROPERTIES
              Name                #Income
              Table               #Person
              Origin              #{ECB0004C-E185-4069-866E-2CD83618528F}
            ENDPROPERTIES
            
          FIELD #LastName
            STRING
            PROPERTIES
              Name                #LastName
              Table               #Person
              Origin              #{938E4C6B-FA83-4355-80E8-801970905E99}
              StringSize          #20
            ENDPROPERTIES
            
        ENDFIELDS
        GROUPS
        ENDGROUPS
        
        INDICES
        ENDINDICES
        FULLTEXTINDICES
        ENDFULLTEXTINDICES
        REFERENCES
        ENDREFERENCES
        
        DELETEACTIONS
        ENDDELETEACTIONS
        
        METHODS
          SOURCE #selectWhereLastNameLike
            #static public Person selectWhereLastNameLike  // X++
            #        (str 20 _sLastNameLike = \"*\")
            #{
            #    Person xrecPerson;
            #    select
            #        forUpdate
            #             Age
            #            ,FirstName
            #            ,Income
            #            ,LastName
            #        from
            #            xrecPerson
            #        where
            #            xrecPerson.LastName like _sLastNameLike
            #    ;
            #    return xrecPerson;
            #}
          ENDSOURCE
        ENDMETHODS
      ENDTABLE
      
    
    ***Element: JOB
    
    ; Microsoft Dynamics AX Job: LPS3PopulateLoanTable unloaded
    ; --------------------------------------------------------------------------------
      JOBVERSION 1
      
      SOURCE #LPS3PopulateLoanTable
        #static void LPS3PopulateLoanTable(Args _args)  // X++
        #{
        #    int i;
        #    Loan lTbl;
        #    void InsertLoan(String30 personLastName, real loanAmount)
        #    {
        #        Person pTbl;
        #        Loan l;
        #        int personID;
        #        select * from pTbl where pTbl.LastName == personLastName;
        #        l.PersonID = pTbl.RecID;
        #        l.Amount = loanAmount;
        #        l.insert();
        #    }
        #    //Make sure there is no data in the table before insert
        #    delete_from lTbl;
        #    //Insert a few loans
        #    InsertLoan('LastName2', 6400);
        #    InsertLoan('LastName2', 5400);
        #    InsertLoan('LastName1', 13450);
        #    InsertLoan('LastName3', 100);
        #    InsertLoan('LastName4', 48000);
        #    InsertLoan('LastName3', 17850);
        #    InsertLoan('LastName5', 32000);
        #    info(\"Loan table is now populated with data.\");
        #}
      ENDSOURCE
      PROPERTIES
        Origin              #{F5FF9BFC-81F9-4425-A52F-4726D1E21FE1}
      ENDPROPERTIES
      
    
    ***Element: JOB
    
    ; Microsoft Dynamics AX Job: LPS2PopulatePersonTable unloaded
    ; --------------------------------------------------------------------------------
      JOBVERSION 1
      
      SOURCE #LPS2PopulatePersonTable
        #static void LPS2PopulatePersonTable(Args _args)  // X++
        #{
        #    int i;
        #    Person pTbl;
        #    void InsertPerson(str fName, str lName, int age, real income)
        #    {
        #        Person p;
        #        p.FirstName = fName;
        #        p.LastName = lName;
        #        p.Age = age;
        #        p.Income = income;
        #        p.insert();
        #    }
        #    //Make sure there is no data in the table before insert
        #    delete_from pTbl;
        #    //Add data
        #    for(i=1;i<7;i++)
        #    {
        #        InsertPerson(
        #            'FirstName' + int2str(i),
        #            'LastName' + int2str(i),
        #            40 + i,
        #            10000 + i*1000
        #        );
        #    }
        #    info(\"Person table is now populated with data.\");
        #}
      ENDSOURCE
      PROPERTIES
        Origin              #{7C24E283-C17F-4C80-99D6-2024E5391383}
      ENDPROPERTIES
      
    
    ***Element: JOB
    
    ; Microsoft Dynamics AX Job: LPS1CleanAllTables unloaded
    ; --------------------------------------------------------------------------------
      JOBVERSION 1
      
      SOURCE #LPS1CleanAllTables
        #static void LPS1CleanAllTables(Args _args)
        #{
        #    Loan lTbl;
        #    Person pTbl;
        #    delete_from lTbl;
        #    delete_from pTbl;
        #    info(\"All data deleted from Person and Loan tables.\");
        #}
      ENDSOURCE
      PROPERTIES
        Origin              #{187ABCA0-09DA-4A15-8C6F-592D7F542FC1}
      ENDPROPERTIES
      
    
    ***Element: PRN
    
    ; Microsoft Dynamics AX Project : LinqProviderSample unloaded
    ; --------------------------------------------------------------------------------
      PROJECTVERSION 2
      
      PROJECT #LinqProviderSample
      PRIVATE
      PROPERTIES
        Name                #LinqProviderSample
        Origin              #{38B9099D-7D23-48E7-8E6E-1FE0E662BFA2}
      ENDPROPERTIES
      
        PROJECTCLASS ProjectNode
        BEGINNODE
          FILETYPE 0
          UTILTYPE 44
          UTILOBJECTID 101592
          NODETYPE 204
          NAME #Loan
        ENDNODE
        BEGINNODE
          FILETYPE 0
          UTILTYPE 44
          UTILOBJECTID 101593
          NODETYPE 204
          NAME #Person
        ENDNODE
        BEGINNODE
          FILETYPE 0
          UTILTYPE 5
          UTILOBJECTID 0
          NODETYPE 215
          NAME #LPS3PopulateLoanTable
        ENDNODE
        BEGINNODE
          FILETYPE 0
          UTILTYPE 5
          UTILOBJECTID 0
          NODETYPE 215
          NAME #LPS2PopulatePersonTable
        ENDNODE
        BEGINNODE
          FILETYPE 0
          UTILTYPE 5
          UTILOBJECTID 0
          NODETYPE 215
          NAME #LPS1CleanAllTables
        ENDNODE
      ENDPROJECT
      
    
    ***Element: END

## Program.cs, to Copy and Paste

Next is the C\# code that contains the LINQ to AX statements.

``` csharp
using       System;  // C#
using       System.Linq;
using U23 = Microsoft.Dynamics.AX.ManagedInterop;
using U22 = Microsoft.Dynamics.AX.Framework.Linq.Data;
using       Microsoft.Dynamics.AX.Framework.Linq.Data; // .ForUpdate() needs this.

namespace LinqProviderSample
{
   class Program  // C#, LINQ to AX.
   {
      static void Main(string[] args)
      {
         // Logon to Dynamics AX.
         U23.Session axSession = new U23.Session();
         axSession.Logon(null, null, null, null);

         // Create a query provider needed by the Linq Provider,
         // and then create a collection of Person using it.
         U22.QueryProvider provider =
            new U22.AXQueryProvider(null);

         // The <Person> type identifies the table to the provider.
         U22.QueryCollection<LinqProviderSample.Person> personCollection =
            new U22.QueryCollection<LinqProviderSample.Person>(provider);
         // Reuse the same QueryProvider instance for the Loan table.
         U22.QueryCollection<LinqProviderSample.Loan> loanCollection =
            new U22.QueryCollection<LinqProviderSample.Loan>(provider);



         Console.WriteLine(Environment.NewLine); //-------------------------
         Console.WriteLine("** Example_1a - LINQ query format - Select all.");
         var allPersons = from pers in personCollection
                      select pers;
         // Current allPersons object inherits IEnumerable<T>.
         foreach (var person in allPersons)
            { Program.WritePerson(person); }
         Console.WriteLine("** Example_1b - Extension methods format - Select all.");
         allPersons = personCollection.Select
                  (pers => pers);
         foreach (var person in allPersons)
            { Program.WritePerson(person); }




         Console.WriteLine(Environment.NewLine); //-------------------------
         Console.WriteLine("** Example_2a - LINQ query format - All persons with age between 30 and 40.");
         var personsAge30_40 = from pers in personCollection
                          where 30 <= pers.Age && pers.Age <= 40
                          select pers;
         foreach (var person in personsAge30_40)
            { Program.WritePerson(person); }
         Console.WriteLine("** Example_2b - Extension methods format - All persons with age between 30 and 40.");
         personsAge30_40 = personCollection.Where
                     (pers => 30 <= pers.Age && pers.Age <= 40);
         foreach (var person in personsAge30_40)
            { Program.WritePerson(person); }




         Console.WriteLine(Environment.NewLine); //-------------------------
         Console.WriteLine("** Example_3a - LINQ query format - Select full name as a list of strings.");
         var nameList = from pers in personCollection
                     select string.Format("{0} {1}", pers.FirstName, pers.LastName);
         foreach (var fullName in nameList)
            { Console.WriteLine(fullName); }
         Console.WriteLine("** Example_3b - Extension methods format - Select full name as a list of strings.");
         nameList = personCollection.Select
                  (pers => string.Format("{0} {1}", pers.FirstName, pers.LastName));
         foreach (var fullName in nameList)
            { Console.WriteLine(fullName); }




         Console.WriteLine(Environment.NewLine); //-------------------------

         Console.WriteLine("** Example_4 - Extension methods format - Average age.");
         var averageAge = personCollection.Average(pers => pers.Age);
         Console.WriteLine(averageAge);

         Console.WriteLine("** Example_5 - Extension methods format - Cost of salaries per month.");
         var costOfSalaries = personCollection.Sum(pers => pers.Income);
         Console.WriteLine(costOfSalaries);

         Console.WriteLine("** Example_6 - Extension methods format - Count of persons with income greater than 11,000.");
         var numOfRecords = personCollection.Where(pers => pers.Income > 13500).Count();
         Console.WriteLine(numOfRecords);




         Console.WriteLine(Environment.NewLine); //-------------------------
         Console.WriteLine("** Example_7 - LINQ query format - Join in a Select.");
         var personWithLargeLoan = from ln in loanCollection
                             // pers.RecId must be on the right side of the 'equals' keyword:
                             join pers in personCollection on ln.PersonID equals pers.RecId
                             where ln.Amount > 20000
                             select new { Name = pers.LastName + " " + pers.FirstName,
                                Amount = ln.Amount }; // Anonymous type.
         foreach (var item in personWithLargeLoan)
         {
            Console.WriteLine("{0} , {1}", item.Name, item.Amount);
         }




         Console.WriteLine(Environment.NewLine); //-------------------------
         Console.WriteLine("** Example_8 - LINQ extension methods format - DynAX .ForUpdate() extension method.");
         Console.WriteLine("Increase income to the first 3 persons by 10001 (update).");
         Console.WriteLine("Before update:");
         allPersons = personCollection
               .OrderBy(pers => pers.Age)
               .ThenByDescending(pers => pers.LastName)
               .Take(3);
         foreach (var person in allPersons)
         {
            Program.WritePerson(person);
         }

         U23.RuntimeContext.Current.TTSBegin();
         var updateAblePersonCollection = personCollection
               .OrderBy(pers => pers.Age)
               .ThenByDescending(pers => pers.LastName)
               .Take(3)
               .ForUpdate();
         foreach (var person in updateAblePersonCollection)
         {
            person.Income = person.Income + 10001;
            person.Update();  // Method on the proxy, not a LINQ method.
         }
         U23.RuntimeContext.Current.TTSCommit();

         Console.WriteLine("After update:");
         allPersons = personCollection
               .OrderBy(pers => pers.Age)
               .ThenByDescending(pers => pers.LastName)
               .Take(3);
         foreach (var person in allPersons)
         {
            Program.WritePerson(person);
         }

         // Restore the data values.
         U23.RuntimeContext.Current.TTSBegin();
         updateAblePersonCollection = personCollection
               .OrderBy(pers => pers.Age)
               .ThenByDescending(pers => pers.LastName)
               .Take(3)
               .ForUpdate();
         foreach (var person in updateAblePersonCollection)
         {
            person.Income = person.Income - 10001;
            person.Update();
         }
         U23.RuntimeContext.Current.TTSCommit();




         Console.WriteLine(Environment.NewLine); //-------------------------
         Console.WriteLine("** Example_9 - Not LINQ specific - Insert, then Delete, a new person by using C# proxy to a DynAX table.");
         Console.WriteLine("Before insert:");
         allPersons = personCollection.Select(pers => pers);
         foreach (var person in allPersons)
         {
            Program.WritePerson(person);
         }

         U23.RuntimeContext.Current.TTSBegin();

         Person newPers = new Person();
         newPers.FirstName = "NewPersonFirstName";
         newPers.LastName = "NewPersonLastName";
         newPers.Age = 50;
         newPers.Income = 56000;
         newPers.Insert(); // Inherited from xRecord or Common of Dynamics AX.

         U23.RuntimeContext.Current.TTSCommit();

         Console.WriteLine("After insert:");
         allPersons = personCollection.Select(p => p);
         foreach (var person in allPersons)
         {
            Program.WritePerson(person);
         }

         // Delete the added person record.
         U23.RuntimeContext.Current.TTSBegin();
         {
            Person persToDelete = new Person();
            persToDelete = Person.selectWhereLastNameLike("NewPerson*");
            while (true)
            {
               if (0 < persToDelete.RecId) persToDelete.Delete();

               if (! persToDelete.Next()) break;
            }
         }
         U23.RuntimeContext.Current.TTSCommit();

         Console.WriteLine("After delete:");
         allPersons = personCollection.Select(pers => pers);
         foreach (var person in allPersons)
         {
            Program.WritePerson(person);
         }


         axSession.Logoff();
      }


      static private void WritePerson(Person pers)
      {
         Console.WriteLine("FirstName: {0}; LastName: {1}; Age: {2}; Income: {3}",
            pers.FirstName, pers.LastName, pers.Age, pers.Income);
      }
   }
}
```

## Output

Next is the output to the console of the LinqProviderSample.exe example C\# program. The program was run in a cmd.exe window.

<pre IsFakePre="true" xmlns="http://www.w3.org/1999/xhtml">&gt;&gt; LinqProviderSample.exe

** Example_1a - LINQ query format - Select all.
FirstName: FirstName1; LastName: LastName1; Age: 41; Income: 11000
FirstName: FirstName2; LastName: LastName2; Age: 42; Income: 12000
FirstName: FirstName3; LastName: LastName3; Age: 43; Income: 13000
FirstName: FirstName4; LastName: LastName4; Age: 44; Income: 14000
FirstName: FirstName5; LastName: LastName5; Age: 45; Income: 15000
FirstName: FirstName6; LastName: LastName6; Age: 46; Income: 16000
** Example_1b - Extension methods format - Select all.
FirstName: FirstName1; LastName: LastName1; Age: 41; Income: 11000
FirstName: FirstName2; LastName: LastName2; Age: 42; Income: 12000
FirstName: FirstName3; LastName: LastName3; Age: 43; Income: 13000
FirstName: FirstName4; LastName: LastName4; Age: 44; Income: 14000
FirstName: FirstName5; LastName: LastName5; Age: 45; Income: 15000
FirstName: FirstName6; LastName: LastName6; Age: 46; Income: 16000


** Example_2a - LINQ query format - All persons with age between 30 and 40.
** Example_2b - Extension methods format - All persons with age between 30 and 40.


** Example_3a - LINQ query format - Select full name as a list of strings.
FirstName1 LastName1
FirstName2 LastName2
FirstName3 LastName3
FirstName4 LastName4
FirstName5 LastName5
FirstName6 LastName6
** Example_3b - Extension methods format - Select full name as a list of strings.
FirstName1 LastName1
FirstName2 LastName2
FirstName3 LastName3
FirstName4 LastName4
FirstName5 LastName5
FirstName6 LastName6


** Example_4 - Extension methods format - Average age.
43.5
** Example_5 - Extension methods format - Cost of salaries per month.
81000
** Example_6 - Extension methods format - Count of persons with income greater than 11,000.
3


** Example_7 - LINQ query format - Join in a Select.
LastName4 FirstName4 , 48000
LastName5 FirstName5 , 32000


** Example_8 - LINQ extension methods format - DynAX .ForUpdate() extension method.
Increase income to the first 3 persons by 10001 (update).
Before update:
FirstName: FirstName1; LastName: LastName1; Age: 41; Income: 11000
FirstName: FirstName2; LastName: LastName2; Age: 42; Income: 12000
FirstName: FirstName3; LastName: LastName3; Age: 43; Income: 13000
After update:
FirstName: FirstName1; LastName: LastName1; Age: 41; Income: 21001
FirstName: FirstName2; LastName: LastName2; Age: 42; Income: 22001
FirstName: FirstName3; LastName: LastName3; Age: 43; Income: 23001


** Example_9 - Not LINQ specific - Insert, then Delete, a new person by using C# proxy to a DynAX table.
Before insert:
FirstName: FirstName1; LastName: LastName1; Age: 41; Income: 11000
FirstName: FirstName2; LastName: LastName2; Age: 42; Income: 12000
FirstName: FirstName3; LastName: LastName3; Age: 43; Income: 13000
FirstName: FirstName4; LastName: LastName4; Age: 44; Income: 14000
FirstName: FirstName5; LastName: LastName5; Age: 45; Income: 15000
FirstName: FirstName6; LastName: LastName6; Age: 46; Income: 16000
After insert:
FirstName: FirstName1; LastName: LastName1; Age: 41; Income: 11000
FirstName: FirstName2; LastName: LastName2; Age: 42; Income: 12000
FirstName: FirstName3; LastName: LastName3; Age: 43; Income: 13000
FirstName: FirstName4; LastName: LastName4; Age: 44; Income: 14000
FirstName: FirstName5; LastName: LastName5; Age: 45; Income: 15000
FirstName: FirstName6; LastName: LastName6; Age: 46; Income: 16000
FirstName: NewPersonFirstName; LastName: NewPersonLastName; Age: 50; Income: 56000
After delete:
FirstName: FirstName1; LastName: LastName1; Age: 41; Income: 11000
FirstName: FirstName2; LastName: LastName2; Age: 42; Income: 12000
FirstName: FirstName3; LastName: LastName3; Age: 43; Income: 13000
FirstName: FirstName4; LastName: LastName4; Age: 44; Income: 14000
FirstName: FirstName5; LastName: LastName5; Age: 45; Income: 15000
FirstName: FirstName6; LastName: LastName6; Age: 46; Income: 16000

&gt;&gt;</pre>


## See also

[Integration with Microsoft Dynamics AX](integration-with-microsoft-dynamics-ax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

