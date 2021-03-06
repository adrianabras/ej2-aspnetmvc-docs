---
title: "Data Binding"
component: "QueryBuilder"
description: "Learn how to bind local and remote data in the Essential JS 2 QueryBuilder control."
---

# Data binding

The Query Builder uses `DataManager` to bind the data source, which supports both RESTful JSON data services binding and local JavaScript object array binding. The `DataSource` property can be assigned either with the instance of `DataManager` or JavaScript object array collection. It supports two kinds of data binding method.

* Local data
* Remote data

## Local Data

To bind local data to the query builder, you can assign the `DataSource` property with a JavaScript object array. The local data source can also be provided as an instance of the `DataManager`.

{% aspTab template="query-builder/getting-started/demo", sourceFiles="default.cs" %}

{% endaspTab %}

> By default, DataManager uses JsonAdaptor for local data-binding.

## Remote data

To bind remote  data to the query builder, assign service data as an instance of  `DataManager` to the [`dataSource`](https://ej2.syncfusion.com/documentation/api/query-builder/#datasource) property. To interact with remote data source, provide the endpoint `url`.

{% aspTab template="query-builder/data-binding/Remote-data", sourceFiles="remotedata.cs" %}

{% endaspTab %}

> By default, `DataManager` uses `ODataAdaptor` for remote data-binding.

### Binding with OData services

[`OData`](https://www.odata.org/documentation/odata-version-3-0/) is a standardized protocol for creating and consuming data. You can retrieve data from OData service using the DataManager. Refer to the following code example for remote Data binding using OData service.

{% aspTab template="query-builder/data-binding/odata", sourceFiles="odata.cs" %}

{% endaspTab %}

### Binding with ODatav4 services

The ODatav4 is an improved version of OData protocols, and the `DataManager` can also retrieve and consume ODatav4 services. For more details on ODatav4 services, refer to the [`odata documentation`](http://docs.oasis-open.org/odata/odata/v4.0/errata03/os/complete/part1-protocol/odata-v4.0-errata03-os-part1-protocol-complete.html#_Toc453752197). To bind ODatav4 service, use the `ODataV4Adaptor`.

{% aspTab template="query-builder/data-binding/odatav4", sourceFiles="odatav4.cs" %}

{% endaspTab %}

### Web API

You can use `WebApiAdaptor` to bind query builder with Web API created using OData endpoint.

{% aspTab template="query-builder/data-binding/web-api", sourceFiles="webapi.cs" %}

{% endaspTab %}

## Support with Data Manager

You can use the created conditions in DataManager through the `getPredicate` method, which results the filtered records.

{% aspTab template="query-builder/data-binding/data-manager", sourceFiles="default.cs" %}

{% endaspTab %}