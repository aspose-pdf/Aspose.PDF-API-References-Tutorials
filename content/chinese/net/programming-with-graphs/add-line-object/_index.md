---
title: 在 PDF 文件中添加线条对象
linktitle: 在 PDF 文件中添加线条对象
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中添加自定义线条对象。
type: docs
weight: 30
url: /zh/net/programming-with-graphs/add-line-object/
---
在本教程中，我们将引导您逐步完成以下 C# 源代码，以使用 Aspose.PDF for .NET 添加线条对象。

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

## 第 4 步：创建线条对象并添加到图表

我们使用指定的坐标创建一个 Line 对象，并将其添加到图表的形状集合中。

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## 第 5 步：线路设置

我们可以指定线条的属性，例如虚线类型和虚线相位。

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## 步骤 6：保存 PDF 文件

最后，我们将生成的 PDF 文件以名称“AddLineObject_out.pdf”保存在指定目录中。

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### 使用 Aspose.PDF for .NET 添加线条对象的示例源代码 

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
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
//指定 Graph 对象的填充颜色
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
//将矩形对象添加到图形对象的形状集合中
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
//保存 PDF 文件
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## 结论

在本教程中，我们逐步解释了如何使用 Aspose.PDF for .NET 添加线条对象。您现在可以利用这些知识在应用程序中创建带有自定义行的 PDF 文档。

### 在 PDF 文件中添加线条对象的常见问题解答

#### 问：本教程的目的是什么？

答：本教程旨在指导您完成使用 Aspose.PDF for .NET 添加线条对象以增强 PDF 文档的过程。

#### 问：开始之前需要什么先决条件？

答：开始之前，请确保您已经安装了 Aspose.PDF 库并设置了开发环境。此外，建议对 C# 编程有基本的了解。

#### 问：如何指定PDF文件的保存目录？

答：在提供的源代码中，您可以修改“dataDir”变量以指示要保存生成的 PDF 文件的目录。

#### 问：Graph 对象的用途是什么？

答：Graph 对象充当绘图元素的容器。它是使用指定的尺寸创建的，并添加到页面的段落集合中。

#### 问：如何在 PDF 文档中添加线条对象？

答：要添加线条对象，请创建具有指定坐标的 Line 类的实例，并将其添加到图形的形状集合中。

#### 问：我可以自定义线路的外观吗？

答：是的，您可以通过使用 Line 对象的 GraphInfo 属性设置破折号类型和破折号相位等属性来自定义线条的外观。

#### 问：指定破折号数组和破折号相位的目的是什么？

答：虚线阵列和虚线阶段属性允许您创建具有特定图案的虚线或点线。

#### 问：添加线条对象后如何保存PDF文件？

答：添加线条对象后，您可以使用以下命令保存生成的 PDF 文件：`doc.Save(dataDir + "AddLineObject_out.pdf");`提供的源代码中的行。

#### 问：有可用的示例源代码吗？

答：是的，本教程包含示例源代码，您可以参考它来实现所描述的步骤。