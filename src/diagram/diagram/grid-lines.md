---
title: "Gridlines"
component: "Diagram"
description: "Diagram gridlines are the lines that are draw behind the nodes and connectors."
---

# Gridlines

Gridlines are the pattern of lines drawn behind the diagram elements. It provides a visual guidance while dragging or arranging the objects on the diagram surface.

The model’s [`snapSettings`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramSnapSettings.html) property is used to customize the gridlines and control the snapping behavior in the diagram.

## Customize the gridlines visibility

The [`snapSettings.snapConstraints`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.SnapConstraints.html) enables you to show/hide the gridlines. The following code example illustrates how to show or hide gridlines.

If you need to enable snapping, then inject snapping module into the diagram.

{% aspTab template="diagram/gridlines/snap", sourceFiles="snap.cs" %}

{% endaspTab %}

To show only horizontal/vertical gridlines or to hide gridlines, refer to [`Constraints`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.SnapConstraints.html).

## Appearance

The appearance of the gridlines can be customized by using a set of predefined properties.

* The [`horizontalGridLines`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramSnapSettings.html#Syncfusion_EJ2_Diagrams_DiagramSnapSettings_HorizontalGridlines) and the [`verticalGridLines`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramSnapSettings.html#Syncfusion_EJ2_Diagrams_DiagramSnapSettings_VerticalGridlines) properties allow to customize the appearance of the horizontal and vertical gridlines respectively.

* The horizontal gridlines [`lineColor`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramGridlines.html#Syncfusion_EJ2_Diagrams_DiagramGridlines_LineColor) and [`lineDashArray`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramGridlines.html#Syncfusion_EJ2_Diagrams_DiagramGridlines_LineDashArray) properties are used to customizes the line color and line style of the horizontal gridlines.

* The vertical gridlines [`lineColor`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramGridlines.html#Syncfusion_EJ2_Diagrams_DiagramGridlines_LineColor) and [`lineDashArray`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramGridlines.html#Syncfusion_EJ2_Diagrams_DiagramGridlines_LineDashArray) properties are used to customizes the line color and line style of the vertical gridlines.

The following code example illustrates how to customize the appearance of gridlines.

{% aspTab template="diagram/gridlines/appear", sourceFiles="appear.cs" %}

{% endaspTab %}

## Line intervals

Thickness and the space between gridlines can be customized by using horizontal gridlines’s [`linesInterval`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramGridlines.html#Syncfusion_EJ2_Diagrams_DiagramGridlines_LineIntervals) and vertical gridlines’s [`linesInterval`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramGridlines.html#Syncfusion_EJ2_Diagrams_DiagramGridlines_LineIntervals) properties. In the lines interval collections, values at the odd places are referred as the thickness of lines and values at the even places are referred as the space between gridlines.

The following code example illustrates how to customize the thickness of lines and the line intervals.

{% aspTab template="diagram/gridlines/intervals", sourceFiles="intervals.cs" %}

{% endaspTab %}

## Snapping

## Snap to lines

This feature allows the diagram objects to snap to the nearest intersection of gridlines while being dragged or resized. This feature enables easier alignment during layout or design.

Snapping to gridlines can be enabled/disabled with the [`snapSettings.snapConstraints`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.SnapConstraints.html). The following code example illustrates how to enable/disable the snapping to gridlines.

{% aspTab template="diagram/gridlines/lines", sourceFiles="lines.cs" %}

{% endaspTab %}

## Customization of snap intervals

By default, the objects are snapped towards the nearest gridline. The gridline or position towards where the diagram object snaps can be customized with the horizontal gridlines’s [`snapInterval`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramGridlines.html#Syncfusion_EJ2_Diagrams_DiagramGridlines_SnapIntervals) and the vertical gridlines’s [`snapInterval`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramGridlines.html#Syncfusion_EJ2_Diagrams_DiagramGridlines_SnapIntervals) properties.

{% aspTab template="diagram/gridlines/snapIntervals", sourceFiles="snapIntervals.cs" %}

{% endaspTab %}

## Snap to objects

The snap to object provides visual cues to assist with aligning and spacing diagram elements. A node can be snapped with its neighboring objects based on certain alignments. Such alignments are visually represented as smart guides.

The [`snapObjectDistance`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramSnapSettings.html#Syncfusion_EJ2_Diagrams_DiagramSnapSettings_SnapObjectDistance) property allows you to define minimum distance between the selected object and the nearest object.

The [`snapAngle`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.DiagramSnapSettings.html#Syncfusion_EJ2_Diagrams_DiagramSnapSettings_SnapAngle) property allows you to define the snap angle by which the object needs to be rotated.

The [`snapConstraints`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Diagrams.SnapConstraints.html) property allows you to enable or disable the certain features of the snapping, refer to `snapConstraints`.

{% aspTab template="diagram/gridlines/objects", sourceFiles="objects.cs" %}

{% endaspTab %}
