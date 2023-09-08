---
title: 获取 PDF 属性
linktitle: 获取 PDF 属性
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 获取 PDF 属性（例如框尺寸和旋转）的分步指南。
type: docs
weight: 100
url: /zh/net/programming-with-pdf-pages/get-properties/
---
在本教程中，我们将引导您逐步完成使用 Aspose.PDF for .NET 获取 PDF 属性的过程。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.PDF for .NET 访问 PDF 页面的不同属性，例如艺术框、裁剪框、裁剪框等。

## 先决条件
在开始之前，请确保您具备以下条件：

- C# 编程语言的基础知识
- 在您的开发环境中安装 Aspose.PDF for .NET

## 第1步：设置文档目录
首先，您需要设置文档目录的路径。这是您要获取其属性的 PDF 文件的位置。将“您的文档目录”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤 2：打开 PDF 文档
接下来，您需要使用以下命令打开 PDF 文档`Document`Aspose.PDF 类。请务必指定 PDF 文件的正确路径。

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## 第 3 步：访问页面集合
现在您可以使用以下命令访问文档的页面集合`Pages`的财产`pdfDocument`目的。

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 第四步：进入指定页面
然后，您可以使用集合中页面的索引跳转到特定页面。在下面的示例中，我们访问第二页（索引 1）。

```csharp
Page pdfPage = pageCollection[1];
```

## 第5步：获取页面属性
现在您可以通过使用PDF页面的相应属性来获取PDF页面的不同属性，例如艺术框，裁剪框，裁剪框等`pdfPage`目的。

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
恭喜！您已使用 Aspose.PDF for .NET 成功获取 PDF 的属性。您学习了如何打开 PDF 文档、导航到特定页面以及获取各种页面属性，例如尺寸框和旋转。现在，您可以使用此信息根据 PDF 文件的属性自定义 PDF 文件的处理方式。

请务必查看官方 Aspose.PDF for .NET 文档，以获取有关高级功能和自定义可能性的更多信息。

### 常见问题解答

#### 问：如何使用 Aspose.PDF for .NET 获取 PDF 的属性？

答：要使用 Aspose.PDF for .NET 获取 PDF 的属性，您可以按照以下步骤操作：

1. 通过指定要检索其属性的 PDF 文件的路径来设置文档目录。
2. 使用以下命令打开 PDF 文档`Document` Aspose.PDF 类，提供 PDF 文件的正确路径。
3. 使用以下命令访问文档的页面集合`Pages`的财产`pdfDocument`目的。
4. 使用集合中页面的索引跳转到特定页面（索引从1开始）。
5. 通过使用 PDF 页面的相应属性来获取 PDF 页面的不同属性，例如 ArtBox、BleedBox、CropBox、MediaBox、TrimBox、Rect、Page Number 和 Rotation`pdfPage`目的。

#### 问：使用 Aspose.PDF for .NET 可以检索的 PDF 页面有哪些不同属性？

答：您可以使用 Aspose.PDF for .NET 检索 PDF 页面的各种属性，例如：

- ArtBox：表示页面艺术品的尺寸。
- BleedBox：表示页面出血的尺寸。
- CropBox：表示裁剪后页面可见内容的尺寸。
- MediaBox：表示页面物理媒体的尺寸。
- TrimBox：表示页面修剪内容的尺寸。
- 矩形：表示页面边框的尺寸。
- 页码：表示文档中的页码。
- Rotate：表示页面的旋转角度。

#### 问：如何访问 PDF 文档中的特定页面以检索其属性？

答：要访问 PDF 文档中的特定页面并检索其属性，您可以使用`Pages`的财产`pdfDocument`对象来访问文档的页面集合。然后，您可以使用集合中页面的索引来跳转到所需的页面。例如，要访问第二页，您可以使用`pdfDocument.Pages[1]`（索引从1开始）。

#### 问：我可以对检索到的属性执行操作，例如修改页面框或调整页面框大小吗？

答：是的，一旦您使用 Aspose.PDF for .NET 检索 PDF 页面的属性，您就可以对它们执行各种操作。例如，您可以修改页面框的尺寸、旋转页面或使用检索到的信息对 PDF 文档进行自定义处理和操作。

#### 问：Aspose.PDF for .NET 支持从加密或受密码保护的 PDF 文件中提取属性吗？

答：是的，Aspose.PDF for .NET 支持从加密或受密码保护的 PDF 文件中提取属性。只要您提供正确的密码来打开 PDF 文档，您就可以使用教程中演示的相同方法访问和检索其属性。