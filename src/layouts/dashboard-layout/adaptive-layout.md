---
title: Responsive Dashboard"
component: "Dashboard Layout"
description: "This section explains about responsiveness and adaptivity of Dashboard Layout component"
---

# Responsive and adaptive layout

The control is provided with built-in responsive support, where panels within the layout get adjusted based on their parent element's dimensions to accommodate any resolution which relieves the burden of building responsive dashboards.

The dashboard layout is designed to automatically adapt with lower resolutions by transforming the entire layout into a stacked one, so that, the panels will be displayed in a vertical column. By default, whenever the screen resolution meets 600px or lower resolutions this layout transformation occurs. This transformation can be modified for any user defined resolution by defining the for the [`mediaQuery`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.Layouts.DashboardLayout~MediaQuery.html) property of the component.

The following sample demonstrates the usage of the [`mediaQuery`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.Layouts.DashboardLayout~MediaQuery.html) property to turn out the layout into a stacked one in user defined resolution. Here, whenever, the window size reaches 700px or lesser, the layout becomes a stacked layout.

{% aspTab template="dashboard-layout/adaptive-layout/", sourceFiles="HomeController.cs" %}

{% endaspTab %}

Output be like the below.

![Responsive and adaptive layout](./images/adaptive_layout.PNG)
