---
title: "Working with Paragraph Formatting"
component: "DocumentEditor"
description: "Learn paragraph formatting supported in ASP.NET CORE document editor and how to apply it for selected contents."
---

# Working with Paragraph Formatting

Document editor supports various paragraph formatting options such as text alignment, indentation, paragraph spacing, and more.

## Indentation

You can modify the left or right indentation of selected paragraphs using the following sample code.

```typescript
documenteditor.selection.paragraphFormat.leftIndent= 24;
documenteditor.selection.paragraphFormat.rightIndent= 24;
```

## Special indentation

You can define special indent for first line of the paragraph using the following sample code.

```typescript
documenteditor.selection.paragraphFormat.firstLineIndent= 24;
```

## Increase indent

You can increase the left indent of selected paragraphs by a factor of 36 points using the following sample code.

```typescript
documenteditor.editor.increaseIndent()
```

## Decrease indent

You can decrease the left indent of selected paragraphs by a factor of 36 points using the following sample code.

```typescript
documenteditor.editor.decreaseIndent()
```

## Text alignment

You can get or set the text alignment of selected paragraphs using the following sample code.

```typescript
documenteditor.selection.paragraphFormat.textAlignment= 'Center' | 'Left' | 'Right' | 'Justify';
```

You can toggle the text alignment of selected paragraphs by specifying a value using the following sample code.

```typescript
documenteditor.editor.toggleTextAlignment('Center' | 'Left' | 'Right' | 'Justify');
```

## Line spacing and its type

You can define the line spacing and its type for selected paragraphs using the following sample code.

```typescript
documenteditor.selection.paragraphFormat.lineSpacingType='AtLeast';
documenteditor.selection.paragraphFormat.lineSpacing= 6;
```

## Paragraph spacing

You can define the spacing before or after the paragraph by using the following sample code.

```typescript
documenteditor.selection.paragraphFormat.beforeSpacing= 24;
documenteditor.selection.paragraphFormat.afterSpacing= 24;
```

## Toolbar with paragraph formatting options

The following sample demonstrates the paragraph formatting options using a toolbar.

{% aspTab template="document-editor/paragraph-format" %}

{% endaspTab %}

## See Also

* [Feature modules](../../document-editor/feature-module/)
* [Paragraph dialog](../../document-editor/dialog/#paragraph-dialog)
* [Keyboard shortcuts](../../document-editor/keyboard-shortcut/)
