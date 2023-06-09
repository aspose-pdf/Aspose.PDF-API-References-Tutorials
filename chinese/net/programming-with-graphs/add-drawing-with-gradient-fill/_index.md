---
title: 添加带有渐变填充的绘图
linktitle: 添加带有渐变填充的绘图
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 添加带有渐变填充的绘图。分步教程创建有吸引力的 PDF 文档。
type: docs
weight: 20
url: /zh/net/programming-with-graphs/add-drawing-with-gradient-fill/
---
在本教程中，我们将逐步引导您完成以下 C# 源代码，以使用 Aspose.PDF for .NET 将带有渐变填充的绘图添加到图形编程中。

在开始之前，请确保您已经安装了 Aspose.PDF 库并设置了您的开发环境。还具有 C# 编程的基本知识。

## 第 1 步：文档目录设置

在提供的源代码中，您需要指定要保存生成的 PDF 文件的目录。将“dataDir”变量更改为所需的目录。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：实例化文档对象并添加页面

我们创建一个 Document 类的实例并向该文档添加一个页面。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 第 3 步：创建图形对象并将其添加到页面

我们创建一个具有指定尺寸的 Graph 对象并将其添加到页面的段落集合中。

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
```

## 第 4 步：创建矩形对象并添加到图表

我们创建一个具有指定尺寸的 Rectangle 对象并将其添加到图表的形状集合中。

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
```

## 第 5 步：配置渐变填充

我们使用 GradientAxialShading 类为矩形配置渐变填充。

```csharp
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
{
Start = new Point(0, 0),
End = new Point(300, 300)
}
};
```

这将创建从红色到蓝色、从点 (0, 0) 到点 (300, 300) 的渐变填充。

## 第 6 步：保存 PDF 文件

最后，我们将生成的 PDF 文件保存在指定目录中，名称为“AddDrawingWithGradientFill_out.pdf”。

```csharp
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");
```

### 使用 Aspose.PDF for .NET 添加带有渐变填充的绘图的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 300);
page.Paragraphs.Add(graph);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(0, 0, 300, 300);
graph.Shapes.Add(rect);
rect.GraphInfo.FillColor = new Aspose.Pdf.Color
{
	PatternColorSpace = new GradientAxialShading(Color.Red, Color.Blue)
	{
		Start = new Point(0, 0),
		End = new Point(300, 300)
	}
};
doc.Save(dataDir + "AddDrawingWithGradientFill_out.pdf");

```
## 结论

在本教程中，我们逐步解释了如何使用 Aspose.PDF for .NET 将带有渐变填充的绘图添加到图形编程中。现在您可以使用这些知识来创建具有自定义设计和渐变填充的有吸引力的 PDF 文档。