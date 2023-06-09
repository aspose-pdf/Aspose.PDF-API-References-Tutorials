---
title: 添加图片
linktitle: 添加图片
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松地将图像添加到 PDF 文档。
type: docs
weight: 10
url: /zh/net/programming-with-images/add-image/
---

本指南将逐步指导您如何使用 Aspose.PDF for .NET 将图像添加到 PDF 文档。确保您已经设置了环境并按照以下步骤操作：

## 第一步：定义文档目录

在开始之前，请确保为文档设置了正确的目录。代替`"YOUR DOCUMENT DIRECTORY"`在代码中包含 PDF 文档所在目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：打开文档

在此步骤中，我们将使用`Document` Aspose.PDF 类。使用`Document`构造函数并将路径传递给 PDF 文档。

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## 第 3 步：设置图像坐标

设置要添加的图像的坐标。变量`lowerLeftX`, `lowerLeftY`, `upperRightX`和`upperRightY`分别代表图像的左下角和右上角的坐标。

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## 第四步：获取要添加图片的页面

要将图像添加到 PDF 文档的特定页面，我们首先需要检索该页面。在此示例中，我们将图像添加到文档的第二页（索引 1）。

```csharp
Page page = pdfDocument.Pages[1];
```

## 第 5 步：从流中加载图像

我们现在将加载要添加到 PDF 文档的图像。此示例假设您有一个名为`aspose-logo.jpg`在与您的文档相同的目录中。如有必要，替换文件名。

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## 第 6 步：将图像添加到页面资源

要在 PDF 文档中使用图像，我们需要将其添加到页面的资源图像集合中。

```csharp
page.Resources.Images.Add(imageStream);
```

## 第 7 步：保存当前图形状态

在绘制图像之前，我们需要使用`GSave`操作员。这确保了对图形状态的更改可以在以后回滚。

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## 步骤 8：创建矩形和矩阵对象

我们现在将创建一个`Rectangle`对象和一个`Matrix`目的。矩形表示图像的位置和大小，而矩阵定义图像的放置方式。

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## 第 9 步：连接矩阵以放置图像

要指定图像应如何放置在矩形中，我们使用`ConcatenateMatrix`操作员。该运算符定义了将图像的坐标空间映射到页面的坐标空间的变换矩阵。

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## 第 10 步：绘制图像

在这一步中，我们将使用`Do`操作员。这`Do`运算符从资源中获取图像名称并将其绘制到页面上。

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## 第十一步：恢复图形状态

绘制图像后，我们需要使用`GRestore`操作员。

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## 第 12 步：保存更新后的文档

最后，我们将更新后的文档保存到一个新文件中。更新`dataDir`具有所需输出目录和文件名的变量。

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 添加图像的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
//设定坐标
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
//获取需要添加图片的页面
Page page = pdfDocument.Pages[1];
//将图像加载到流中
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
//将图像添加到页面资源的图像集合
page.Resources.Images.Add(imageStream);
//使用 GSave 运算符：此运算符保存当前图形状态
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
//创建矩形和矩阵对象
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
//使用 ConcatenateMatrix（连接矩阵）运算符：定义必须如何放置图像
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
//使用 Do 运算符：此运算符绘制图像
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
//使用 GRestore 运算符：此运算符恢复图形状态
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
//保存更新的文档
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 将图像添加到 PDF 文档。我们详细介绍了从打开文档到保存更新版本的每一步。通过遵循本指南，您现在应该能够使用 C# 和 Aspose.PDF 以编程方式将图像嵌入到 PDF 文件中。