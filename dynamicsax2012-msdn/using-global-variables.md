---
title: Using Global Variables
TOCTitle: Using Global Variables
ms:assetid: fae1d483-a47f-4f09-b404-fe388daefbe1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa891830(v=AX.60)
ms:contentKeyID: 35254193
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Using Global Variables [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Global variables are often needed because of flawed implementation designs. However, if used for caching purposes, global variables can provide increases in performance. This topic describes how you can implement a global variable with zero maintenance during an upgrade.

## How to Set the Variable

Get the globalCache variable located on the ClassFactory class:

SysGlobalCache globalCache = ClassFactory.globalCache();

Call the set method:

globalCache.set(str  owner , anytype  key , anytype  value );

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Parameters</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>owner</p></td>
<td><p>A unique name that identifies you as the user. Use classIdGet(this) or classStr(myClass).</p></td>
</tr>
<tr class="even">
<td><p>key</p></td>
<td><p>Identifies your variable. This is useful if you need more than one global variable from the same location.</p></td>
</tr>
<tr class="odd">
<td><p>value</p></td>
<td><p>The actual value of your variable.</p></td>
</tr>
</tbody>
</table>


## Get the Variable

Get the globalCache variable, located on the ClassFactory class:

SysGlobalCache globalCache = ClassFactory.globalCache();

Call the get method:

value = globalCache.get(str  owner , anytype  key , anytype  returnValue  = '');

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Parameters</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>owner</p></td>
<td><p>Must be a unique name that identifies you as the user.</p></td>
</tr>
<tr class="even">
<td><p>key</p></td>
<td><p>Identifies your variable.</p></td>
</tr>
<tr class="odd">
<td><p>returnValue</p></td>
<td><p>The value you want if the global variable has not been set. This is useful for caching purposes. See the following example.</p></td>
</tr>
</tbody>
</table>


## Example

```X++
    void new(Integer _width  = Imagelist::smallIconWidth(),
             Integer _height = Imagelist::smallIconHeight())
    {
        SysGlobalCache globalCache;
        Container      packedData;
        ClassName      className;
        ;
     
        if (this.keepInMemory())
        {
            globalCache = ClassFactory.globalCache();
            className   = classId2Name(ClassIdGet(this));
            packedData  = globalCache.get(className, 0, connull());
            imageList  = globalCache.get(className+classStr(imagelist), 
                                         0, 
                                         null);
        }
        if (!imageList)
        {
            imagelist = new Imagelist(_width,_height);
            this.build();
            if (this.keepInMemory())
            {
                globalCache.set(className, 0, this.pack());
                globalCache.set(className+classStr(imagelist), 
                                0, 
                                imagelist);
            }
        }
        else
        {
            this.unpack(packedData);
        }
    }
```

## Client/Server Considerations

Because of the duality of ClassFactory, global variables can exist either on the client or the server. This could mean less network traffic because it is possible to have the global variable on both sides—set it twice.

To share your global variable across the network and accept the performance penalty of a client/server call, use the infolog variable (Info class) or appl variable (Application class) instead of ClassFactory. They reside on the client and on the server, respectively.

## See also

[Global Class](https://msdn.microsoft.com/en-us/library/gg836018\(v=ax.60\))

[ClassFactory Class](https://msdn.microsoft.com/en-us/library/gg835446\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

