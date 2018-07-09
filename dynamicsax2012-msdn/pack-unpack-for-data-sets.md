---
title: Pack/Unpack for Data Sets
TOCTitle: Pack/Unpack for Data Sets
ms:assetid: 521609db-9a30-4a15-9f97-e65bbd7ddabe
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh812493(v=AX.60)
ms:contentKeyID: 44090279
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Pack/Unpack for Data Sets 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The pack/unpack pattern is used throughout Microsoft Dynamics AX. Data sets are one of the areas where this pattern is used. Data sets often have X++ code that defines variables and methods that are used by the data set. These X++ methods can be called from the code you write for User Controls in Enterprise Portal. However, the values of the variables for the data set do not survive the postbacks that occur in Enterprise Portal. By implementing the pack/unpack pattern, the variables for the data set can be preserved when a postback occurs.

## Implementing Pack/Unpack for a Data Set

To implement the pack/unpack design pattern for a data set, you must add code to several areas of the data set.

### Class declaration

In the classDeclaration for the data set, you do the following:

1.  Define the variables the data set uses.  

2.  Add a \#DEFINE macro that indicates the version of the variables that are stored by the pack method.  

3.  Complete the code with a \#LOCALMACRO macro that indicates what variable values are stored by the pack method. If there are multiple variables in the macro, separate their names with commas.

In the following example, two int variables are defined for the data set. Notice that both variables are included in the definition of the CurrentList macro.

```X++
    public class DataSetRun extends ObjectRun
    {
        int sampleValue1;
        int sampleValue2;
    
        #DEFINE.CurrentVersion(1)
    
        #LOCALMACRO.CurrentList
            sampleValue1, sampleValue2
        ENDMACRO
    }
```

### Pack method

Override the pack method for the data set and supply the following code:

```X++
    public container pack()
    {
       return [#CurrentVersion, #CurrentList];
    }
```

### Unpack method

Override the unpack method for the data set and supply the following code:

```X++
    public boolean unpack(container _packed)
    {
        Version version = RunBase::getVersion(_packed);
    
        switch(version)
        {
            case #CurrentVersion:
                [version, #CurrentList] = _packed;
                break;
    
            default:
                return false;
        }
    
        return true;
    }
```

## Getter and Setter Methods to Access Data Set Variables

The code for a User Control often must access the member variables of a data set. To support that access, you can add a getter and a setter method to the data set for each member variable.

The following code example adds a getter and a setter method for the data set to get and set the sampleValue1 variable that was defined in the previous example.

```X++
    public int GetSampleValue1()
    {
        return sampleValue1;
    }
    
    public void SetSampleValue1(int _value)
    {
        sampleValue1 = _value;
    }
```

For more information about data set methods, see [How to: Add Methods to Data Sets](how-to-add-methods-to-data-sets.md). Because the pack/unpack design pattern is implemented for the data set, the values of the two variables are maintained through the postbacks that occur in Enterprise Portal.

## See also

[How to: Use a Macro Value](how-to-use-a-macro-value.md)

[How to: Use the \#localmacro and \#globalmacro Directives](how-to-use-the-sharplocalmacro-and-sharpglobalmacro-directives.md)

[Pack-Unpack Design Pattern](pack-unpack-design-pattern.md)

[Data Access Overview](data-access-overview.md)

