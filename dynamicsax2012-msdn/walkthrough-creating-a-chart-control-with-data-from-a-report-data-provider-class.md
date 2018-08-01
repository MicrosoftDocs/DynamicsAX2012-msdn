---
title: 'Walkthrough: Creating a Chart Control with Data from a Report Data Provider Class'
TOCTitle: 'Walkthrough: Creating a Chart Control with Data from a Report Data Provider Class'
ms:assetid: b5964308-df7c-4533-be32-3f8436e5554c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh975425(v=AX.60)
ms:contentKeyID: 46357772
ms.date: 11/07/2012
mtps_version: v=AX.60
f1_keywords:
- Chart Control
- EP Chart Control
- ReportDataProvider
- Report Data Provider
- Enterprise Portal Chart Control
- RDP Data
- Enterprise Portal
- RDP
---

# Walkthrough: Creating a Chart Control with Data from a Report Data Provider Class [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2_

A Chart Control is a User Control option to display chart data in Enterprise Portal. A Chart Control allows many different ways of populating data in a chart. The Visual Studio tools for Microsoft Dynamics AX provided specific support to display data from a Report Data Provider (RDP) class or from an analysis cube. This walkthrough demonstrates how to use the features in Microsoft Dynamics AX to create and deploy a Chart Control for Enterprise Portal that displays data from an RDP class. For information about Chart Controls that display analysis cube data, see [Walkthrough: Creating a Chart Control with Data from an Analysis Services Cube](walkthrough-creating-a-chart-control-with-data-from-an-analysis-services-cube.md). For more information about chart controls that display data from an RDP class, see [How to: Create a Chart with Data from a Report Data Provider Class](how-to-create-a-chart-with-data-from-a-report-data-provider-class.md). For information about how to define RDP classes and data contract classes, see [How to: Use a Report Data Provider Class in a Report](https://msdn.microsoft.com/en-us/library/gg731917\(v=ax.60\)).

The following illustration shows the pie chart that you will create in this walkthrough. Your chart will look different based on your data.

![Pie Chart with Report Data Provider Data for EP](images/Hh975425.RPDPieChart(AX.60).bmp "Pie Chart with Report Data Provider Data for EP")

The walkthrough illustrates the following tasks:

  - Creating an EP Web Application project.

  - Creating a Chart Control.

  - Deploying the Chart Control.

  - Viewing the Chart Control in Enterprise Portal.

## Prerequisites

To complete this walkthrough, you will need:

  - Microsoft Dynamics AX

  - Visual Studio 2010

  - Enterprise Portal with Administrator status. For more information, see [Install Enterprise Portal on a stand-alone server](https://msdn.microsoft.com/en-us/library/gg731916\(v=ax.60\)).

## Creating the EP Web Application Project

Use Visual Studio to create a project for Enterprise Portal.

### To create the EP Web Application project

1.  Start Visual Studio. If User Account Control (UAC) is active, make sure that you start Visual Studio with administrative privileges. To do this, right-click the shortcut for Visual Studio and then click **Run as administrator**.

2.  In the **File** menu, click **New**, and then click **Project**.

3.  In the **New Project** window, select **.NET Framework 3.5** as the framework version to use.
    

    > [!IMPORTANT]
    > <P>For this release of Microsoft Dynamics AX, the EP Web Application project must target the .NET Framework 3.5 to work correctly.</P>



4.  In the **Installed Templates** list, select **Microsoft Dynamics AX**. If you do not see this project template, make sure that you have Visual Studio tools for Microsoft Dynamics AX installed. For more information, see [How to: Set Up Visual Studio for Enterprise Portal Development](how-to-set-up-visual-studio-for-enterprise-portal-development.md).

5.  Choose the EP Web Application template.

6.  Specify a name for the project, and the location of the folder where you want to store the files for the project.

7.  Click **OK** to create the project.

## Creating a Chart Control

Create a Chart Control that displays data from the RDP class. Set the data type of the data source to **ReportDataProvider** and bind the chart to an RDP class, and set the X and Y value members to indicate what fields to display on the chart. Then define the static values of the chart parameters.

### To create a chart control

1.  In Visual Studio, use Solution Explorer to select the project you created.

2.  In the **Project** menu, click **Add New Item**.

3.  In the **Add New Item** window, expand the **Visual C\#** group of installed templates.

4.  Click **Microsoft Dynamics AX**, and then click the **EP Chart Control** template.

5.  For the Chart Control name, type AxRevenue.ascx.
    
    The name entered identifies the chart in SharePoint.

6.  Click **Add**. The new Chart Control is added to the project.

7.  In Solution Explorer, right-click AxRevenue.ascx and then click **View Designer**.

8.  The following components are included in the layout for the revenue chart:
    
      - **AxChartDataSource - AxRevenueDataSource**
    
      - Chart - **AxRevenueChart**
        
        The **DataSourceID** property of the chart has been set to **AxRevenueDataSource**.
    
      - **AxChartBehavior - AxRevenueBehavior**
        
        The **ChartID** property of the chart behavior has been set to **AxRevenueChart**.

9.  Right-click the **AxChartDataSource – AxRevenueDataSource** component in the layout, and then click **Properties**.

10. Set the **DataType** property to **ReportDataProvider**, to indicate that the data is coming from an RDP class.

11. In the **CommandText** property, click the ellipsis button (...). The DataSource picker opens and the **Select a Microsoft Dynamics AX Report Data Provider** tab is displayed.

12. Select the smmSalesRankingDP class.

13. Click **Next**. The **Select Fields** tab displays the fields available to display in the chart.

14. Verify that all of the fields are marked.
    

    > [!NOTE]
    > <P>From the list of field names that you select, you must provide the XValueMember value and YValueMembers value to update the Series property in the next step. In this example, you will display data for the <STRONG>Name</STRONG> field and the <STRONG>Revenue</STRONG> field on the chart.</P>



15. Click **OK**.

16. In the **Design**, right-click the **AxRevenueChart** component in the layout, and then click **Properties**.

17. In the **Series** property, click the ellipsis (…) button to open the **Series Collection Editor**.

18. In the **Series Collection Editor**, set the following properties:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>ChartType</strong></p></td>
    <td><p><strong>Pie</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>XValueMember</strong></p></td>
    <td><p>Name</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>YValueMembers</strong></p></td>
    <td><p>Revenue</p></td>
    </tr>
    </tbody>
    </table>


19. Click **OK** to save the Series value members.

20. In Solution Explorer, right-click the AxRevenue.ascx file and then click **View Markup**. The **ChartType**, **XValueMember**, and **YValueMembers** property values are reflected in the markup.

21. In the \<dynamics:AxChartDataSource\> tag, add the parameters defined in the data contract of the RDP class that you are using to access data for the chart. For this example, you chose the smmSalesRankingDP RDP class. The parameters for the RDP class are defined in the smmSalesRankingContract class. The smmSalesRankingContract class defines two parameters named OutputSorting and OutputQty. The \<dynamics:AxChartDataSource\> tag in your markup should look like the following:
    
        <dynamics:AxChartDataSource ID="AxRevenueDataSource" runat="server" 
        CommandText="SELECT * FROM smmSalesRankingDP.smmSalesRankingTmp" 
        DataType="ReportDataProvider">
            <Parameters>
                <dynamics:ChartParameter Name="OutputSorting" Value="0" />
                <dynamics:ChartParameter Name="OutputQty" Value="5" />
            </Parameters>
        </dynamics:AxChartDataSource>

22. In Solution Explorer, right-click the chart project, and then click Add \[ProjectName\] to AOT.

23. In the **File** menu, click **Save All**.

## Deploying the Chart Control

After you have created and saved the Chart Control, display it in Enterprise Portal to verify its functionality. Use the **Deploy to EP** functionality in the AOT to add the chart to Enterprise Portal. For information about how to display a chart in an existing page, see [How to: Add Web Parts](how-to-add-web-parts.md).

### To deploy the Chart Control

1.  Open the Microsoft Dynamics AX client with administrative privileges. To do this, you must right-click on the icon for Microsoft Dynamics AX and then click **Run as administrator**.

2.  Open the Development Workspace.

3.  Display the AOT.

4.  In the AOT, expand the **Web** \> **Web Content** \> **Managed** node. This node contains all of the User Controls that have been defined for Enterprise Portal.

5.  In the list of managed components, locate the AxRevenue node. This is the managed content node for the Chart Control that you just created.

6.  Right-click the AxRevenue node, and then click **Deploy to EP**.

7.  The **Deploy to EP** dialog box is displayed. Set the **Web module lookup** to Home\\Sales to indicate that the new resources will be used in the Sales site for Enterprise Portal. Click **OK**.

8.  Microsoft Dynamics AX creates a SharePoint page named AxRevenue that is located in the Sales site. This page contains the revenue chart that you created. Microsoft Dynamics AX also creates a web menu item named AxRevenue that points to the new page. Click **Close** to close the **Infolog**.

## Viewing the Chart Control in Enterprise Portal

After you have created the page that contains the Chart Control, view the page in Enterprise Portal.

### To view the Chart Control in Enterprise Portal

1.  Using a web browser, open Enterprise Portal. The typical URL to access Enterprise Portal is:
    
    http://\<server\>/sites/DynamicsAx/
    
    Substitute the name of the server on which Enterprise Portal is installed.

2.  Click **Sales** on the top link bar to display the Sales module site. This is the site that you deployed the new page to.

3.  In the **Site Actions** menu, click **View All Site Content**.

4.  In the **Document Libraries** section, click **Enterprise Portal**. This is the document library that pages for the Sales site are stored in.

5.  Locate the AxRevenue page in the list of pages for the Sales site.

6.  Click the link for the AxRevenue page to display it in Enterprise Portal. After several moments, you should see a page that contains the Chart Control you created, displaying revenue in the current company.

## Next Steps

Recall that a web menu item was created when you deployed the Chart Control. You could add this web menu item to the navigation for Enterprise Portal, and then access the new page through standard Enterprise Portal navigation. See [Page-level Navigation Overview](page-level-navigation-overview.md) or [Walkthrough: Adding a Page to Navigation](walkthrough-adding-a-page-to-navigation.md) for more information about how to add the web menu item to the navigation. Another option is to add the User Control web part to an existing page, such as a Role Center page. For information about how to display a chart in an existing page, see [How to: Add Web Parts](how-to-add-web-parts.md).

## See also

[User Controls Overview](user-controls-overview.md)

[Chart Controls Overview](chart-controls-overview.md)

[Walkthrough: Quickly Creating and Deploying a User Control](walkthrough-quickly-creating-and-deploying-a-user-control.md)

[Walkthrough: Displaying Cube Data in a Report](https://msdn.microsoft.com/en-us/library/dd252605\(v=ax.60\))

