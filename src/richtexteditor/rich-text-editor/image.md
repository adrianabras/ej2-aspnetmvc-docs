---
title: "ASP.NET MVC Rich Text Editor with image actions with upload"
component: "Rich Text Editor"
description: "The user guide section shows the option to insert images within your content with the caption, link, drag-and-drop images, image with the upload, and resize.."
---

# Image

Rich Text Editor allows to insert images from online sources as well as local computer where you want to insert the image in your content. For inserting the image to the Rich Text Editor, the following list of options have been provided in the [`InsertImageSettings`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.RichTextEditor.RichTextEditorBuilder.html#Syncfusion_EJ2_RichTextEditor_RichTextEditorBuilder_InsertImageSettings_Syncfusion_EJ2_RichTextEditor_RichTextEditorImageSettings_)

| Options | Description |
|----------------|---------|
| AllowedTypes | Specifies the extensions of the image types allowed to insert on bowering and passing the extensions with comma separators. For example, pass allowedTypes as .jpg and .png.|
| Display | Sets the default display for an image when it is inserted in to the Rich Text Editor. Possible options are: 'inline' and 'break'.|
| Width | Sets the default width of the image when it is inserted in the Rich Text Editor.|
| Height | Sets the default height of the image when it is inserted in the Rich Text Editor.|
| SaveUrl | Provides URL to map the action result method to save the image.|
| Path | Specifies the location to store the image.|
| Resize | To enable resizing for image element.|
| MinWidth | Defines the maximum Width of the image.|
| MaxWidth | Defines the maximum Width of the image.|
| MinHeight | Defines the minimum Height of the image.|
| MaxHeight | Defines the maximum Height of the image.|
| ResizeByPercent | Image resizing should be done by percentage calculation.|

## Upload Options

Through the `browse` option in the Image dialog, select the image from the local machine and insert into the Rich Text Editor content.

If the path field is not specified in the [`InsertImageSettings`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.RichTextEditor.RichTextEditorBuilder.html#Syncfusion_EJ2_RichTextEditor_RichTextEditorBuilder_InsertImageSettings_Syncfusion_EJ2_RichTextEditor_RichTextEditorImageSettings_), the image will be converted into blob url for the image will be created and the generated url will be set as src property of `<img>` tag as below.

```typescript

<img src="blob:http://ej2.syncfusion.com/3ab56a6e-ec0d-490f-85a5-f0aeb0ad8879" >

```

> If you want to insert a lot of tiny images in the editor and don't want a specific physical location for saving images, you can opt to save format as Base64.

In the below sample, the image has been load from the local machine and it will be saved in the given location.

{% aspTab template="rich-text-editor/image", sourceFiles="controller.cs" %}

{% endaspTab %}

## Server Side Action

The selected image can be uploaded to the required destination by using the below controller action. Map this method name in saveUrl property of [`InsertImageSettings`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.RichTextEditor.RichTextEditorBuilder.html#Syncfusion_EJ2_RichTextEditor_RichTextEditorBuilder_InsertImageSettings_Syncfusion_EJ2_RichTextEditor_RichTextEditorImageSettings_) and provide required destination path through path property.

> Note: The runnable demo application is available in this [Github](https://github.com/SyncfusionExamples/aspnet-mvc-richtexteditor-image-upload) repository.

{% aspTab template="rich-text-editor/save", sourceFiles="saveFile.cs" %}

{% endaspTab %}

## Image Delete

If you want to remove am image from the Rich Text Editor content, select the image and click “Remove” tool from quick toolbar. It will delete the image from the Rich Text Editor content.

Once you select the image from the local machine, the URL for the image will be generate, from there also you remove the image from the service location through the clicking of cross icon as below in the image.

![Rich Text Editor Image delete](./images/image-del.png)

## Insert from Web

If you want to insert an image from online source like Google, Ping, etc., you need to enable images tool on the editor’s toolbar. By default, the images tool is open an image dialog which allows you to insert an image from online source.

## Dimension

Sets the default width and height of the image when it is inserted in the Rich Text Editor using `Width` and `Height` of [`InsertImageSettings`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.RichTextEditor.RichTextEditorBuilder.html#Syncfusion_EJ2_RichTextEditor_RichTextEditorBuilder_InsertImageSettings_Syncfusion_EJ2_RichTextEditor_RichTextEditorImageSettings_).

Through the `quickToolbar`, also you can change the width and height using `Change Size` option. Once click into the option. The Image Size dialog will open as below. In that specify the width and height of the image in pixel.

![Rich Text Editor Image dimension](./images/image-size.png)

## Caption and Alt Text

Image caption and alternative text can be specified for the inserted image in the Rich Text Editor through the [`QuickToolbarSettings`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.RichTextEditor.RichTextEditorBuilder.html#Syncfusion_EJ2_RichTextEditor_RichTextEditorBuilder_QuickToolbarSettings_Syncfusion_EJ2_RichTextEditor_RichTextEditorQuickToolbarSettings_) options such as Image Caption and Alternative Text.

Through the Alternative Text option, set the alternative text for the image, when the image is not upload successfully into the Rich Text Editor.

By clicking the Image Caption, the image will get wrapped in an image element with a caption. Then, you can type caption content inside the Rich Text Editor.

## Display Position

Sets the default display for an image when it is inserted in the Rich Text Editor using `Display` field in [`InsertImageSettings`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.RichTextEditor.RichTextEditorBuilder.html#Syncfusion_EJ2_RichTextEditor_RichTextEditorBuilder_InsertImageSettings_Syncfusion_EJ2_RichTextEditor_RichTextEditorImageSettings_). It has two possible options: 'inline' and 'break'.

{% aspTab template="rich-text-editor/image-settings", sourceFiles="controller.cs" %}

{% endaspTab %}

## Image with Link

The hyperlink itself can be an image in Rich Text Editor. If the image given as hyperlink, the remove, edit and open link will be added to the quick toolbar of image as below. For further details about link, please see the [`link documentation`](./link).

![Rich Text Editor image with link](./images/image-link.png)

## Drag and Drop

By default, the Rich Text Editor allows you to insert images by drag-and-drop from the local file system such as Windows Explorer into the content editor area. And, you can upload the images to the server before inserting into the editor by configuring the saveUrl property. The images can be repositioned anywhere within the editor area by dragging and dropping the image.

In the following sample, you can see feature demo.

{% aspTab template="rich-text-editor/drag-drop", sourceFiles="controller.cs" %}

{% endaspTab %}

### Drag and drop with specific extension images

You can allow the specific images alone to be uploaded using the the allowedTypes property. By default, the Rich Text Editor allows the JPG, JPEG, and PNG formats. You can configure this formats as follows.

``` typescript

    insertImageSettings: {
      allowedTypes: ['.jpg']
    }

```

### Prevent drag and drop action

You can prevent drag-and-drop action by setting the actionBegin argument cancel value to true. The following code shows how to prevent the drag-and-drop.

``` typescript

    function actionBegin(args) {
        if(args.type === 'drop' || args.type === 'dragstart') {
            args.cancel =true;
        }
    }

```

## See Also

* [How to edit the quick toolbar settings](./toolbar/#quick-inline-toolbar)
* [How to use link editing option in the toolbar items](./link/)