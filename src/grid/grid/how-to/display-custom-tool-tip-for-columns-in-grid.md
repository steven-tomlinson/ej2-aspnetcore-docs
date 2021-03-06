---
title: "Display custom ToolTip for columns in Grid"
component: "Grid"
description: "Learn how to Display custom ToolTip for columns in Grid."
---

# Display custom ToolTip for columns in Grid

To display custom ToolTip **EJ2 Tooltip**, use the
[`queryCellInfo`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.Grid.html#Syncfusion_EJ2_Grids_Grid_QueryCellInfo) event.

Render the ToolTip component for the grid cells by using the following code in the [`queryCellInfo`](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Grids.Grid.html#Syncfusion_EJ2_Grids_Grid_QueryCellInfo) event.

```typescript

function tooltip (args) {
    var tooltip = new ej.popups.Tooltip({
        content: args.data[args.column.field].toString();
    }, args.cell);
}

```

{% aspTab template="grid/how-to/custom-tooltip", sourceFiles="custom-tooltip.cs" %}

{% endaspTab %}
