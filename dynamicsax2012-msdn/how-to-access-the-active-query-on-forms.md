---
title: 'How to: Access the Active Query on Forms'
TOCTitle: 'How to: Access the Active Query on Forms'
ms:assetid: 8c001fbe-f430-44be-82e3-29a556986ed7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa659696(v=AX.60)
ms:contentKeyID: 35246370
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Access the Active Query on Forms [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Setting the AutoQuery property on a form data source to Yes causes the system to automatically generate the query that retrieves data to display in the form.

Modify the system-generated query to display a different set of data as the result of user input in the form.

1.  Declare a variable of the type QueryBuildRange.

2.  Initialize the QueryBuildRange variable.

3.  Modify the form data source executeQuery method.

## Declare a Variable of the Type QueryBuildRange

Declare a variable of the type QueryBuildRange in the class declaration method on your form. Following is an example.

```X++
class FormRun extends ObjectRun
    {
        QueryBuildRange   criteriaOpen;
        ...
    }
```

QueryBuildRange is a system class used to specify the search scope of a query.

## Initialize the QueryBuildRange Variable

Initialize the QueryBuildRange variable in the init method on the form data source. To override the init method, right-click the **Methods** node within the data source node, and then click **Override Method** \> **init**.

The initialization must be after the super() call that generates the query. Following is an example.

```X++
void init()
    {
        super();
        criteriaOpen = this.Query().DataSourceNo(1).addRange(
            fieldNum(CustTrans,Open));
        ...
    }
```

Placing the initialization after the super() call in init is equivalent to placing it before the super() call in the run method.

The code sets the criteriaOpen variable to point to the Open field in the CustTrans table.

Following is an explanation of the code:

  - this – a reference to the current form data source.

  - Query() – the member method on the form data source used to retrieve a reference to the form’s query.
    
    An instance of the Query system class is always available on a form data source. The class is automatically instantiated when the form is opened.

  - DataSourceNo(1) – the method on the Query class used to identify the data source that takes an integer as parameter to identify the data source. The first data source is 1.
    
    This call returns a QueryBuildDataSource MorphX object.

  - addRange – the method on the QueryBuildDataSource class used to add a search range to the active criteria. addRange takes a field ID as parameter, and then returns a QueryBuildRange object.

  - fieldNum(CustTrans,Open) – a built-in function that returns the field ID (in this case, the ID of the Open field in the CustTrans table).


> [!NOTE]
> <P>The previously described code pattern enables you to reference the active query to add a range to it. The only values that vary are the parameters to the DataSourceNo method and to the fieldnum function.</P>



## Modify the executeQuery Method

The executeQuery method on the form data source is activated when the form is opened to display data. When overriding the method, you must add your modifications prior to the super() call.

In the following example, the switch statement performs a test on the IncludeAll variable. The QueryBuildRange variable (criteriaOpen) is set to 1 or 0..1, depending on the value of the member variable Value. The query can now be executed.

```X++
void executeQuery()
    {
        switch (IncludeAll.Value())
        {
            case (1) :
                criteriaOpen.Value('1'); 
                break;
            case (0) :
                criteriaOpen.Value('0..1');
                break;
        }
        super();
    }
```

## See also

[How to: Coordinate Two Forms by Overriding an Event Method](how-to-coordinate-two-forms-by-overriding-an-event-method.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

