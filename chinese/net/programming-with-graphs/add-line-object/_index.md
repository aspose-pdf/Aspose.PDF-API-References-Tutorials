---
title: 添加线对象
linktitle: 添加线对象
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中添加自定义线条对象。
type: docs
weight: 30
url: /zh/net/programming-with-graphs/add-line-object/
---
在本教程中，我们将逐步引导您通过以下 C# 源代码使用 Aspose.PDF for .NET 添加线条对象。

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

## 第 4 步：创建线对象并添加到图表

我们创建一个具有指定坐标的 Line 对象，并将其添加到图表的形状集合中。

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## 第 5 步：线路设置

我们可以指定线条的属性，例如破折号类型和破折号阶段。

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## 第 6 步：保存 PDF 文件

最后，我们将生成的 PDF 文件保存在指定目录中，名称为“AddLineObject_out.pdf”。

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### 使用 Aspose.Words for .NET 添加行对象的示例源代码 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
//为 Graph 对象指定填充颜色
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
//将矩形对象添加到图形对象的形状集合
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
//保存PDF文件
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## 结论

在本教程中，我们逐步解释了如何使用 Aspose.PDF for .NET 添加线条对象。您现在可以使用这些知识在您的应用程序中创建带有自定义行的 PDF 文档。
