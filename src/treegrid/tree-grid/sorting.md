---
title: "Sorting"
component: "TreeGrid"
description: "Learn how to sort rows in the TreeGrid control, perform initial sorting, and customize sorting logic."
---

# Sorting

Sorting enables you to sort data in the **Ascending** or **Descending** order.
To sort a column, click the column header.

To sort multiple columns, press and hold the CTRL key and click the column header.  You can clear sorting of any one of the multi-sorted columns by pressing and holding the SHIFT key and clicking the specific column header.

To enable sorting in the TreeGrid, set the [`AllowSorting`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~AllowSorting.html) to true. Sorting options can be configured through the [`SortSettings`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~SortSettings.html).

{% aspTab template="tree-grid/sorting/default-sorting", sourceFiles="defaultSorting.cs" %}

{% endaspTab %}

> TreeGrid columns are sorted in the **Ascending** order. If you click the already sorted column, the sort direction toggles.
> You can apply and clear sorting by invoking [`sortByColumn`](https://ej2.syncfusion.com/documentation/api/treegrid/#sortbycolumn) and [`clearSorting`](https://ej2.syncfusion.com/documentation/api/treegrid/#clearsorting) methods.
> To disable sorting for a particular column, set the [`AllowSorting`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGridColumn~AllowSorting.html) property of [`Column`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGridColumn.html) to **false**.

## Initial sort

To sort at initial rendering, set the **Field** and **Direction** in the [`Columns`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGridSortSettings~Columns.html) property of [`SortSettings`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGridSortSettings.html).

{% aspTab template="tree-grid/sorting/initial-sort", sourceFiles="initialSort.cs" %}

{% endaspTab %}

## Sorting events

During the sort action, the treegrid component triggers two events. The [`ActionBegin`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~ActionBegin.html) event triggers before the sort action starts, and the [`ActionComplete`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~ActionComplete.html) event triggers after the sort action is completed. Using these events you can perform the needed actions.

{% aspTab template="tree-grid/sorting/event-handlers", sourceFiles="eventHandlers.cs" %}

{% endaspTab %}

> The **args.requestType** is the current action name. For example, in sorting the **args.requestType** value is 'sorting'.

<!--  Custom sort comparer

You can customize the default sort action for a column by defining the [`column.sortComparer`](../../api/treegrid/column/#sortcomparer) property. The sort comparer function has the same functionality like [`Array.sort`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort) sort comparer.

In the following example, custom sort comparer function was defined in the `Category` column.

{% tab template="tree-grid/sorting", es5Template="sort-comparer" %}

```typescript
import { TreeGrid, Sort } from '@syncfusion/ej2-treegrid';
import { sortData } from './datasource.ts';

TreeGrid.Inject(Sort);

// The custom function
let sortComparer: (reference: string, comparer:  string) => number = (reference: string,
comparer:  string) => {
    if (reference < comparer) {
        return -1;
    }
    if (reference > comparer) {
        return 1;
    }
    return 0;
};

let treeGridObj: TreeGrid = new TreeGrid({
    dataSource: sortData,
    childMapping: 'subtasks',
    allowSorting: true,
    height: 315,
    treeColumnIndex: 1,
    columns: [
        { field: 'Category', headerText: 'Category', width: 140 },
        { field: 'orderName', headerText: 'Order Name', width: 200 },
        { field: 'orderDate', headerText: 'Order Date', width: 120, textAlign: 'Right', format: 'yMd', type: 'date' },
        { field: 'units', headerText: 'Units', width: 90, textAlign: 'Right' }
    ]
});

treeGridObj.appendTo('#TreeGrid');

```

{% endtab %}

> The sort comparer function will work only for the local data. -->

## Touch interaction

When you tap the treegrid header on touchscreen devices, the selected column header is sorted. A popup ![Multi column sorting](images/sorting.jpg) is displayed for multi-column sorting. To sort multiple columns, tap the popup![Multi sorting](images/msorting.jpg), and then tap the desired treegrid headers.

The following screenshot shows treegrid touch sorting.

<!-- markdownlint-disable MD033 -->
<img src="../images/touch-sorting.jpg" alt="Touch interaction" style="width:320px;height: 620px">
<!-- markdownlint-enable MD033 -->