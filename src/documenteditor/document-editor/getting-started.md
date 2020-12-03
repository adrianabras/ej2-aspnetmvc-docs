---
title: "Getting Started"
component: "DocumentEditor"
description: "Learn how to get started using ASP.NET MVC document editor component through simple steps."
---

# Getting Started with ASP.NET MVC

> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your ASP.NET MVC application to use our components.

## Prerequisites

To get start with ASP.NET MVC application, need to ensure the following software to be installed on the machine.

1. .Net Framework 4.5 and above.
2. ASP.NET MVC 4 or ASP.NET MVC 5
3. Visual Studio

## Preparing ASP.NET MVC application

The following steps to create ASP.NET MVC Application.

**Step 1:** Create ASP.NET MVC Application with default template project in Visual Studio.

![Default Template](./images/default-template.png)

**Step 2:** Once your project created. We need to add Syncfusion EJ2 package into your application by using `NuGet Package Manager`.

Open the `NuGet` package manager.

![Solution Explorer](./images/solution-explorer-mvc.png)

Install the [Syncfusion.EJ2.MVC4](https://www.nuget.org/packages/Syncfusion.EJ2.MVC4/) package to the application.

![Nuget Demo](./images/aspnetmvc-nuget-package.png)

After installation complete, this will be included in the project. You can refer it from the Project Assembly Reference.

> The [Syncfusion.EJ2.MVC4](https://www.nuget.org/packages/Syncfusion.EJ2.MVC4/) NuGet package has dependencies, [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/) for JSON serialization and [Syncfusion.Licensing](https://www.nuget.org/packages/Syncfusion.Licensing/) for validating [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key#aspnet-mvc).

**Step 3:** Add `Syncfusion.EJ2` namespace reference in `Web.config`

```cs
<namespaces>
    <add namespace="Syncfusion.EJ2"/>
</namespaces>

```

```cs
<system.web>
    <compilation>
      <assemblies>
        <add assembly="Syncfusion.EJ2, Culture=neutral"/>
      </assemblies>
    </compilation>
  </system.web>
```

**Step 4:** Add client side resource through [`CDN`](http://ej2.syncfusion.com/15.4.23/documentation/base/deployment.html?lang=typescript#cdn) or local [`package`](https://www.npmjs.com/package/@syncfusion/ej2) in the layout page `_Layout.cshtml`.

```html
<head>
    ....
    ....

    <!-- Syncfusion Essential JS 2 Styles -->
    <link rel="stylesheet" href="https://cdn.syncfusion.com/ej2/material.css" />

    <!-- Syncfusion Essential JS 2 Scripts -->
    <script src="https://cdn.syncfusion.com/ej2/dist/ej2.min.js"></script>
</head>
```

**Step 5:** Adding Script Manager in layout page `_Layout.cshtml`.

```html
<body>
    ....
    ....
    <!-- Syncfusion Essential JS 2 ScriptManager -->
    @Html.EJS().ScriptManager()
</body>
```

**Step 6:** Add the below code to your Index.cshtml view page which is present under Views/Home folder, to initialize the document editor.

{% aspTab template="document-editor/getting-started", sourceFiles="document-editor.cs" %}

{% endaspTab %}
