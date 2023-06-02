---
title: 画线
linktitle: 画线
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在页面上画一条线。创建自定义行的分步指南。
type: docs
weight: 80
url: /zh/net/programming-with-graphs/drawing-line/
---

在本教程中，我们将逐步引导您通过以下 C# 源代码使用 Aspose.PDF for .NET 绘制线条。

在开始之前，请确保您已经安装了 Aspose.PDF 库并设置了您的开发环境。还具有 C# 编程的基本知识。

## 第 1 步：文档目录设置

在提供的源代码中，您需要指定要保存生成的 PDF 文件的目录。将“dataDir”变量更改为所需的目录。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建文档实例并添加页面

我们创建一个 Document 类的实例并向该文档添加一个页面。

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## 第 3 步：设置页边距

我们将所有边的页边距设置为 0。

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## 第 4 步：创建图形对象和第一行

我们创建一个尺寸等于页面尺寸的 Graph 对象，并绘制从页面左下角到右上角的第一条线。

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## 第五步：绘制第二条线

我们绘制从页面左上角到右下角的第二条线。

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## 第 6 步：将图形对象添加到页面

我们将 Graph 对象添加到页面的段落集合中。

```csharp
pg.Paragraphs.Add(graph);
```

## 第 7 步：保存生成的 PDF 文件

最后，我们将生成的 PDF 文件保存在指定目录中，名称为“DrawingLine_out.pdf”。

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### 使用 Aspose.Words for .NET 绘制线条的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建文档实例
Document pDoc = new Document();
//将页面添加到 PDF 文档的页面集合
Page pg = pDoc.Pages.Add();
//设置四边页边距为0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
//创建宽度和高度等于页面尺寸的图形对象
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
//创建从页面左下角到右上角的第一行对象
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
//向 Graph 对象的形状集合添加线条
graph.Shapes.Add(line);
//从页面左上角到页面右下角画线
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
//向 Graph 对象的形状集合添加线条
graph.Shapes.Add(line2);
//将 Graph 对象添加到页面的段落集合
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
//保存PDF文件
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## 结论

在本教程中，我们解释了如何使用 Aspose.PDF for .NET 绘制线条。您现在可以使用这些知识在 PDF 文件中创建带有自定义线条的几何形状。
