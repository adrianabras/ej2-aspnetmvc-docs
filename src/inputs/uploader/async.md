---
title: "Asynchronous upload"
component: "Uploader"
description: "Explains how to upload single or multiple files using asynchronous mode with auto-upload, preload, and additional HTTP headers."
---

# Asynchronous upload

The uploader control allows you to upload the files asynchronously.
The upload process requires save and remove action URL to manage the upload process in the server.

    *   The save action is necessary to handle the upload operation.
    *   The remove action is optional, one can handle the removed files from server.

The File can be uploaded automatically or manually. For more information, you can refer to the [Auto Upload](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Inputs.Uploader.html#Syncfusion_EJ2_Inputs_Uploader_AutoUpload) section from the documentation.

## Multiple file upload

By Default, the uploader control allows you to select and upload multiple files simultaneously.
The selected files are organized in a list for every file selection until you clear it by clicking clear button that is shown in footer. You can add the multiple attributes to original input element of file by enabling the multiple file selection.
The following example explains about [multiple](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Inputs.Uploader.html#Syncfusion_EJ2_Inputs_Uploader_Multiple) file upload settings.

{% aspTab template="uploader/multiple", sourceFiles="multiple.cs" %}

{% endaspTab %}

## Single file upload

You can select and upload a single file by disabling the [multiple](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Inputs.Uploader.html#Syncfusion_EJ2_Inputs_Uploader_Multiple) file selection property.
The file list item is removed for every selection and it always maintain a single file to upload.
You can remove the multiple attributes form the original input element of file by enabling the single file upload property.

The following example explains about single file upload settings.

{% aspTab template="uploader/single", sourceFiles="single.cs" %}

{% endaspTab %}

## Save action

The save action handler upload the files that needs to be specified in the [saveUrl](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Inputs.UploaderAsyncSettings.html#Syncfusion_EJ2_Inputs_UploaderAsyncSettings_SaveUrl) property.
The save handler receives the submitted files and manages the save process in server.
After uploading the files to server location, the color of the selected file name changes to green and the remove
icon is changed as bin icon.

    *   When the file is uploaded successfully, the event “success” triggers to handle the operation after upload.
    *   When the file is failed to upload, the event “failure” triggers with information, which cause this failure.

You can cancel the upload process by setting the upload event argument **eventargs.cancel** to true.

{% aspTab template="uploader/save", sourceFiles="save.cs" %}

{% endaspTab %}

### Server-side configuration for save action

This section explains how to handle the server-side action for saving the file from server.

```csharp
[AcceptVerbs("Post")]
public void Save()
{
    try
    {
        var httpPostedFile = System.Web.HttpContext.Current.Request.Files["UploadFiles"];

        if (httpPostedFile != null)
        {
        var fileSave = System.Web.HttpContext.Current.Server.MapPath("UploadedFiles");
        var fileSavePath = Path.Combine(fileSave, httpPostedFile.FileName);
        if (!System.IO.File.Exists(fileSavePath))
            {
                HttpResponse Response = System.Web.HttpContext.Current.Response;
                Response.Clear();
                Response.ContentType = "application/json; charset=utf-8";
                Response.StatusDescription = "File uploaded succesfully";
                Response.End();
            }
            else
            {
                HttpResponse Response = System.Web.HttpContext.Current.Response;
                Response.Clear();
                Response.Status = "204 File already exists";
                Response.StatusCode = 204;
                Response.StatusDescription = "File already exists";
                Response.End();
            }
        }
    }
    catch (Exception e)
    {
        HttpResponse Response = System.Web.HttpContext.Current.Response;
        Response.Clear();
        Response.ContentType = "application/json; charset=utf-8";
        Response.StatusCode = 204;
        Response.Status = "204 No Content";
        Response.StatusDescription = e.Message;
        Response.End();
    }
}
```

## Remove action

The remove action is optional. Specify the URL to handle remove process from server.
The remove handler receives the posted files and handle the remove operation in server.

    *   When the files are removed successfully from the server, the success event triggers to denote the process has completed.
    *   When remove action fails, the event “failure” triggers with information, which cause failure in remove process.

> You can differentiate the file operation whether the success event triggers from save or remove action in its arguments **eventArgs.operation**.

You can remove the files which is not uploaded locally by clicking the remove icon. In this case, the success or failure events will not be triggered.

{% aspTab template="uploader/remove", sourceFiles="remove.cs" %}

{% endaspTab %}

### Server-side configuration for remove action

This section explains how to handle the server-side action for removing the file from server.

```csharp
[AcceptVerbs("Post")]
public void Remove()
{
    try
    {
        HttpResponse Response = System.Web.HttpContext.Current.Response;
        Response.Clear();
        Response.Status = "200 OK";
        Response.StatusCode = 200;
        Response.ContentType = "application/json; charset=utf-8";
        Response.StatusDescription = "File removed succesfully";
        Response.End();
    }
    catch (Exception e)
    {
        HttpResponse Response = System.Web.HttpContext.Current.Response;
        Response.Clear();
        Response.Status = "200 OK";
        Response.StatusCode = 200;
        Response.ContentType = "application/json; charset=utf-8";
        Response.StatusDescription = "File removed succesfully";
        Response.End();
    }
}

```

## Auto upload

By default, the uploader processes the files to upload once the files are selected and added in upload queue. To upload manually, disable the [autoUpload](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Inputs.Uploader.html#Syncfusion_EJ2_Inputs_Uploader_AutoUpload) property. When you disable this property, you can use the action buttons to call upload all or clear all actions manually. You can change those buttons text using the [buttons](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Inputs.Uploader.html#Syncfusion_EJ2_Inputs_Uploader_Buttons) &nbsp;property in Uploader control.

{% aspTab template="uploader/auto-upload", sourceFiles="auto-upload.cs" %}

{% endaspTab %}

Auto upload output be like the below.

![uploader](./images/uploader-auto-01.png)

Auto upload false output be like the below.

![uploader](./images/uploader-auto-02.png)

## Sequential upload

By default, the uploader control process multiple files to upload simultaneously. When you enable the [sequentialUpload](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Inputs.Uploader.html#Syncfusion_EJ2_Inputs_Uploader_SequentialUpload) property, the selected files will process sequentially (one after the other) to the server. If the file uploaded successfully or failed, the next file will upload automatically in this sequential upload. This feature helps to reduce the upload traffic and reduce the failure of file upload.

{% aspTab template="uploader/sequential-upload", sourceFiles="sequential-upload.cs" %}

{% endaspTab %}

## Preload files

The uploader control allows you to preload the list of files that are uploaded in the server. The preloaded files are useful to view and remove the files from server that can be achieved by the [files](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Inputs.Uploader.html#Syncfusion_EJ2_Inputs_Uploader_Files) property. By default, the files are configured with uploaded successfully state on rendering file list. The following properties are mandatory to configure the preloaded files:

    *   Name
    *   Size
    *   Type

{% aspTab template="uploader/file-preload", sourceFiles="preload-file.cs" %}

{% endaspTab %}

Output be like the below.

![uploader](./images/uploader-preload.png)

## Adding additional HTTP headers with upload action

The Uploader control allows you to add the additional headers with `save` and `remove` action requests using the [uploading](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Inputs.Uploader.html#Syncfusion_EJ2_Inputs_Uploader_Uploading) and [removing](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Inputs.Uploader.html#Syncfusion_EJ2_Inputs_Uploader_Removing) events, which helps to send validation token on file upload. Access the current request and set the request header within these events.

The following code block shows how to add the additional headers with save and remove action request.

```html
   @Html.EJS().Uploader("UploadFiles").DropArea(".control-fluid").Uploading("addHeaders").Removing("addHeaders").AsyncSettings(new Syncfusion.EJ2.Inputs.UploaderAsyncSettings { SaveUrl = "https://ej2.syncfusion.com/services/api/uploadbox/Save", RemoveUrl = "https://ej2.syncfusion.com/services/api/uploadbox/Remove" }).Render()

```

```javascript
    function addHeaders(args) {
        args.currentRequest.setRequestHeader('custom-header', 'Syncfusion');
    }

```

## See Also

* [How to add additional data on upload](./how-to/add-additional-data-on-upload)
* [How to add confirm dialog to remove the files](./how-to/add-confirm-dialog-to-remove-the-files)
* [Check the MIME type of file before uploading it](./how-to/check-the-mime-type-of-file-before-upload-it)
* [How to open and edit the uploaded files](./how-to/open-and-edit-the-uploaded-files)