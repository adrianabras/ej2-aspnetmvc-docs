---
title: "Validate image/* on drop"
component: "Uploader"
description: "Covers customizable features of the file upload control such as a preview image, invisible upload, progress bar, sort the file list and more."
---

# Validate image/* on drop

The uploader control allows you to select all types of images using the
*image/ ** to [allowedExtensions](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Inputs.Uploader.html#Syncfusion_EJ2_Inputs_Uploader_AllowedExtensions) property. You can directly set it to accept the attribute of uploader element.

By default, it is working fine when you select a file by clicking the browse button. But, this behavior is not supported to drag and drop the files for selection.

{% aspTab template="uploader/validate-image", sourceFiles="validate-image.cs,index.css" %}

{% endaspTab %}