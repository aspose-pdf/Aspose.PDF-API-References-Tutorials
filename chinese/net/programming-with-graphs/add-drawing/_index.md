---
title: 添加图纸
linktitle: 添加图纸
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 添加绘图。按照此分步指南创建具有绘图功能的有吸引力的 PDF 文档。
type: docs
weight: 10
url: /zh/net/programming-with-graphs/add-drawing/
---

应用程序开发通常需要添加绘图和图形等功能，以使文档更具吸引力和信息量。在本文中，我们将逐步指导您使用 C# 源代码将绘图添加到使用 Aspose.PDF for .NET 的图形编程中。

在开始之前，确保您已经安装了 Aspose.PDF 库并设置了您的开发环境。此外，请确保您具有 C# 编程的基本知识。

## 第一步：Aspose.PDF for .NET 介绍及其特性

Aspose.PDF 是一个功能强大且用途广泛的库，用于在 .NET 应用程序中创建、操作和转换 PDF 文件。它为处理 PDF 文档提供了广泛的功能，包括添加绘图、图形、文本等。

## 第二步：了解使用Aspose.PDF添加绘图的源码

提供的源代码使用 Aspose.PDF 库在 PDF 文档中创建简单的绘图。我们现在将详细检查代码的每个步骤。

## 第 3 步：配置文档目录并初始化变量

在源代码中，您需要指定要保存生成的 PDF 文件的目录。您可以修改“dataDir”变量以指示所需的目录。

此外，该代码还初始化了 alpha、红色、绿色和蓝色分量的变量。

## 第 4 步：使用 Alpha RGB 创建颜色对象

以下代码行使用指定的 alpha、红色、绿色和蓝色值创建 Color 对象：

```csharp
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue);
```

这允许使用 alpha 通道定义颜色，这意味着该颜色可以是部分透明的。

## 第 5 步：实例化文档对象

要开始使用 Aspose.PDF，我们需要创建一个 Document 类的实例。这代表我们的 PDF 文档。

```csharp
Document document = new Document();
```

## 第 6 步：向 PDF 文件添加页面

我们需要在要显示绘图的 PDF 文件中添加一个页面。

```csharp
Page page = document.Pages.Add();
```

## 第 7 步：创建具有维度的图形对象

在此步骤中，我们创建一个具有指定维度的 Graph 对象。这个对象将作为我们绘图的容器。

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
```

## 第 8 步：为绘图对象设置边框

我们可以使用 BorderInfo 类设置 Drawing 对象的边框。

```csharp
graph.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black);
```

这将在我们的绘图周围设置一个黑色边框。

## 第 9 步：将图形对象添加到页面

现在我们将图形对象添加到 Page 类实例的段落集合中。

```csharp
page.Paragraphs.Add(graph);
```

## 第 10 步：创建带尺寸的矩形对象

我们创建一个具有指定尺寸的 Rectangle 对象。这个矩形将被添加到我们的绘图中。

```csharp
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
```

## 步骤 11：为 Rectangle 实例创建一个 GraphInfo 对象

我们需要为 Rectangle 实例创建一个 GraphInfo 对象来配置它的图形属性。

```csharp
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
```

## 第 12 步：为 GraphInfo 对象配置颜色信息

我们可以使用 Color 和 FillColor 属性为 GraphInfo 对象配置颜色信息。

```csharp
graphInfo.Color = Aspose.Pdf.Color.Red;
graphInfo. FillColor = alphaColor;
```

这会将矩形边框颜色设置为红色，将填充颜色设置为指定的 alpha 颜色。

## 第 13 步：将矩形形状添加到图形对象

现在我们将矩形形状添加到图形对象的形状集合中。

```csharp
graph.Shapes.Add(rectangle);
```
## 第 14 步：保存 PDF 文件并显示成功消息

最后，我们保存 PDF 文件并显示绘图已成功添加的消息。

```csharp
dataDir = dataDir + "AddDrawing_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nSuccessfully added drawing with transparent color.\nFile saved to location: " + dataDir);
```

### 使用 Aspose.PDF for .NET 添加绘图的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
//使用 Alpha RGB 创建颜色对象
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue); //提供阿尔法通道
//实例化文档对象
Document document = new Document();
//将页面添加到 PDF 文件的页面集合
Page page = document.Pages.Add();
//创建具有特定维度的 Graph 对象
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
//为绘图对象设置边框
graph.Border = (new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black));
//将图形对象添加到 Page 实例的段落集合
page.Paragraphs.Add(graph);
//创建具有特定尺寸的矩形对象
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
//为 Rectangle 实例创建 graphInfo 对象
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
//为 GraphInfo 实例设置颜色信息
graphInfo.Color = (Aspose.Pdf.Color.Red);
//为 GraphInfo 设置填充颜色
graphInfo.FillColor = (alphaColor);
//将矩形形状添加到图形对象的形状集合
graph.Shapes.Add(rectangle);
dataDir = dataDir + "AddDrawing_out.pdf";
//保存PDF文件
document.Save(dataDir);
Console.WriteLine("\nDrawing added successfully with transparent color.\nFile saved at " + dataDir);            

```

## 结论

在本文中，我们学习了如何使用 Aspose.PDF for .NET 将绘图添加到图形编程中。我们按照分步指南了解源代码以及将绘图添加到 PDF 文件所涉及的各个步骤。使用 Aspose.PDF 的强大功能，您可以在您的 .NET 应用程序中创建有吸引力的交互式 PDF 文档。