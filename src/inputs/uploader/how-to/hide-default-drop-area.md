---
title: "Hide default drop area"
component: "Uploader"
description: "Covers customizable features of the file upload control such as a preview image, invisible upload, progress bar, sort the file list and more."
---

# Hide default drop area

You can achieve this behavior by overriding the corresponding uploader styles. Override the following styles to hide the default drop area behavior.

    * .e-upload.e-control
    * .e-upload .e-file-select
    * .e-upload .e-file-drop

{% aspTab template="uploader/hide-drop", sourceFiles="hide-drop.cs,index.css" %}

{% endaspTab %}