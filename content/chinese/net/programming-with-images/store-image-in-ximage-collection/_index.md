---
title: 将图像存储在 XImage 集合中
linktitle: 将图像存储在 XImage 集合中
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将图像存储在 XImage 集合中的分步指南。
type: docs
weight: 290
url: /zh/net/programming-with-images/store-image-in-ximage-collection/
---
在本教程中，我们将引导您了解如何使用 Aspose.PDF for .NET 将图像存储在 XImage 集合中。按照以下步骤轻松执行此操作。

## 先决条件

开始之前，请确保您已准备好以下物品：

- 已安装并配置 Visual Studio 或任何其他开发环境。
- C# 编程语言的基本知识。
- 已安装适用于 .NET 的 Aspose.PDF 库。您可以从 Aspose 官方网站下载。

## 步骤1：PDF文档初始化

首先，使用以下代码初始化一个新的 PDF 文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//初始化文档
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## 步骤 2：将图像添加到 XImage 集合

接下来，我们将图像添加到 PDF 文档的 XImage 集合中。使用以下代码：

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

确保提供图像源文件的正确路径。

## 步骤 3：将图像放置在页面上

现在让我们将图像放在 PDF 文档的页面上。使用以下代码：

```csharp
page. Contents. Add(new GSave());

//设置坐标
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

//使用 ConcatenateMatrix 运算符：定义图像的放置方式
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

这会将图像放置在页面上的指定坐标处。

## 步骤 4：保存 PDF 文档

最后，我们将保存更新后的 PDF 文档。使用以下代码：

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

确保提供最终 PDF 文档所需的路径和文件名。

### 使用 Aspose.PDF for .NET 将图像存储在 XImage 集合中的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//初始化文档
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
//设置坐标
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
//使用 ConcatenateMatrix（连接矩阵）运算符：定义图像必须如何放置
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## 结论

恭喜！您已成功使用 Aspose.PDF for .NET 将图像存储在 XImage 集合中。您现在可以将此方法应用于您自己的项目，以操作和个性化 PDF 文件中的图像。

### 常见问题解答

#### 问：使用 Aspose.PDF for .NET 将图像存储在 XImage 集合中有什么目的？

答：将图像存储在 XImage 集合中可让您高效地管理和使用 PDF 文档中的图像。此方法可让您在将图像放置在特定页面上之前对其进行操作、自定义和个性化。

#### 问：将图像存储在 XImage 集合中与直接将图像放在 PDF 页面上有何不同？

答：将图像存储在 XImage 集合中提供了一种更有条理、可重复使用的图像管理方法。您无需将图像直接放在页面上，而是将其存储在集合中，然后在需要时按名称引用它，从而更易于管理和修改。

#### 问：我可以在单个 PDF 文档中将多个图像添加到 XImage 集合中吗？

答：是的，您可以在同一个 PDF 文档中将多幅图像添加到 XImage 集合中。集合中每幅图像都分配有一个唯一名称，可用于引用和放置图像到不同的页面。

#### 问：将 XImage 集合中的图像放置在 PDF 页面上时，如何指定图像的位置和大小？

答：要指定图像的位置和大小，您需要定义一个矩形和一个矩阵变换。矩形定义图像的边界，矩阵变换指定图像应如何放置在该矩形内。

#### 问：`GSave()` and `GRestore()` operators in the code for placing the image?

答：`GSave()`和`GRestore()`操作符用于保存和恢复 PDF 页面的图形状态。这确保在页面上执行的操作（例如放置图像）不会影响放置图像后的页面状态。

#### 问：我可以对存储在 XImage 集合中的图像进行额外的修改或转换吗？

答：是的，您可以对存储在 XImage 集合中的图像进行各种修改和转换。您可以使用 Aspose.PDF for .NET 提供的适当操作和技术进行旋转、缩放、裁剪和执行其他转换。

#### 问：我如何将此方法集成到我自己的项目中，以将图像存储并放置在 PDF 文档的 XImage 集合中？

答：要集成此方法，请按照概述的步骤操作并修改代码以满足项目要求。您可以使用 XImage 集合来存储和管理图像，然后使用指定的坐标和变换将它们放置在特定页面上。

#### 问：使用 Aspose.PDF for .NET 中的 XImage 集合时有什么注意事项或限制吗？

答：虽然 XImage 集合提供了一种管理和操作图像的强大方法，但重要的是要考虑诸如内存使用量和对图像执行的操作的复杂性等因素。建议谨慎管理集合并有效利用资源。

#### 问：我可以在多个 PDF 文档中重复使用存储在 XImage 集合中的图像吗？

答：XImage 集合是针对每个 PDF 文档的，并非为跨文档重复使用而设计的。如果您需要在多个文档中重复使用图像，则需要为每个文档单独存储和管理它们。