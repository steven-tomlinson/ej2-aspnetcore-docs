---
title: "ASP.NET Core Rich Text Editor Miscellaneous"
component: "Rich Text Editor"
description: "This section for Syncfusion ASP.NET CORE Rich Text Editor control explains on how to directly edit HTML code via `Source View` in the text area."
---

# Miscellaneous

## Placeholder

Specifies the placeholder for the Rich Text Editor’s content used when the Rich Text Editor body is empty through the [`placeholder`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.RichTextEditor.RichTextEditor.html#Syncfusion_EJ2_RichTextEditor_RichTextEditor_Placeholder) property.

Through the `e-rte-placeholder` class we can able to define our custom font family, font color and styles to the placeholder text.

```css

.e-richtexteditor .e-rte-placeholder {
    font-family: monospace;
}

```

The below sample demonstrates the `placeholder` option in Rich Text Editor.

{% aspTab template="rich-text-editor/placeholder", sourceFiles="controller.cs" %}

{% endaspTab %}

## Character Count

The Rich Text Editor automatically counts the number of characters in the content area while typing using [`showCharCount`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.RichTextEditor.RichTextEditor.html#Syncfusion_EJ2_RichTextEditor_RichTextEditor_ShowCharCount) property. The characters count displayed at the bottom right of the editor. Limit the number of character in the Rich Text Editor's content using [`maxLength`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.RichTextEditor.RichTextEditor.html#Syncfusion_EJ2_RichTextEditor_RichTextEditor_MaxLength) property. By default, the editor sets the characters limit value is infinity.

The character count color will be modified based on the characters in the Rich Text Editor.

| Status | Description |
|----------------|---------|
| normal | Till 70% of given maxLength count reach, character count color is black.|
| warning | Once the number of character count in the Rich Text Editor reached 70% of given maxLength count, the character count color will be orange, indicating that, the Rich Text Editor value going to reach the maximum count.|
| error | Once the number of character count in the Rich Text Editor reached 90% of given maxLength count, the character count color will be red, indicating that, the Rich Text Editor value reached the maximum count.|

{% aspTab template="rich-text-editor/character-count", sourceFiles="controller.cs" %}

{% endaspTab %}

## Print

The editor provides print tools which use to print the contents of the editor.

{% aspTab template="rich-text-editor/print", sourceFiles="controller.cs" %}

{% endaspTab %}

## Code View

Rich Text Editor includes the ability for users to directly edit HTML code via `Source View` in the text area. If you made any modification in Source view directly, the changes will be reflected in the Rich Text Editor's content. So, the users will have more flexibility over the content they have created.

This sample used [`Code mirror`](https://codemirror.net/) plugin helps to highlight the HTML content and when changes happens in code view, the same has been reflected in preview mode.

{% aspTab template="rich-text-editor/code-mirror", sourceFiles="controller.cs" %}

{% endaspTab %}

## Full Screen

Stretches the editor to the maximum width and height of the browser window through the `FullScreen` tool in the toolbar.

{% aspTab template="rich-text-editor/fullscreen", sourceFiles="controller.cs" %}

{% endaspTab %}

## Prevention of cross-site scripting (XSS)

The Rich Text Editor allows the users to edit the content with security by preventing cross-site
scripting (XSS). By default, provided built-in support to remove the elements from editor content, which cause XSS
attack. The editor removes the elements based on the attributes if it is possible to execute script.

In the following sample, removed `script` tag and `onmouseover` attribute from content of the Rich Text Editor.

{% aspTab template="rich-text-editor/cross", sourceFiles="controller.cs" %}

{% endaspTab %}

> It is only applicable to editorMode as HTML.

### Custom cross-site scripting

You can also filter the elements and attributes additionally, which cause the XSS attack through
[`beforeSanitizeHtml`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.RichTextEditor.RichTextEditor.html#Syncfusion_EJ2_RichTextEditor_RichTextEditor_BeforeSanitizeHtml) event. Return the value from the event argument `helper` function to apply in the editor. To prevent the built-in support and make own cross-site scripting rules, set `cancel` argument to true.

The following sample demonstrates how to filter `script` tag from value.

{% aspTab template="rich-text-editor/custom-cross", sourceFiles="controller.cs" %}

{% endaspTab %}

## Resizable support

This feature allows the editor to be resized dynamically. The users can enable or disable this feature using the `enableResize` property in the Rich Text Editor. If `enableResize` is set to true, the Rich Text Editor component creates grip at the bottom right corner, which allows resizing the component in the diagonal direction. The following code demonstrates the resizable feature.

### Enabling the resizable support

To render the Rich Text Editor in the resizable mode, set the `enableResize` property to true.

{% aspTab template="rich-text-editor/resizable", sourceFiles="controller.cs" %}

{% endaspTab %}

![Rich Text Editor Resizable support](./images/Resizable-Editor.png)

### Specifying the Minimum and Maximum width and height for Resize

To have a restricted resizable area for the Rich Text Editor, you need to specify the min-width, max-width, min-height, and max-height CSS properties for the control's wrapper element. By default, the control is capable of resizing upto the current viewport. The `e-richtexteditor` CSS class will be available in the component's wrapper and can be used for applying the above mentioned styles.

{% aspTab template="rich-text-editor/max-resizable", sourceFiles="controller.cs" %}

{% endaspTab %}
