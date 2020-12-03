---
title: "PDF Export"
component: "TreeGrid"
description: "Documentation on exporting TreeGrid content to PDF format and customizing the exported document with headers and footers, and file name changes."
---

# PDF Export

PDF export allows exporting TreeGrid data to PDF document. You need to use the
[`pdfExport`](https://ej2.syncfusion.com/documentation/api/grid/#pdfexport) method for exporting. To enable PDF export in the treegrid, set the [`AllowPdfExport`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~AllowPdfExport.html) as true.

{% aspTab template="tree-grid/pdf-export/export", sourceFiles="export.cs" %}

{% endaspTab %}

## To customize PDF export

PDF export provides an option to customize mapping of treegrid to exported PDF document.

### File Name for Exported document

You can assign the file name for the exported document by defining [`fileName`](https://ej2.syncfusion.com/documentation/api/grid/pdfExportProperties/#filename) property in [`PdfExportProperties`](https://ej2.syncfusion.com/documentation/api/grid/pdfExportProperties/#properties).

{% aspTab template="tree-grid/pdf-export/file-name", sourceFiles="file-name.cs" %}

{% endaspTab %}

### Default Fonts for PDF exporting

By default, treegrid uses **Helvetica** font in the exported document. You can change the default font by using [`theme`](https://ej2.syncfusion.com/documentation/api/grid/pdfExportProperties/#theme) property in [`PdfExportProperties`](https://ej2.syncfusion.com/documentation/api/grid/pdfExportProperties/#properties).
The available default fonts are,

* Helvetica
* TimesRoman
* Courier
* Symbol
* ZapfDingbats

The code example for changing default font,

```typescript

    let pdfExportProperties = {
        theme: {
            header: {font:  new ej.pdfexport.PdfStandardFont(ej.pdfexport.PdfFontFamily.TimesRoman, 11, PdfFontStyle.Bold),
            caption: { font: new ej.pdfexport.PdfStandardFont(ej.pdfexport.PdfFontFamily.TimesRoman, 9) },
            record: { font: new ej.pdfexport.PdfStandardFont(ej.pdfexport.PdfFontFamily.TimesRoman, 10) }
        }
    };

```

### Add Custom Font for PDF exporting

You can change the default font of TreeGrid header, content and caption cells in the exported document by using [`theme`](https://ej2.syncfusion.com/documentation/api/grid/pdfExportProperties/#theme) property in [`PdfExportProperties`](https://ej2.syncfusion.com/documentation/api/grid/pdfExportProperties/#properties).

In the following example, we have used Advent Pro font to export the treegrid with Hungarian fonts.

{% aspTab template="tree-grid/pdf-export/custom-font", sourceFiles="custom-font.cs" %}

{% endaspTab %}

> **PdfTrueTypeFont** accepts base 64 format of the Custom Font.

### To add header and footer

You can customize text, page number, line, page size and changing orientation in header and footer.

#### How to write a text in header/footer

You can add text either in Header or Footer of exported PDF document.

```typescript

var exportProperties = {
    header: {
        fromTop: 0,
        height: 130,
        contents: [
            {
                type: 'Text',
                value: "Task Details",
                position: { x: 0, y: 50 },
                style: { textBrushColor: '#000000', fontSize: 13 }
            },

        ]
    }
}

```

#### How to draw a line in header/footer

you can add line either in Header or Footer of the exported PDF document.

Supported line styles:

* dash
* dot
* dashdot
* dashdotdot
* solid

```typescript

var exportProperties = {
    header: {
        fromTop: 0,
        height: 130,
        contents: [
            {
                type: 'Line',
                style: { penColor: '#000080', penSize: 2, dashStyle: 'Solid' },
                points: { x1: 0, y1: 4, x2: 685, y2: 4 }
            }
        ]
    }
}

```

#### Add page number in header/footer

you can add page number either in Header or Footer of exported PDF document.

Supported page number types:

* LowerLatin - a, b, c,
* UpperLatin - A, B, C,
* LowerRoman - i, ii, iii,
* UpperRoman - I, II, III,
* Number - 1,2,3.

```typescript

 var exportProperties = {
    header: {
        fromTop: 0,
        height: 130,
        contents: [
            {
                type: 'PageNumber',
                pageNumberType: 'Arabic',
                format: 'Page {$current} of {$total}', //optional
                position: { x: 0, y: 25 },
                style: { textBrushColor: '#ffff80', fontSize: 15, hAlign: 'Center' }
            }
        ]
    }
}

```

#### Insert an image in header/footer

Image (Base64 string) can be added in the exported document in header/footer using the [`PdfExportProperties`](https://ej2.syncfusion.com/documentation/api/grid/pdfExportProperties/#properties).

```typescript

var exportProperties = {
    header: {
        fromTop: 0,
        height: 130,
        contents: [
            {
                type: 'Image',
                src: image,
                position: { x: 40, y: 10 },
                size: { height: 100, width: 250 },
            }
        ]
    }
}

```

The below code illustrates the pdf export customization.

{% aspTab template="tree-grid/pdf-export/insert-image", sourceFiles="insert-image.cs" %}

{% endaspTab %}

### How to change page orientation

Page orientation can be changed Landscape(Default Portrait) for the exported document using the [`PdfExportProperties`](https://ej2.syncfusion.com/documentation/api/grid/pdfExportProperties/#pdfexportproperties).

{% aspTab template="tree-grid/pdf-export/page-orientation", sourceFiles="page-orientation.cs" %}

{% endaspTab %}

### How to change page size

Page size can be customized for the exported document using the [`PdfExportProperties`](https://ej2.syncfusion.com/documentation/api/grid/pdfExportProperties/#pdfexportproperties).
Supported page sizes are:

* Letter
* Note
* Legal
* A0
* A1
* A2
* A3
* A5
* A6
* A7
* A8
* A9
* B0
* B1
* B2
* B3
* B4
* B5
* Archa
* Archb
* Archc
* Archd
* Arche
* Flsa
* HalfLetter
* Letter11x17
* Ledger

{% aspTab template="tree-grid/pdf-export/page-size", sourceFiles="page-size.cs" %}

{% endaspTab %}

### Export hidden columns

PDF export provides an option to export hidden columns of TreeGrid by defining the [`includeHiddenColumn`](https://ej2.syncfusion.com/documentation/api/grid/pdfExportProperties/#includehiddencolumn) as **true**.

{% aspTab template="tree-grid/pdf-export/hidden-column", sourceFiles="hidden-column.cs" %}

{% endaspTab %}

### Show or Hide columns on Exported PDF

You can show a hidden column or hide a visible column while exporting the treegrid using [`ToolbarClick`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~ToolbarClick.html) and [`PdfExportComplete`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~PdfExportComplete.html) events.

In [`ToolbarClick`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~ToolbarClick.html) event, based on **args.item.text** as **PDF Export**. We can show or hide columns by setting [`Visible`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGridColumn~Visible.html) property to **true** or **false** respectively.

In [`PdfExportComplete`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~PdfExportComplete.html) event, We have reversed the state back to the previous state.

In the below example, we have **Duration** as a hidden column in the treegrid. While exporting, we have changed **Duration** to visible column and **StartDate** as hidden column.

{% aspTab template="tree-grid/pdf-export/show-hide-column", sourceFiles="show-hide-column.cs" %}

{% endaspTab %}

### Conditional Cell Formatting

TreeGrid cells in the exported PDF can be customized or formatted using [`PdfQueryCellInfo`](https://help.syncfusion.com/cr/cref_files/aspnetcore-js2/Syncfusion.EJ2~Syncfusion.EJ2.TreeGrid.TreeGrid~PdfQueryCellInfo.html) event. In this event, we can format the treegrid cells of exported PDF document based on the column cell value.

In the below sample, we have set the background color for **Duration** column in the exported document by **args.cell** and **backgroundColor** property.

{% aspTab template="tree-grid/pdf-export/conditional-cell", sourceFiles="conditional-cell.cs" %}

{% endaspTab %}

### Theme

PDF export provides an option to include theme for exported PDF document.

To apply theme in exported PDF, define the [`theme`](https://ej2.syncfusion.com/documentation/api/grid/pdfExportProperties/#theme) in [`PdfExportProperties`](https://ej2.syncfusion.com/documentation/api/grid/pdfExportProperties/#pdfexportproperties).

{% aspTab template="tree-grid/pdf-export/theme", sourceFiles="theme.cs" %}

{% endaspTab %}

> By default, material theme is applied to exported PDF document.
