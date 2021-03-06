---
title: "Drop-down list Data binding"
component: "DropDownList"
description: "This section for Syncfusion ASP.NET drop-down list control shows how to bind with local data source and how to fetch data from remote data service."
---

# Data Binding

The DropDownList loads the data either from local data sources or
remote data services using the [dataSource](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.DropDowns.DropDownList~DataSource.html) property. It supports
the data type of `array` or [DataManager](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.DataManager_members.html).

The DropDownList also supports different kinds of data services such as OData, OData V4, and Web API, and data formats such as XML, JSON, and JSONP with the help of [DataManager](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.DataManager_members.html) adaptors.

| Fields | Type | Description |
|------|------|-------------|
| text |  `string` | Specifies the display text of each list item. |
| value |  `number or string` | Specifies the hidden data value mapped to each list item that should contain a unique value. |
| groupBy |  `string` | Specifies the category under which the list item has to be grouped. |
| iconCss |  `string` | Specifies the icon class of each list item. |

> When binding complex data to the DropDownList, fields should be mapped correctly. Otherwise, the selected item remains undefined.

## Binding local data

Local data can be represented in two ways as described below.

### 1. Array of simple data

The DropDownList has support to load array of primitive data such as strings and numbers. Here, both value and text field act the same.

{% aspTab template="dropdownlist/data-binding/arrayofstrings", sourceFiles="arrayofstrings.cs" %}

{% endaspTab %}

### 2. Array of JSON data

The DropDownList can generate its list items through an array of complex data. For this,
the appropriate columns should be mapped to the [fields](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.DropDowns.DropDownList~fields.html) property.

In the following example, `Vegetable` column from complex data have been mapped to the `value` field.

{% aspTab template="dropdownlist/data-binding/arrayofobjects", sourceFiles="arrayofobjects.cs,Vegetables.cs" %}

{% endaspTab %}

### 3. Array of Complex data

The DropDownList can generate its list items through an array of complex data. For this,
the appropriate columns should be mapped to the [fields](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.DropDowns.DropDownList~fields.html) property.

In the following example, `Code.Id` column and `Country.CountrtyId` column from complex data have been mapped to the `value` field and `text` field, respectively.

{% aspTab template="dropdownlist/data-binding/complexdata", sourceFiles="complexdata.cs,Complex.cs" %}

{% endaspTab %}

## Binding remote data

The DropDownList supports retrieval of data from remote data services with the help of [DataManager](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.DataManager_members.html) control. The [`Query`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.DropDowns.DropDownList~Query.html) property is used to fetch
data from the database and bind it to the DropDownList.

The following sample displays the first 6 contacts from **Customers** table of the `Northwind` Data Service.

{% aspTab template="dropdownlist/data-binding/remotedata", sourceFiles="remotedata.cs" %}

{% endaspTab %}

### Bind to URL Adaptor

The DropDownList supports retrieval of data from URL adaptor.

{% aspTab template="dropdownlist/data-binding/urladaptor", sourceFiles="urldata.cs" %}

{% endaspTab %}

### Web API Adaptor

Use the `WebApiAdaptor` to bind DropDownList with Web API created using OData.

{% aspTab template="dropdownlist/data-binding/webapi", sourceFiles="webapi.cs" %}

{% endaspTab %}

### Binding with OData services

`OData` is a standardized protocol for creating and consuming data. You can retrieve data from OData service using the DataManager.

The following example for remote data binding using OData service.

{% aspTab template="dropdownlist/data-binding/odata", sourceFiles="odata.cs" %}

{% endaspTab %}

### Offline mode

To avoid post back for every action, set the DropDownList to load all data on initialization and make the actions process in client-side. To enable this behavior, use the `Offline` property of `DataManager`.

The following example for remote data binding and enabled offline mode.

{% aspTab template="dropdownlist/data-binding/offline", sourceFiles="offline.cs" %}

{% endaspTab %}

## See Also

* [How to load data using template](./templates/#item-template)
* [How to group the data using header](./grouping)
* [How to filter the bound data](./filtering)
* [How to get the count of the data when using remote data](./how-to/remote-data-bind)
* [How to acheive cascading](./how-to/cascading/)
* [How to add item in between the options](./how-to/add-item/)
* [How to remove an item](./how-to/remove-item/)
* [How to preselect the items in dropdownlist](./how-to/multiple-cascading/)