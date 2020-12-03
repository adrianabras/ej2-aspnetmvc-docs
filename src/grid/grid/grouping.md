---
title: "Grouping"
component: "Grid"
description: "Learn how to group rows, apply initial groups, customize caption templates, and group by format in the Essential JS 2 DataGrid control."
---

# Grouping

The Grid has options to group records by dragging and dropping the column header to the group drop area. When grouping is applied, grid records are organized into a hierarchical structure to facilitate easier expansion and collapse of records.

To enable grouping in the grid, set the [`AllowGrouping`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.Grid.html#Syncfusion_EJ2_Grids_Grid_AllowGrouping) as true. Grouping options can be configured through the [`GroupSettings`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridGroupSettings.html).

{% aspTab template="grid/grouping/group", sourceFiles="group.cs" %}

{% endaspTab %}

> You can group and ungroup columns by using the [`groupColumn`](https://ej2.syncfusion.com/documentation/api/grid/#groupcolumn) and
[`ungroupColumn`](https://ej2.syncfusion.com/documentation/api/grid/#ungroupcolumn) methods.
> To disable grouping for a particular column, set
[`AllowGrouping`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridColumn.html#Syncfusion_EJ2_Grids_GridColumn_AllowGrouping) property of [`Column`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridColumn.html) to false.

## Initial group

To apply group at initial rendering, set the column field name in the [`Columns`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridGroupSettings.html#Syncfusion_EJ2_Grids_GridGroupSettings_Columns) property of [`GroupSettings`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridGroupSettings.html).

{% aspTab template="grid/grouping/initial-group", sourceFiles="initial-group.cs" %}

{% endaspTab %}

## Caption template

You can customize the group caption by using the [`CaptionTemplate`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridGroupSettings.html#Syncfusion_EJ2_Grids_GridGroupSettings_CaptionTemplate) property of [`GroupSettings`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridGroupSettings.html).

{% aspTab template="grid/grouping/caption-temp", sourceFiles="caption-temp.cs" %}

{% endaspTab %}

## Hide drop area

To avoid ungrouping or further grouping of a column after initial column
grouping, define the [`ShowDropArea`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridGroupSettings.html#Syncfusion_EJ2_Grids_GridGroupSettings_ShowDropArea) of [`GroupSettings`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridGroupSettings.html) as false.

{% aspTab template="grid/grouping/hide-drop-area", sourceFiles="hide-drop-area.cs" %}

{% endaspTab %}

## Group with paging

On grouping columns with paging feature, the aggregated information and total items are displayed based on the current page. The grid does not consider aggregated information and total items from other pages. To get additional details (aggregated information and total items) from other pages, set the [`DisablePageWiseAggregates`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridGroupSettings.html#Syncfusion_EJ2_Grids_GridGroupSettings_DisablePageWiseAggregates) of [`GroupSettings`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridGroupSettings.html) to false.

> If remote data is bound to grid dataSource, two requests will be sent when performing grouping action; one for getting the grouped data and another for getting aggregate details and total items count.

## Group by format

By default, a column will be grouped by the data or value present for the particular row. To group the numeric
or datetime column based on the mentioned format, you have to enable the
[`EnableGroupByFormat`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridColumn.html#Syncfusion_EJ2_Grids_GridColumn_EnableGroupByFormat) property of the corresponding
grid columns.

{% aspTab template="grid/grouping/group-format", sourceFiles="group-format.cs" %}

{% endaspTab %}

## Grouping events

During the group action, the grid component triggers two events. The [`ActionBegin`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.Grid.html#Syncfusion_EJ2_Grids_Grid_ActionBegin) event
triggers before the group action starts and the [`ActionComplete`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.Grid.html#Syncfusion_EJ2_Grids_Grid_ActionComplete) event triggers after the group action is completed. Using these events you can perform any action.

{% aspTab template="grid/grouping/grouping-events", sourceFiles="grouping-events.cs" %}

{% endaspTab %}

> The **args.requestType** is based on the current action name. For example, when grouping, the **args.requestType** value will be grouping.

## Collapse by external button

You can collapse the selected group from an external button by invoking the expandCollapseRows method.

{% aspTab template="grid/grouping/collapse", sourceFiles="collapse.cs" %}

{% endaspTab %}

## Reordering on Grouped Columns

Grid provides an option to interchange the position of the Grouped Columns by dragging and dropping the grouped headercells in the droparea. So, any new column entering into the droparea can also be dropped in any position.

To enable this feature, you have to set the [`allowReordering`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridGroupSettings.html) of **GroupSettings** property as **true**.

{% aspTab template="grid/grouping/reordering", sourceFiles="GroupOrdering.cs" %}

{% endaspTab %}

## Lazy Load Grouping

The lazy load grouping allows you to load grouped records to the Grid through the on-demand concept. So, you can use this feature to load a huge amount of grouped data to the Grid without any performance degradation.

When you enable this feature, the Grid will render only the initial level caption rows in the collapsed state at grouping. The child rows of each caption will be fetched from the server and render in the Grid when you expand the caption row. The fetching child records count will be implicitly determined by the content area occupying rows count. So, if the child records exceed the count, then the Grid will request the server again to fetch the next block of child records on scrolling.

The caption row expand/collapse state will be persisted on paging and Grid pages count will be determined based on the caption rows count instead of the child rows.

To enable this feature, you have to set the [`groupSettings.enableLazyLoading`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridGroupSettings.html#Syncfusion_EJ2_Grids_GridGroupSettings_EnableLazyLoading) property as **true**.

{% aspTab template="grid/grouping/lazy-load-grouping", sourceFiles="lazy-load.cs" %}

{% endaspTab %}

### Handling the lazy load grouping at server-side

You can use the `UrlAdaptor` of `DataManager` when binding the remote data. Along with the default server request, this feature will additionally send the below details to handle the lazy load grouping. In the server end, these details are bound with the `IsLazyLoad` and `OnDemandGroupInfo` parameters in the `DataManagerRequest` model. Please refer to the below table and screenshots.

Property Name |Description
-----|-----
`isLazyLoad` |To differentiate the default grouping and lazy load grouping
`onDemandGroupInfo` |Have the details of expanded caption row grouping `level`, `skip`, `take` and `filter` query of the child records

![IsLazyLoad](images/islazyload.jpg)

![OnDemandGroupInfo](images/groupinfo.jpg)

The following code example describes the lazy load grouping handled at the server-side with other the grid actions.

```typescript
public IActionResult UrlDatasource([FromBody] DataManagerRequest dm)
{
    IEnumerable groupedData = null;
    IEnumerable<Customers> DataSource = customers;
    DataOperations operation = new DataOperations();

    if (dm.Search != null && dm.Search.Count > 0)
    {
        DataSource = operation.PerformSearching(DataSource, dm.Search);  //Search
    }
    if (dm.Sorted != null && dm.Sorted.Count > 0) //Sorting
    {
        DataSource = operation.PerformSorting(DataSource, dm.Sorted);
    }
    if (dm.Where != null && dm.Where.Count > 0) //Filtering
    {
        DataSource = operation.PerformFiltering(DataSource, dm.Where, dm.Where[0].Operator);
    }
    int count = DataSource.Cast<Customers>().Count();
    if (dm.IsLazyLoad == false && dm.Skip != 0)
    {
        DataSource = operation.PerformSkip(DataSource, dm.Skip); // Paging
    }
    if (dm.IsLazyLoad == false && dm.Take != 0)
    {
        DataSource = operation.PerformTake(DataSource, dm.Take);
    }
    if (dm.IsLazyLoad)
    {
        groupedData = operation.PerformGrouping<Customers>(DataSource, dm); // Lazy load grouping
        if (dm.OnDemandGroupInfo != null && dm.Group.Count() == dm.OnDemandGroupInfo.Level)
        {
            count = groupedData.Cast<Customers>().Count();
        }
        else
        {
            count = groupedData.Cast<Group>().Count();
        }
        groupedData = operation.PerformSkip(groupedData, dm.OnDemandGroupInfo == null ? dm.Skip : dm.OnDemandGroupInfo.Skip);
        groupedData = operation.PerformTake(groupedData, dm.OnDemandGroupInfo == null ? dm.Take : dm.OnDemandGroupInfo.Take);
    }
return dm.RequiresCounts ? Json(new { result = groupedData == null ? DataSource : groupedData, count = count }) : Json(DataSource);
}

```

### Limitations for Lazy load grouping

* Due to the element height limitation in browsers, the maximum number of records loaded by the grid is limited due to the browser capability.
* DataManager's `UrlAdaptor` and `JsonAdaptor` only have the built-in lazy load grouping support.
* Lazy load grouping is not compatible with virtualization, infinite scroll and batch editing, row template etc.
* Programmatic selection is not supported.

## See Also

* [Exporting grouped records](./excel-exporting#Exporting-grouped-records)