---
title: 创建填充矩形
linktitle: 创建填充矩形
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 创建填充矩形。自定义填充颜色的分步指南。
type: docs
weight: 50
url: /zh/net/programming-with-graphs/create-filled-rectangle/
---
在本教程中，我们将引导您逐步完成以下 C# 源代码，以使用 Aspose.PDF for .NET 创建填充矩形。

在开始之前，请确保您已经安装了 Aspose.PDF 库并设置了开发环境。还具备 C# 编程的基础知识。

## 第 1 步：文档目录设置

在提供的源代码中，您需要指定要保存生成的 PDF 文件的目录。将“dataDir”变量更改为所需的目录。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第2步：创建文档实例并添加页面

我们创建 Document 类的一个实例并向该文档添加一个页面。

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

## 第四步：创建矩形对象并添加到图表中

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

最后，我们将生成的 PDF 文件以名称“CreateFilledRectangle_out.pdf”保存在指定目录中。

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### 使用 Aspose.PDF for .NET 创建填充矩形的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建文档实例
Document doc = new Document();
//将页面添加到 PDF 文件的页面集合
Page page = doc.Pages.Add();
//创建图实例
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
//将图形对象添加到页面实例的段落集合中
page.Paragraphs.Add(graph);
//创建矩形实例
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
//指定 Graph 对象的填充颜色
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
//将矩形对象添加到图形对象的形状集合中
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
//保存 PDF 文件
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## 结论

在本教程中，我们解释了如何使用 Aspose.PDF for .NET 创建填充矩形。现在，您可以利用这些知识在 PDF 文件中创建具有自定义填充颜色的几何形状。

## 常见问题解答

#### 问：本教程的目的是什么？

答：本教程的目的是指导您完成使用 Aspose.PDF for .NET 创建填充矩形的过程，使您能够向 PDF 文件添加带有填充颜色的自定义几何形状。

#### 问：开始之前需要什么先决条件？

答：开始之前，请确保您已安装 Aspose.PDF 库并设置开发环境。此外，建议对 C# 编程有基本的了解。

#### 问：如何指定PDF文件的保存目录？

答：在提供的源代码中，您可以修改“dataDir”变量以指示要保存生成的 PDF 文件的目录。

#### 问：Graph 对象的用途是什么？

答：Graph 对象充当绘图元素的容器。它是使用指定的尺寸创建的，并添加到页面的段落集合中。

#### 问：如何在 PDF 文档中添加填充矩形？

答：要添加填充矩形，请创建具有指定尺寸和填充颜色的 Rectangle 类的实例，并将其添加到图形的形状集合中。

#### 问：我可以自定义矩形的尺寸和填充颜色吗？

 A：是的，您可以通过修改传入的参数来自定义矩形的尺寸和填充颜色`Aspose.Pdf.Drawing.Rectangle`构造函数并设置 FillColor 属性。

#### 问：创建填充矩形后如何保存生成的 PDF 文件？

答：创建填充矩形后，您可以使用以下命令保存生成的 PDF 文件：`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");`提供的源代码中的行。