---
title: "Cell"
component: "Grid"
description: "Learn how to customize the Essential JS 2 DataGrid cells with styling, text wrapping, adding custom attributes and tooltips."
---

# Cell

## Displaying the HTML content

The HTML tags can be displayed in the Grid header and content by enabling the [`disableHtmlEncode`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridColumn.html#Syncfusion_EJ2_Grids_GridColumn_DisableHtmlEncode) property of **e-grid-column** tag helper.

{% aspTab template="grid/cell/html", sourceFiles="html.cs" %}

{% endaspTab %}

## Customize cell styles

The appearance of cells can be customized by using the [`queryCellInfo`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.Grid.html#Syncfusion_EJ2_Grids_Grid_QueryCellInfo) event.

The [`queryCellInfo`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.Grid.html#Syncfusion_EJ2_Grids_Grid_QueryCellInfo) event triggers for every cell.

{% aspTab template="grid/cell/customize", sourceFiles="customize.cs" %}

{% endaspTab %}

## Auto wrap

The auto wrap allows the cell content of the grid to wrap to the next line when it exceeds the boundary of the cell width. The Cell Content wrapping works based on the position of white space between words.
To enable auto wrap, set the [`allowTextWrap`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.Grid.html#Syncfusion_EJ2_Grids_Grid_AllowTextWrap) property to `true`.
You can configure the auto wrap mode by setting the [`wrapMode`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridTextWrapSettings.html#Syncfusion_EJ2_Grids_GridTextWrapSettings_WrapMode) property of **e-grid-textwrapsettings** tag helper.

There are three types of [`wrapMode`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridTextWrapSettings.html#Syncfusion_EJ2_Grids_GridTextWrapSettings_WrapMode). They are:

* **Both**: Both value is set by default. Auto wrap will be enabled for both the content and the header.
* **Header**: Auto wrap will be enabled only for the header.
* **Content**: Auto wrap will be enabled only for the content.

Note: When a column width is not specified, then auto wrap of columns will be adjusted with respect to the grid's width.

In the following example, the [`wrapMode`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridTextWrapSettings.html#Syncfusion_EJ2_Grids_GridTextWrapSettings_WrapMode) is set to **Content**.

{% aspTab template="grid/cell/autowrap", sourceFiles="autowrap.cs" %}

{% endaspTab %}

## Custom Attributes

You can customize the grid cells by adding a CSS class to the [`customAttribute`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.GridColumn.html#Syncfusion_EJ2_Grids_GridColumn_CustomAttributes) property of **e-grid-column** tag helper.

```CSS
.e-attr {
    background: #d7f0f4;
}
```

In the below example, we have customized the cells of **OrderID** and **ShipCity** columns.

{% aspTab template="grid/cell/customAttribute", sourceFiles="customStyle.cs" %}

{% endaspTab %}

## Grid Lines

The **GridLines** have option to display cell border and it can be defined by the
[`gridLines`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.Grid.html#Syncfusion_EJ2_Grids_Grid_GridLines) property.

The available modes of grid lines are:

| Modes | Actions |
|-------|---------|
| Both | Displays both the horizontal and vertical grid lines.|
| None | No grid lines are displayed.|
| Horizontal | Displays the horizontal grid lines only.|
| Vertical | Displays the vertical grid lines only.|
| Default | Displays grid lines based on the theme.|

{% aspTab template="grid/cell/gridlines", sourceFiles="gridlines.cs" %}

{% endaspTab %}

>By default, the grid renders with **Default** mode.

## Clip Mode

The clip mode provides options to display its overflow cell content and it can be defined by??the [`clipMode`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.ClipMode.html) property of **e-grid-column** tag helper.

There are three types of **ClipMode**. They are:

* **Clip**: Truncates the cell content when it overflows its area.
* **Ellipsis**: Displays ellipsis when the cell content overflows its area.
* **EllipsisWithTooltip**: Displays ellipsis when the cell content overflows its area, also it will display the tooltip while hover on ellipsis is applied.

{% aspTab template="grid/cell/clipmode", sourceFiles="clipmode.cs" %}

{% endaspTab %}

>By default, [`clipMode`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.ClipMode.html) value is **Ellipsis**.