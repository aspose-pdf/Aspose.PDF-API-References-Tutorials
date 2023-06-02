---
title: 创建填充矩形
linktitle: 创建填充矩形
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 创建填充矩形。分步指南自定义填充颜色。
type: docs
weight: 50
url: /zh/net/programming-with-graphs/create-filled-rectangle/
---
在本教程中，我们将逐步引导您通过以下 C# 源代码使用 Aspose.PDF for .NET 创建一个填充矩形。

在开始之前，请确保您已经安装了 Aspose.PDF 库并设置了您的开发环境。还具有 C# 编程的基本知识。

## 第 1 步：文档目录设置

在提供的源代码中，您需要指定要保存生成的 PDF 文件的目录。将“dataDir”变量更改为所需的目录。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建文档实例并添加页面

我们创建一个 Document 类的实例并向该文档添加一个页面。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 第 3 步：创建图形对象并将其添加到页面

我们创建一个具有指定尺寸的 Graph 对象并将其添加到页面的段落集合中。

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## 第 4 步：创建矩形对象并添加到图表

我们创建一个具有指定尺寸的 Rectangle 对象，并将其添加到图表的形状集合中。

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## 第五步：设置填充颜色

我们可以使用 GraphInfo 对象的 FillColor 属性指定矩形的填充颜色。

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## 第 6 步：保存生成的 PDF 文件

最后，我们将生成的 PDF 文件保存在指定目录中，名称为“CreateFilledRectangle_out.pdf”。

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### 使用 Aspose.Words for .NET 创建填充矩形的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建文档实例
Document doc = new Document();
//将页面添加到 PDF 文件的页面集合
Page page = doc.Pages.Add();
//创建图形实例
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
//将图形对象添加到页面实例的段落集合
page.Paragraphs.Add(graph);
//创建矩形实例
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
//为 Graph 对象指定填充颜色
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
//将矩形对象添加到图形对象的形状集合
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
//保存PDF文件
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## 结论

在本教程中，我们解释了如何使用 Aspose.PDF for .NET 创建一个填充矩形。您现在可以使用这些知识在 PDF 文件中创建具有自定义填充颜色的几何形状。
