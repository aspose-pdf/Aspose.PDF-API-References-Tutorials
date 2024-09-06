---
title: 创建填充矩形
linktitle: 创建填充矩形
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 创建填充矩形。逐步指导如何自定义填充颜色。
type: docs
weight: 50
url: /zh/net/programming-with-graphs/create-filled-rectangle/
---
在本教程中，我们将逐步引导您完成以下 C# 源代码，使用 Aspose.PDF for .NET 创建填充矩形。

开始之前，请确保您已安装 Aspose.PDF 库并设置开发环境。此外，还应具备 C# 编程的基本知识。

## 步骤 1：文档目录设置

在提供的源代码中，您需要指定要保存生成的 PDF 文件的目录。将“dataDir”变量更改为所需的目录。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤 2：创建文档实例并添加页面

我们创建 Document 类的一个实例，并向该文档添加一个页面。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 步骤 3：创建图形对象并将其添加到页面

我们创建一个具有指定尺寸的 Graph 对象并将其添加到页面的段落集合中。

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## 步骤 4：创建矩形对象并添加到图表

我们创建一个具有指定尺寸的矩形对象，并将其添加到图表的形状集合中。

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## 步骤 5：设置填充颜色

我们可以使用 GraphInfo 对象的 FillColor 属性指定矩形的填充颜色。

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## 步骤 6：保存生成的 PDF 文件

最后，我们将生成的PDF文件以“CreateFilledRectangle_out.pdf”为名保存在指定的目录中。

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### 使用 Aspose.PDF for .NET 创建填充矩形的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建 Document 实例
Document doc = new Document();
//将页面添加到 PDF 文件的页面集合
Page page = doc.Pages.Add();
//创建 Graph 实例
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
//将图形对象添加到页面实例的段落集合中
page.Paragraphs.Add(graph);
//创建 Rectangle 实例
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
//指定图形对象的填充颜色
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
//将矩形对象添加到图形对象的形状集合中
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
//保存 PDF 文件
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## 结论

在本教程中，我们解释了如何使用 Aspose.PDF for .NET 创建填充矩形。现在，您可以使用这些知识在 PDF 文件中创建具有自定义填充颜色的几何形状。

## 常见问题解答

#### 问：本教程的目的是什么？

答：本教程的目的是指导您完成使用 Aspose.PDF for .NET 创建填充矩形的过程，使您能够将带有填充颜色的自定义几何形状添加到 PDF 文件中。

#### 问：开始之前需要满足哪些先决条件？

答：开始之前，请确保您已安装 Aspose.PDF 库并设置开发环境。此外，建议您对 C# 编程有基本的了解。

#### 问：如何指定PDF文件的保存目录？

答：在提供的源代码中，您可以修改“dataDir”变量来指示您想要保存生成的 PDF 文件的目录。

#### 问：Graph 对象的用途是什么？

答：Graph 对象充当绘图元素的容器。它以指定的尺寸创建并添加到页面的段落集合中。

#### 问：如何在 PDF 文档中添加填充矩形？

答：要添加填充矩形，请创建具有指定尺寸和填充颜色的 Rectangle 类的实例，然后将其添加到图形的形状集合中。

#### 问：我可以自定义矩形的尺寸和填充颜色吗？

答：是的，您可以通过修改传递给`Aspose.Pdf.Drawing.Rectangle`构造函数并设置 FillColor 属性。

#### 问：创建填充矩形后，如何保存生成的 PDF 文件？

答：创建填充矩形后，您可以使用`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");`提供的源代码中的行。