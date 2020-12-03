---
title: "Editing"
component: "Pivot Table"
description: "Editing allows to perform CRUD operation in the raw items of any cells of the pivot table."
---

# Editing

> This feature is applicable only for relational data source.

Cell edit allows to add, delete, or update the raw items of any value cell from the pivot table. The raw items can be viewed in a data grid inside a new window on double-clicking the appropriate value cell. In the data grid, CRUD operations can be performed by double-clicking the cells or using toolbar options. Once user finishes editing raw items, aggregation will be performed for the updated values in pivot table component immediately. This support can be enabled by setting the [`AllowEditing`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.PivotView.PivotViewCellEditSettings.html#Syncfusion_EJ2_PivotView_PivotViewCellEditSettings_AllowEditing) property in [`PivotViewCellEditSettings`](https://help.syncfusion.com/cr/aspnetmvc-js2/Syncfusion.EJ2.PivotView.PivotViewCellEditSettings.html) class to **true**.

The CRUD operations available in the data grid toolbar and command column are:

| Toolbar Button | Actions |
|----------------|---------|
| Add | Add a new row.|
| Edit | Edit the current row or cell.|
| Delete | Delete the current row.|
| Update | Update the edited row or cell.|
| Cancel | Cancel the edited state. |

The following are the supported edit types in the data grid:

* Normal
* Dialog
* Batch
* Command Columns

## Normal

In normal edit mode, when user starts editing, the state of the currently selected row alone will be completely changed to edit state. User can change the cell values and save it to the data source by clicking "Update" toolbar button. To enable the normal edit, set the [`Mode`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.PivotView.PivotViewCellEditSettings.html#Syncfusion_EJ2_PivotView_PivotViewCellEditSettings_Mode) property in [`PivotViewCellEditSettings`](https://help.syncfusion.com/cr/aspnetmvc-js2/Syncfusion.EJ2.PivotView.PivotViewCellEditSettings.html) class to [**EditMode.Normal**](https://help.syncfusion.com/cr/aspnetmvc-js2/Syncfusion.EJ2.PivotView.EditMode.html).

> The normal edit mode is the default mode of editing..

{% aspTab template="pivot-table/editing/normal", sourceFiles="Normal.cs" %}

{% endaspTab %}

![output](images/edit-normal.png)

## Dialog

In dialog edit mode, when you start editing, the currently selected row data will be shown in a dialog.
You can change the cell values and save it to the data source by clicking **Save**.
To enable the dialog edit, set the [`Mode`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.PivotView.PivotViewCellEditSettings.html#Syncfusion_EJ2_PivotView_PivotViewCellEditSettings_Mode) property in [`PivotViewCellEditSettings`](https://help.syncfusion.com/cr/aspnetmvc-js2/Syncfusion.EJ2.PivotView.PivotViewCellEditSettings.html) class to [**EditMode.Dialog**](https://help.syncfusion.com/cr/aspnetmvc-js2/Syncfusion.EJ2.PivotView.EditMode.html).

{% aspTab template="pivot-table/editing/dialog", sourceFiles="Dialog.cs" %}

{% endaspTab %}

![output](images/edit-dialog.png)

## Batch

In batch edit mode, when you double-click the table cell, the state of target cell is changed to edit state.
You can perform bulk save (added, changed, and deleted data in the single request) to the data source by clicking the toolbar's **Update** button.

To enable the batch edit, set the [`Mode`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.PivotView.PivotViewCellEditSettings.html#Syncfusion_EJ2_PivotView_PivotViewCellEditSettings_Mode) property in [`PivotViewCellEditSettings`](https://help.syncfusion.com/cr/aspnetmvc-js2/Syncfusion.EJ2.PivotView.PivotViewCellEditSettings.html) class to [**EditMode.Batch**](https://help.syncfusion.com/cr/aspnetmvc-js2/Syncfusion.EJ2.PivotView.EditMode.html).

{% aspTab template="pivot-table/editing/batch", sourceFiles="Batch.cs" %}

{% endaspTab %}

![output](images/edit-batch.png)

## Command column

An additional column appended in the grid layout holds the command buttons to perform the CRUD operation.
To enable the command columns, set the [`AllowCommandColumns`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.PivotView.PivotViewCellEditSettings.html#Syncfusion_EJ2_PivotView_PivotViewCellEditSettings_Mode) property in [`PivotViewCellEditSettings`](https://help.syncfusion.com/cr/aspnetmvc-js2/Syncfusion.EJ2.PivotView.PivotViewCellEditSettings.html) class to **true**.

The available built-in command buttons are:

| Command Button | Actions |
|----------------|---------|
| Edit | Edit the current row.|
| Delete | Delete the current row.|
| Save | Update the edited row.|
| Cancel | Cancel the edited state. |

{% aspTab template="pivot-table/editing/cc", sourceFiles="CC.cs" %}

{% endaspTab %}

![output](images/edit-command.png)

## Inline Editing

Allows editing of a value cell directly without the use of an external edit dialog. It is applicable if and only if a single raw data is used for the value of the cell. It is applicable to all editing modes, such as normal, batch, dialog and column commands. It can be enabled by setting the [`allowInlineEditing`](https://help.syncfusion.com/cr/aspnetmvc-js2/Syncfusion.EJ2.PivotView.PivotViewCellEditSettings.html#Syncfusion_EJ2_PivotView_PivotViewCellEditSettings_AllowInlineEditing) property in [`editSettings`](https://help.syncfusion.com/cr/aspnetmvc-js2/Syncfusion.EJ2.PivotView.PivotView.html#Syncfusion_EJ2_PivotView_PivotView_EditSettings) to **true**.

{% aspTab template="pivot-table/editing/Inline-editing", sourceFiles="Inline.cs" %}

{% endaspTab %}

![output](images/inline-editting.png)

## Editing using the pivot chart

Users can also add, delete, or update the underlying raw items of any data point via pivot chart. The raw items will be shown in the data grid in the new window by clicking the appropriate data point. Then you can edit the raw items as mentioned above by any of the edit types (normal, dialog, batch and command column).

{% aspTab template="pivot-table/editing/chart", sourceFiles="Chart.cs" %}

{% endaspTab %}

![output](images/drillthrough-chart-before.png)
<br/>
<br/>
![output](images/editing-dialog.png)

## Events

### EditCompleted

The event [`editCompleted`](https://help.syncfusion.com/cr/aspnetmvc-js2/Syncfusion.EJ2.PivotView.PivotView.html#Syncfusion_EJ2_PivotView_PivotView_EditCompleted) triggers when values cells are edited completely. The event provides edited cell(s) information along with its previous cell value. It also helps to do the CRUD operation by manually updating the database which is connected to the component. It has the following parameters.
* `currentData` - It holds the current raw data of the edited cells.
* `previousData` - It holds the previous raw data of the edited cells.
* `previousPosition` - It holds the index of the raw data whose values are edited.
* `cancel` - It is a boolean property and if it is set as **true**, the editing won’t be reflected in the pivot table.

{% aspTab template="pivot-table/editCompleted-event", sourceFiles="EditCompleted.cs" %}

{% endaspTab %}

### DrillThrough

For more information [`refer`](./drill-through/#drillthrough) here.

### BeginDrillThrough

For more information [`refer`](./drill-through/#begindrillthrough) here.