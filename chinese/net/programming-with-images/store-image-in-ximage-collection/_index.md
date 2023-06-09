---
title: 将图像存储在 XImage 集合中
linktitle: 将图像存储在 XImage 集合中
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将图像存储在 XImage 集合中的分步指南。
type: docs
weight: 290
url: /zh/net/programming-with-images/store-image-in-ximage-collection/
---

在本教程中，我们将带您了解如何使用 Aspose.PDF for .NET 在 XImage 集合中存储图像。按照以下步骤轻松执行此操作。

## 先决条件

在开始之前，请确保您具备以下条件：

- 安装和配置 Visual Studio 或任何其他开发环境。
- C# 编程语言的基本知识。
- 安装了 .NET 的 Aspose.PDF 库。可以从Aspose官网下载。

## 第一步：PDF文档初始化

首先，使用以下代码初始化一个新的 PDF 文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//初始化文件
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## 第 2 步：将图像添加到 XImage 集合

接下来，我们将图像添加到 PDF 文档的 XImage 集合中。使用以下代码：

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

请务必提供图像源文件的正确路径。

## 第 3 步：将图像放置在页面上

现在让我们将图像放在 PDF 文档的页面上。使用以下代码：

```csharp
page. Contents. Add(new GSave());

//设定坐标
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

请务必为最终 PDF 文档提供所需的路径和文件名。

### 使用 Aspose.PDF for .NET 在 XImage 集合中存储图像的示例源代码 
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
//设定坐标
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
//使用 ConcatenateMatrix（连接矩阵）运算符：定义必须如何放置图像
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## 结论

恭喜！您已使用 Aspose.PDF for .NET 成功地将图像存储在 XImage 集合中。您现在可以将此方法应用到您自己的项目中，以操作和个性化 PDF 文件中的图像。