---
title: "Getting Started"
component: "Splitter"
description: "Explains to get started with Splitter control with its key features such as resizable,validation and nested splitter, etc."
---

# Getting Started

 This section briefly explains about how to include a simple Splitter in your ASP.NET MVC application. You can refer [ASP.NET MVC Getting Started documentation](../getting-started) page for introduction part part of the system requirements and configure the common specifications.

> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed,
you also have to include the license key in your projects.
Please refer to this [`link`](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your ASP.NET MVC application to use our controls.

## Adding control to the application

* Now open your view page to render splitter control.

{% aspTab  template="splitter/getting-started/default-splitter", sourceFiles="controller.cs"%}

{% endaspTab %}

Output be like the below.

![splitter](./images/default.png)

## Load content to the pane

You can load the pane contents in either HTML element or string types using [`Content`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Layouts.Splitter.html#Syncfusion_EJ2_Layouts_Splitter_PaneSettings) property.

For detailed information, refer to the `Pane Content` section.

{% aspTab template="splitter/getting-started/load-content", sourceFiles="controller.cs" %}

{% endaspTab %}

Output be like the below.

![Loading content to the panes](./images/content.png)

## Configure pane size

You can specify the size to each pane using [`Size`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Layouts.Splitter.html#Syncfusion_EJ2_Layouts_Splitter_PaneSettings) property. It accepts pane values in percentage and pixel types.

In case of pane size is not declared, panes will equally share the sizes automatically.

  > For Horizontal orientation, panes will share the total width.
  > For Vertical orientation, panes will share the total height.

{% aspTab template="splitter/getting-started/pane-size", sourceFiles="controller.cs" %}

{% endaspTab %}

## Resizable panes

Splitter allows you to change the pane dimensions by resizing the panes. By default, all the panes are resizable. You can disable the resize by using [`Resizable`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Layouts.Splitter.html#Syncfusion_EJ2_Layouts_Splitter_PaneSettings) property in each pane settings.

{% aspTab template="splitter/getting-started/resizable-panes", sourceFiles="controller.cs" %}

{% endaspTab %}

Output be like the below.

![Resizable panes](./images/resizable.png)

## Set minimum and maximum pane sizes

Splitter allows you to set the minimum and maximum sizes for each pane. Resize will happens up to the minimum and maximum values only. It will accepts the size in both percentage and pixel formats.

{% aspTab template="splitter/getting-started/min-max-panesize", sourceFiles="controller.cs" %}

{% endaspTab %}

## Orientation

Splitter supports both `Horizontal` and `Vertical` orientation for the panes. By default, it will be rendered in `Horizontal` orientation. You can change it by using [`Orientation`](https://help.syncfusion.com/cr/aspnetmvc-js2/Syncfusion.EJ2.Layouts.Orientation.html) property.

{% aspTab template="splitter/getting-started/orientation", sourceFiles="controller.cs" %}

{% endaspTab %}

Output be like the below.

![Orientation](./images/orientation.png)

## Nested Splitter

Splitter provides support to render the nested pane to achieve the complex layouts. You can render the nested splitter using the `<div>` element provided for parent splitter.

Also you can render the nested splitter using direct child of the splitter pane. For this, nested splitter should have `100%` width and height to match with the parent pane dimensions.

{% aspTab template="splitter/getting-started/nested-splitter", sourceFiles="controller.cs" %}

{% endaspTab %}

Output be like the below.

![Nested splitter](./images/nested-splitter.png)

## See Also

* [Construct different layouts using Splitter](./different-layouts).