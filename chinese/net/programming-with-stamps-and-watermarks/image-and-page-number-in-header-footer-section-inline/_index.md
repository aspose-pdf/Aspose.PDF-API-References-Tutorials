---
title: 页眉页脚部分内嵌的图像和页码
linktitle: 页眉页脚部分内嵌的图像和页码
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 使用内联段落在页眉和页脚中添加图像和页码。
type: docs
weight: 120
url: /zh/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉和页脚部分添加图像和页码。我们将使用提供的 C# 源代码创建一个页面，设置页眉和页脚，在 PDF 文档的页眉中使用内联段落添加图像和文本。

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
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

//在文档中创建页面
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

上面的代码在 PDF 文档中创建了一个新的 Document 对象和一个空白页面。

## 第 3 步：添加带有图像和内联文本的标题

现在页面已创建，我们可以使用内联段落添加带有图像和文本的标题部分。就是这样：

```csharp
//创建标题部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//设置页眉
page. Header = header;

//为第一个内联文本创建一个 TextFragment 对象
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

//指定文字颜色
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

//为图像创建一个 Image 对象
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//设置图片路径
image1.File = dataDir + "aspose-logo.jpg";

//定义图像的尺寸
image1.FixWidth = 50;
image1.FixHeight = 20;

//指示第一个内联文本是图像
image1.IsInLineParagraph = true;

//创建第二个内联文本
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

//将项目添加到标题
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

上面的代码创建了一个标题部分，用这个部分设置页眉，添加一个带有内联文本的 TextFragment 和一个内联图像对象。

## 第 4 步：保存修改后的 PDF 文档

添加带有图像和内联文本的页眉后，我们可以保存修改后的 PDF 文档。就是这样：

```csharp
//保存修改后的 PDF 文档
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

上述代码将编辑好的PDF文档保存到指定目录。

### 使用 Aspose.PDF for .NET 的 Imageand Page Numberin Header Footersection Inline 示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//通过调用其空构造函数来实例化一个 Document 对象
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

//在 Pdf 对象中创建页面
Aspose.Pdf.Page page = pdf1.Pages.Add();

//创建文档的标题部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//设置 PDF 文件的标题
page.Header = header;

//创建文本对象
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

//指定颜色
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

//在节中创建图像对象
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//设置图片文件路径
image1.File = dataDir + "aspose-logo.jpg";

//设置图像宽度信息
image1.FixWidth = 50;
image1.FixHeight = 20;

//表示 seg1 的 InlineParagraph 是一个图像。
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

//保存 PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## 结论

恭喜！您已经学习了如何使用 Aspose.PDF for .NET 使用内联段落在 PDF 文档的页眉和页脚部分添加图像和页码。您现在可以灵活地自定义 PDF 文档的页眉和页脚。
