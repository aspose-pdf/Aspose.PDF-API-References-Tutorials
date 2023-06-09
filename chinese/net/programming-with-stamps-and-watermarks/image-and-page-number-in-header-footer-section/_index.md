---
title: 页眉页脚部分中的图像和页码
linktitle: 页眉页脚部分中的图像和页码
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose 在 PDF 文档的页眉和页脚中添加图像和页码。
type: docs
weight: 110
url: /zh/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉和页脚部分添加图像和页码。我们将向您展示如何使用提供的 C# 源代码创建页面、设置页眉和页脚、将图像添加到页眉以及将带页码的文本添加到文档页脚 PDF。

## 第 1 步：设置环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 在您的项目中下载并引用了用于 .NET 的 Aspose.PDF 库。

## 第 2 步：创建 PDF 文档和页面

第一步是在 PDF 文档中创建一个新的 Document 对象和一个页面。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建一个新的文档对象
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//在文档中创建页面
Aspose.Pdf.Page page = doc.Pages.Add();
```

上面的代码在 PDF 文档中创建了一个新的 Document 对象和一个空白页面。

## 第 3 步：添加带图像的标题

现在页面已创建，我们可以添加带有图像的标题部分。就是这样：

```csharp
//创建标题部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//设置页眉
page. Header = header;

//创建图像对象
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//设置图片路径
image1.File = dataDir + "aspose-logo.jpg";

//将图像添加到 PDF 文档的页眉
header.Paragraphs.Add(image1);
```

上面的代码创建了一个页眉部分，用这个部分设置页眉，并向页眉添加一个图像。

## 第 4 步：添加带有页码的页脚

现在添加了页眉，我们可以添加带有页码的页脚部分。就是这样：

```csharp
//创建页脚部分
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

//定义 PDF 文档的页脚
page. Footer = footer;

//创建一个 TextFragment 对象
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

//将带有页码的文本添加到 PDF 文档的页脚
footer.Paragraphs.Add(txt);
```

上面的代码创建了一个页脚部分，用这个部分设置页面的页脚，并添加一个包含文本“Page: ($p of $P)”的 TextFragment

  显示页码。

## 步骤 5：保存修改后的 PDF 文档

添加页眉和页脚后，我们可以保存修改后的 PDF 文档。就是这样：

```csharp
//保存修改后的 PDF 文档
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

上述代码将编辑好的PDF文档保存到指定目录。

### 使用 Aspose.PDF for .NET 的页眉页脚部分中图像和页码的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//在文档对象中创建页面
Aspose.Pdf.Page page = doc.Pages.Add();

//创建文档的标题部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//设置 PDF 文件的标题
page.Header = header;

//在页面中创建图像对象
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//设置图片文件路径
image1.File = dataDir + "aspose-logo.jpg";

//将图像添加到 Pdf 文件的页眉
header.Paragraphs.Add(image1);

//创建文档的页脚部分
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

//设置 PDF 文件的页脚
page.Footer = footer;

//创建文本对象
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

//将文本添加到 Pdf 文件的页眉部分
footer.Paragraphs.Add(txt);

//保存 Pdf 文件
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## 结论

恭喜！您已经学习了如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉和页脚部分添加图像和页码。现在您可以使用此方法自定义 PDF 文档中的页眉和页脚。
