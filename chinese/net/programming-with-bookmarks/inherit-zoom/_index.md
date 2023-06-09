---
title: 继承缩放
linktitle: 继承缩放
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松继承 PDF 文件中的书签缩放。
type: docs
weight: 90
url: /zh/net/programming-with-bookmarks/inherit-zoom/
---

PDF 文档中的缩放继承允许您为书签指定默认缩放级别。使用 Aspose.PDF for .NET，您可以通过以下源代码轻松继承缩放：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要从中继承缩放的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 3 步：打开 PDF 文档

现在我们将使用以下代码打开要继承缩放的 PDF 文档：

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 第 4 步：获取书签收藏

在此步骤中，我们将使用`Outlines`的财产`doc`目的。下面是相应的代码：

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## 第 5 步：设置缩放级别

现在我们将通过创建一个`XYZExplicitDestination`具有指定 x、y 和 z 坐标的对象。这里我们使用坐标(100, 100, 0)，缩放为2。下面是对应的代码：

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## 第 6 步：为书签添加缩放级别

在这一步中，我们添加`XYZExplicitDestination`对象作为对书签的操作`item`收藏。下面是相应的代码：

```csharp
item. Action = new GoToAction(dest);
```

## 步骤 7：将更新后的书签添加到文档中

最后，我们使用将更新的书签添加到文档的书签集合中`Add`的方法`doc.Outlines`目的。下面是相应的代码：

```csharp
doc. Outlines. Add(item);
```

## 第 8 步：保存更新后的文件

现在让我们使用`Save`的方法`doc`目的。下面是相应的代码：

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 继承缩放的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document doc = new Document(dataDir + "input.pdf");
//获取 PDF 文件的大纲/书签集合
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
//将缩放级别设置为 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
//添加 XYZExplicitDestination 作为操作以概述 PDF 集合
item.Action = new GoToAction(dest);
//将项目添加到 PDF 文件的大纲集合
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
//保存输出
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## 结论

恭喜！现在，您有了使用 Aspose.PDF for .NET 继承缩放的分步指南。您可以使用此代码为 PDF 文档中的书签指定默认缩放级别。

请务必查看官方 Aspose.PDF 文档以获取有关高级书签操作功能的更多信息。