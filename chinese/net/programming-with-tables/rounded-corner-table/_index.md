---
title: 圆角桌
linktitle: 圆角桌
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中创建圆角表格。
type: docs
weight: 190
url: /zh/net/programming-with-tables/rounded-corner-table/
---

在本教程中，我们将逐步指导您使用 Aspose.PDF for .NET 在 PDF 文档中创建圆角表格。我们将解释提供的 C# 源代码并向您展示如何实现它。

## 第 1 步：创建表
首先，我们将使用以下代码创建表：

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## 第 2 步：圆角样式设置
接下来，我们将为表格配置圆角样式：

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## 第 3 步：表格边框设置
为了给表格一个圆角边框，我们需要创建一个 BorderInfo 对象并用适当的参数配置它：

```csharp
//创建一个 GraphInfo 对象来设置边框颜色
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

//创建一个空的 BorderInfo 对象
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

//将圆角边框的半径设置为 15
bInfo.RoundedBorderRadius = 15;

//将边框信息应用于表格
tab1.Border = bInfo;
```

### 使用 Aspose.Words for .NET 的圆角表示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
//创建一个空白的 BorderInfo 对象
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
//将边框设置为更圆的边框，其中圆的半径为 15
bInfo.RoundedBorderRadius = 15;
//将表角样式设置为圆形。
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
//设置表格边框信息
tab1.Border = bInfo;
```

## 结论
恭喜！您现在已经了解了如何使用 Aspose.PDF for .NET 在 PDF 文档中创建圆角表格。本分步指南向您展示了如何设置圆角样式和表格边框。现在您可以将这些知识应用到您自己的项目中。