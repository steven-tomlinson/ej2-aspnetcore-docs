---
title: "Getting Started"
component: "TreeView"
description: "Rendering treeview using asp.net core"
---

# Getting Started

 This section briefly explains about how to include a simple TreeView in your ASP.NET Core application. You can refer [ASP.NET Core Getting Started documentation](../getting-started/) page for introduction part part of the system requirements and configure the common specifications.

## Adding control to the Application

TreeView control can be rendered by using the `ejs-treeview` tag helper in ASP.NET Core application. Add the below simple code to your `index.cshtml` page which is available within the `Views/Home` folder, to initialize the TreeView.

The following example shows a basic TreeView control.

{% aspTab template="treeview/getting-started", sourceFiles="gettingstarted.cs" %}

{% endaspTab %}

## Binding data source

TreeView can load data either from local data sources or remote data services. This can be done using the dataSource property that is a member of the fields property. The dataSource property supports array of JavaScript objects and DataManager. Here, an array of JSON values is passed to the TreeView control.

{% aspTab template="treeview/binding-data/self-referential", sourceFiles="selfreferential.cs" %}

{% endaspTab %}

Output be like the below.

![TreeView Sample](./image/binding-self.PNG)