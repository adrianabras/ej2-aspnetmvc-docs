---
title: "Scroll Settings"
component: "Diagram"
description: "Scroll settings allow you to scroll the diagram by using the vertical and horizontal scroll bars"
---

# Scroll Settings

The diagram can be scrolled by using the vertical and horizontal scrollbars. In addition to the scrollbars,mousewheel can be used to scroll the diagram.
Diagram’s [`scrollSettings`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramScrollSettings.html) enable you to read the current scroll status, view port size, current zoom, and zoom factor. It also allows you to scroll the diagram programmatically.

## Get current scroll status

Scroll settings allow you to read the scroll status, [`viewPortWidth`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramScrollSettings.html#Syncfusion_EJ2_Diagrams_DiagramScrollSettings_ViewPortWidth), [`viewPortHeight`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramScrollSettings.html#Syncfusion_EJ2_Diagrams_DiagramScrollSettings_ViewPortHeight), and [`currentZoom`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramScrollSettings.html#Syncfusion_EJ2_Diagrams_DiagramScrollSettings_CurrentZoom) with a set of properties. To explore those properties, see [`Scroll Settings`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramScrollSettings.html).

## Define scroll status

Diagram allows you to pan the diagram before loading, so that any desired region of a large diagram is made to view. You can programmatically pan the diagram with the [`horizontalOffset`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramScrollSettings.html#Syncfusion_EJ2_Diagrams_DiagramScrollSettings_HorizontalOffset) and [`verticalOffset`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramScrollSettings.html#Syncfusion_EJ2_Diagrams_DiagramScrollSettings_VerticalOffset) properties of scroll settings. The following code illustrates how to set pan the diagram programmatically.

In the following example, the vertical scroll bar is scrolled down by 50px and horizontal scroll bar is scrolled to right by 100px.

{% aspTab template="diagram/pagesettings/status", sourceFiles="status.cs" %}

{% endaspTab %}

## Update scroll status

You can programmatically change the scroll offsets at runtime by using the client-side method update. The following code illustrates how to change the scroll offsets and zoom factor at runtime.

{% aspTab template="diagram/pagesettings/update", sourceFiles="update.cs" %}

{% endaspTab %}

```javascript
var diagram = document.getElementById("container").ej2_instances[0];
//Updates scroll settings
diagram.scrollSettings.horizontalOffset=200;
diagram.scrollSettings.verticalOffset=30
diagram.dataBind();

```

## AutoScroll

Autoscroll feature automatically scrolls the diagram, whenever the node or connector is moved beyond the boundary of the diagram. So that, it is always visible during dragging, resizing, and multiple selection operations. Autoscroll is automatically triggered when any one of the following is done towards the edges of the diagram.

* Node dragging, resizing
* Connection editing
* Rubber band selection
* Label dragging

The diagram client-side event [`ScrollChange`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.Diagram.html#Syncfusion_EJ2_Diagrams_Diagram_ScrollChange) gets triggered when the autoscroll (scrollbars) is changed and you can do your own customization in this event.

The autoscroll behavior in your diagram can be enabled/disabled by using the [`canAutoScroll`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramScrollSettings.html#Syncfusion_EJ2_Diagrams_DiagramScrollSettings_CanAutoScroll) property of the diagram.

## Autoscroll border

The autoscroll border is used to specify the maximum distance between the object and diagram edge to trigger autoscroll. The default value is set as 15 for all sides (left, right, top, and bottom) and it can be changed by using the [`autoScrollBorder`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramScrollSettings.html#Syncfusion_EJ2_Diagrams_DiagramScrollSettings_AutoScrollBorder) property of page settings. The following code example illustrates how to set autoscroll border.

{% aspTab template="diagram/pagesettings/auto", sourceFiles="auto.cs" %}

{% endaspTab %}

## Scroll limit

The scroll limit allows you to define the scrollable region of the diagram. It includes the following options:

* Allows to scroll in all directions without any restriction.
* Allows to scroll within the diagram content.
* Allows to scroll within the specified scrollable area.
* The [`scrollLimit`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramScrollSettings.html#Syncfusion_EJ2_Diagrams_DiagramScrollSettings_ScrollLimit) property of scroll settings helps to limit the scrolling.

The scrollSettings [`scrollableArea`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramScrollSettings.html#Syncfusion_EJ2_Diagrams_DiagramScrollSettings_ScrollableArea) allow to extend the scrollable region that is based on the scroll limit.
The following code example illustrates how to specify the scroll limit.

{% aspTab template="diagram/pagesettings/default", sourceFiles="default.cs" %}

{% endaspTab %}

## Scroll padding

The scroll padding allows you to extend the scrollable region that is based on the scroll limit.

The following code example illustrates how to set scroll padding to diagram region.

{% aspTab template="diagram/pagesettings/default", sourceFiles="default.cs" %}

{% endaspTab %}

## Scrollable Area

Scrolling beyond any particular rectangular area can be restricted by using the [`scrollableArea`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramScrollSettings.html#Syncfusion_EJ2_Diagrams_DiagramScrollSettings_ScrollableArea) property of scroll settings. To restrict scrolling beyond any custom region, set the [`scrollLimit`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramScrollSettings.html#Syncfusion_EJ2_Diagrams_DiagramScrollSettings_ScrollLimit) as “limited”. The following code example illustrates how to customize scrollable area.

{% aspTab template="diagram/pagesettings/area", sourceFiles="area.cs" %}

{% endaspTab %}

## UpdateViewport

The [`updateViewPort`](../api/diagram) method is used to update the diagram page and view size at runtime.