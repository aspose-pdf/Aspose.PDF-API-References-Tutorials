---
title: 将图像存储在 XImage 集合中
linktitle: 将图像存储在 XImage 集合中
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 XImage 集合中存储图像的分步指南。
type: docs
weight: 290
url: /zh/net/programming-with-images/store-image-in-ximage-collection/
---
在本教程中，我们将引导您了解如何使用 Aspose.PDF for .NET 在 XImage 集合中存储图像。请按照以下步骤轻松执行此操作。

## 先决条件

在开始之前，请确保您具备以下条件：

- 安装并配置 Visual Studio 或任何其他开发环境。
- C# 编程语言的基础知识。
- 安装了适用于.NET 的 Aspose.PDF 库。您可以从Aspose官方网站下载。

## 第1步：PDF文档初始化

首先，使用以下代码初始化一个新的 PDF 文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//初始化文档
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## 步骤 2：将图像添加到 XImage 集合中

接下来，我们将图像添加到 PDF 文档的 XImage 集合中。使用以下代码：

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

请务必提供图像源文件的正确路径。

## 步骤 3：将图像放置在页面上

现在让我们将图像放置在 PDF 文档的页面上。使用以下代码：

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

请务必提供最终 PDF 文档所需的路径和文件名。

### 使用 Aspose.PDF for .NET 在 XImage Collection 中存储图像的示例源代码 
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
//使用ConcatenateMatrix（连接矩阵）运算符：定义图像的放置方式
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## 结论

恭喜！您已使用 Aspose.PDF for .NET 成功将图像存储在 XImage 集合中。您现在可以将此方法应用到您自己的项目中，以操作和个性化 PDF 文件中的图像。

### 常见问题解答

#### 问：使用 Aspose.PDF for .NET 在 XImage 集合中存储图像的目的是什么？

答：将图像存储在 XImage 集合中可以让您有效地管理和使用 PDF 文档中的图像。这种方法使您能够在将图像放置到特定页面之前对其进行操作、自定义和个性化。

#### 问：在 XImage 集合中存储图像与直接将图像放置在 PDF 页面上有何不同？

答：将图像存储在 XImage 集合中提供了一种更有组织性和可重用性的图像管理方式。您无需将图像直接放置在页面上，而是将其存储在集合中，然后可以在需要时通过名称引用它，从而更轻松地管理和修改。

#### 问：我可以在单个 PDF 文档中将多个图像添加到 XImage 集合中吗？

答：是的，您可以将多个图像添加到同一 PDF 文档中的 XImage 集合中。每个图像在集合中都被分配了一个唯一的名称，可用于引用图像并将图像放置在不同的页面上。

#### 问：将 XImage 集合中的图像放置到 PDF 页面上时，如何指定图像的位置和大小？

A：要指定图像的位置和大小，需要定义一个矩形和一个矩阵变换。矩形定义图像的边界，矩阵变换指定图像应如何放置在该矩形内。

#### 问：这样做的目的是什么`GSave()` and `GRestore()` operators in the code for placing the image?

答： 的`GSave()`和`GRestore()`运算符用于保存和恢复PDF页面的图形状态。这样可以确保在页面上执行的操作（例如放置图像）不会影响图像放置后页面的状态。

#### 问：我可以对 XImage 集合中存储的图像应用其他修改或转换吗？

答：是的，您可以对 XImage 集合中存储的图像应用各种修改和转换。您可以使用 Aspose.PDF for .NET 提供的适当操作和技术来旋转、缩放、裁剪和执行其他转换。

#### 问：如何将此方法集成到我自己的项目中，以在 PDF 文档的 XImage 集合中存储和放置图像？

答：要集成此方法，请按照概述的步骤操作并修改代码以满足您的项目要求。您可以使用 XImage 集合来存储和管理图像，然后使用指定的坐标和转换将它们放置在特定页面上。

#### 问：在 Aspose.PDF for .NET 中使用 XImage 集合时是否有任何注意事项或限制？

答：虽然 XImage 集合提供了一种强大的方法来管理和操作图像，但考虑内存使用情况和对图像执行的操作的复杂性等因素也很重要。建议仔细管理收集并有效利用资源。

#### 问：我可以在多个 PDF 文档中重复使用 XImage 集合中存储的图像吗？

答：XImage 集合特定于每个 PDF 文档，并不是为跨文档重用而设计的。如果您需要在多个文档中重复使用图像，则需要为每个文档单独存储和管理它们。