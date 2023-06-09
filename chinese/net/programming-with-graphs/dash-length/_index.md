---
title: 破折号长度
linktitle: 破折号长度
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 设置破折号的长度。分步指南自定义破折号模式。
type: docs
weight: 70
url: /zh/net/programming-with-graphs/dash-length/
---
在本教程中，我们将逐步引导您通过以下 C# 源代码使用 Aspose.PDF for .NET 设置破折号的长度。

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
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## 第 4 步：创建线对象并配置

我们创建一个具有指定坐标的 Line 对象，并配置破折号的颜色和长度。

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## 第 5 步：将线添加到图形对象

我们将线条添加到 Graph 对象的形状集合中。

```csharp
canvas.Shapes.Add(line);
```

## 第 6 步：保存生成的 PDF 文件

最后，我们将生成的 PDF 文件保存在指定目录中，名称为“DashLength_out.pdf”。

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### 使用 Aspose.PDF for .NET 的 Dash Length 示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//实例化文档实例
Document doc = new Document();
//将页面添加到 Document 对象的页面集合
Page page = doc.Pages.Add();
//创建具有特定尺寸的绘图对象
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
//将绘图对象添加到页面实例的段落集合
page.Paragraphs.Add(canvas);
//创建线对象
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
//为 Line 对象设置颜色
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
//为线对象指定破折号数组
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
//为 Line 实例设置破折号阶段
line.GraphInfo.DashPhase = 1;
//向绘图对象的形状集合添加线条
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
//保存 PDF 文档
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## 结论

在本教程中，我们解释了如何使用 Aspose.PDF for .NET 设置破折号的长度。现在您可以使用这些知识在您的 PDF 文件中创建带有自定义破折号图案的线条。
