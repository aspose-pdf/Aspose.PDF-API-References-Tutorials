---
title: 获取属性
linktitle: 获取属性
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 获取 PDF 属性（如框尺寸和旋转）的分步指南。
type: docs
weight: 100
url: /zh/net/programming-with-pdf-pages/get-properties/
---

在本教程中，我们将逐步引导您使用 Aspose.PDF for .NET 获取 PDF 的属性。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，以帮助您了解并在您自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.PDF for .NET 访问 PDF 页面的不同属性，例如艺术框、裁剪框、裁剪框等。

## 先决条件
在开始之前，请确保您具备以下条件：

- C#编程语言的基本知识
- 安装在您的开发环境中的 Aspose.PDF for .NET

## 第一步：设置文档目录
首先，您需要设置文档目录的路径。这是您要获取其属性的 PDF 文件的位置。用适当的路径替换“您的文档目录”。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：打开 PDF 文档
接下来，您需要使用`Document`Aspose.PDF 类。请务必指定 PDF 文件的正确路径。

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## 第 3 步：访问页面集合
现在您可以使用访问文档的页面集合`Pages`的财产`pdfDocument`目的。

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 第 4 步：转到特定页面
然后您可以使用集合中页面的索引跳转到特定页面。在下面的示例中，我们访问第二页（索引 1）。

```csharp
Page pdfPage = pageCollection[1];
```

## 第五步：获取页面属性
现在你可以通过使用相应的属性来获取PDF页面的不同属性，如艺术框、裁剪框、裁剪框等。`pdfPage`目的。

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### 使用 Aspose.PDF for .NET 获取属性的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
//获取页面集合
PageCollection pageCollection = pdfDocument.Pages;
//获取特定页面
Page pdfPage = pageCollection[1];
//获取页面属性
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## 结论
恭喜！您已经使用 Aspose.PDF for .NET 成功获取了 PDF 的属性。您学习了如何打开 PDF 文档、导航到特定页面以及获取各种页面属性，例如尺寸框和旋转。您现在可以使用此信息根据 PDF 文件的属性自定义处理 PDF 文件的方式。

请务必查看官方 Aspose.PDF for .NET 文档，了解有关高级功能和自定义可能性的更多信息。
