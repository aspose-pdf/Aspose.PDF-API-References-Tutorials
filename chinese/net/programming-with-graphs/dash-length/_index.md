---
title: 短划线长度
linktitle: 短划线长度
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 设置破折号的长度。自定义破折号图案的分步指南。
type: docs
weight: 70
url: /zh/net/programming-with-graphs/dash-length/
---
在本教程中，我们将引导您逐步完成以下 C# 源代码，以使用 Aspose.PDF for .NET 设置破折号的长度。

在开始之前，请确保您已经安装了 Aspose.PDF 库并设置了开发环境。还具备 C# 编程的基础知识。

## 第 1 步：文档目录设置

在提供的源代码中，您需要指定要保存生成的 PDF 文件的目录。将“dataDir”变量更改为所需的目录。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：实例化文档对象并添加页面

我们创建 Document 类的一个实例并向该文档添加一个页面。

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

## 第 4 步：创建线路对象并配置

我们使用指定的坐标创建一个 Line 对象，并配置虚线的颜色和长度。

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## 第 5 步：将线条添加到图形对象

我们将线条添加到 Graph 对象的形状集合中。

```csharp
canvas.Shapes.Add(line);
```

## 第 6 步：保存生成的 PDF 文件

最后，我们将生成的 PDF 文件以名称“DashLength_out.pdf”保存在指定目录中。

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### 使用 Aspose.PDF for .NET 的 Dash Length 示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//实例化文档实例
Document doc = new Document();
//将页面添加到 Document 对象的页面集合中
Page page = doc.Pages.Add();
//创建具有特定尺寸的绘图对象
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
//将绘图对象添加到页面实例的段落集合中
page.Paragraphs.Add(canvas);
//创建线对象
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
//设置线条对象的颜色
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
//为线对象指定虚线数组
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
//设置 Line 实例的破折号相位
line.GraphInfo.DashPhase = 1;
//将线条添加到绘图对象的形状集合中
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
//保存 PDF 文档
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## 结论

在本教程中，我们解释了如何使用 Aspose.PDF for .NET 设置破折号的长度。现在，您可以利用这些知识在 PDF 文件中创建具有自定义虚线图案的线条。

## 常见问题解答

#### 问：本教程的目的是什么？

答：本教程的目的是指导您完成使用 Aspose.PDF for .NET 设置线条破折号长度的过程。您将学习如何在 PDF 文件中使用自定义虚线图案创建线条。

#### 问：开始之前需要什么先决条件？

答：开始之前，请确保您已经安装了 Aspose.PDF 库并设置了开发环境。还建议您对 C# 编程有基本的了解。

#### 问：如何指定PDF文件的保存目录？

答：修改提供的源代码中的“dataDir”变量以指示要保存生成的 PDF 文件的目录。

#### 问：如何创建具有自定义虚线图案的线条？

答：本教程演示了创建 Line 对象并使用以下命令配置其颜色、破折号数组和破折号相位：`GraphInfo`目的。修改这些设置以获得所需的虚线图案。

#### 问：我可以自定义线条的颜色吗？

答：是的，您可以通过设置来自定义线条的颜色`Color`的财产`GraphInfo`与线关联的对象。

#### 问：设置了破折号长度后如何保存PDF文档？

答：使用所需的虚线图案配置 Line 对象后，您可以使用以下命令保存生成的 PDF 文档：`doc.Save(dataDir + "DashLength_out.pdf");`提供的源代码中的行。