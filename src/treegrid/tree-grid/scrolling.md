---
title: "Scrolling"
component: "TreeGrid"
description: "Learn how to set width and height for TreeGrid content, display a scrollbar and make the TreeGrid responsive with a parent container."
---

# Scrolling

The scrollbar will be displayed in the treegrid when content exceeds the element [`Width`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~Width.html) or [`Height`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~Height.html). The vertical and horizontal scrollbars will be displayed based on the following criteria:

The vertical scrollbar appears when the total height of rows present in the treegrid exceeds its element height.
The horizontal scrollbar appears when the sum of columns width exceeds the treegrid element width.
The [`Height`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~Height.html) and [`Width`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~Width.html) are used to set the treegrid height and width, respectively.

> The default value for [`Height`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~Height.html) and [`Width`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~Width.html) is **auto**.

## Set width and height

To specify the [`Width`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~Width.html) and [`Height`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~Height.html) of the scroller in the pixel, set the pixel value to a number.

{% aspTab template="tree-grid/scrolling/width-height", sourceFiles="width-height.cs" %}

{% endaspTab %}

## Responsive with parent container

Specify the [`Width`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~Width.html) and [`Height`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~Height.html) as **100%** to make the treegrid element fill its parent container.
Setting the [`Height`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~Height.html) to **100%** requires the treegrid parent element to have explicit height.

{% aspTab template="tree-grid/scrolling/responsive", sourceFiles="responsive.cs" %}

{% endaspTab %}

## Scroll to selected row

You can scroll the treegrid content to the selected row position by using the [`RowSelected`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~RowSelected.html) event.

{% aspTab template="tree-grid/scrolling/selected-row", sourceFiles="selected-row.cs" %}

{% endaspTab %}

## Frozen rows and columns

Frozen rows and columns provides an option to make rows and columns always visible in the top and left side of the treegrid while scrolling.

In this demo, the [`FrozenColumns`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~FrozenColumns.html) is set as **2** and the [`FrozenRows`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~FrozenRows.html)
is set as **3**. Hence, the left two columns and top three rows are frozen.

{% aspTab template="tree-grid/scrolling/frozencolumn", sourceFiles="freezecolumn.cs" %}

{% endaspTab %}

### Freeze particular columns

To freeze particular column in the treegrid, the [`IsFrozen`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGridColumn~IsFrozen.html) property can be used.

In this demo, the columns with field name **TaskName** and **StartDate** is frozen using
the [`IsFrozen`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGridColumn~IsFrozen.html) property.

{% aspTab template="tree-grid/scrolling/isfreezecol", sourceFiles="isfreeze.cs" %}

{% endaspTab %}

### Limitations

The following features are not supported in frozen rows and columns:

* Row Template
* Detail Template
