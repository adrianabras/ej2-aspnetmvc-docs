---
title: "How to"
component: "DocumentEditor"
description: "Learn how to work with document editor in real time scenarios like create simple word processor, override keyboard shortcut behaviors, and more."
---

# How to override the keyboard shortcuts in document editor

Document editor triggers the [`keyDown`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.DocumentEditor.DocumentEditor.html#Syncfusion_EJ2_DocumentEditor_DocumentEditor_KeyDown) event every time when any key is entered and provides an instance of `DocumentEditorKeyDownEventArgs`. You can use the `isHandled` property to override the keyboard shortcut behaviour.

## Preventing default keyboard shortcut

The following code shows how to prevent the `CTRL + C` keyboard shortcut for copying selected content in document editor.

{% aspTab template="document-editor/prevent-default" %}

{% endaspTab %}

## Override or define the keyboard shortcut

Override or define a new keyboard shortcut behaviour instead of preventing the keyboard shortcut.

For example, `Ctrl + S` keyboard shortcut saves the document in SFDT format by default, and there is no behaviour for `Ctrl + Alt + S`. The following code demonstrates how to override the `Ctrl + S` shortcut to save a document in DOCX format and define `Ctrl + Alt + S` to save the document in SFDT format.

{% aspTab template="document-editor/override" %}

{% endaspTab %}