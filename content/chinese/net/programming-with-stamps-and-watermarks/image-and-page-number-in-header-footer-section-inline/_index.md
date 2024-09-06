---
title: 页眉页脚部分内联中的图像和页码
linktitle: 页眉页脚部分内联中的图像和页码
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 的内联段落在页眉和页脚中添加图像和页码。
type: docs
weight: 120
url: /zh/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉和页脚部分添加图像和页码。我们将使用提供的 C# 源代码创建页面、设置页眉和页脚，并使用 PDF 文档页眉中的内联段落添加图像和文本。

## 步骤 1：设置环境

开始之前，请确保您已准备好以下物品：

- 已安装的 .NET 开发环境。
- 已下载并引用适用于 .NET 的 Aspose.PDF 库到您的项目中。

## 步骤 2：创建 PDF 文档和页面

第一步是在 PDF 文档中创建一个新的 Document 对象和一个页面。操作方法如下：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建新的 Document 对象
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

//在文档中创建页面
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

上面的代码在 PDF 文档中创建了一个新的 Document 对象和一个空白页。

## 步骤 3：添加带有图片和内联文本的标题

现在页面已创建，我们可以使用内联段落添加带有图像和文本的标题部分。操作方法如下：

```csharp
//创建标题部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//设置页眉
page. Header = header;

//为第一个内联文本创建 TextFragment 对象
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

//指定文本颜色
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

//为图像创建 Image 对象
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

上面的代码创建了一个标题部分，并用此部分设置页面标题，并添加了一个带有内联文本和内联图像对象的 TextFragment。

## 步骤 4：保存修改后的 PDF 文档

添加带有图像和内联文本的页眉后，我们可以保存修改后的 PDF 文档。操作方法如下：

```csharp
//保存修改后的PDF文档
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

上述代码将编辑后的PDF文档保存到指定目录。

### 使用 Aspose.PDF for .NET 内联页眉页脚部分中的图像和页码的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//通过调用空构造函数来实例化 Document 对象
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

//在 Pdf 对象中创建一个页面
Aspose.Pdf.Page page = pdf1.Pages.Add();

//创建文档的页眉部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//设置 PDF 文件的页眉
page.Header = header;

//创建文本对象
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

//指定颜色
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

//在部分中创建一个图像对象
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//设置图片文件路径
image1.File = dataDir + "aspose-logo.jpg";

//设置图片宽度信息
image1.FixWidth = 50;
image1.FixHeight = 20;

//表明 seg1 的 InlineParagraph 是一张图片。
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

恭喜！您已经学会了如何使用 Aspose.PDF for .NET 的内联段落在 PDF 文档的页眉和页脚部分添加图像和页码。现在您可以灵活地自定义 PDF 文档的页眉和页脚。

### 常见问题解答

#### 问：使用内联段落将图像和文本添加到 PDF 文档的页眉有什么好处？

答：使用内联段落可让您在同一段落中无缝集成图像和文本，从而精确控制其位置和格式。此方法对于使用视觉元素创建自定义标题特别有用。

#### 问：提供的 C# 源代码如何实现 PDF 文档中页眉的内联段落？

答：提供的代码演示了如何创建 PDF 文档、添加页面以及使用内联段落自定义页眉。它添加了一个带有内联文本的 TextFragment、一个内联图像和另一个内联 TextFragment。

#### 问：如何指定页眉中的内嵌文本的颜色？

答：内联文本的颜色使用`ForegroundColor`的财产`TextState`的`TextFragment`目的。

#### 问：我可以调整页眉内嵌图像的尺寸吗？

答：是的，您可以使用`FixWidth`和`FixHeight`的属性`Image`对象。这允许您控制标题内图像的宽度和高度。

#### 问：我可以在标题中包含额外的内联元素，例如超链接或不同的字体样式吗？

答：是的，您可以通过创建更多内容在标题中包含其他内联元素`TextFragment`或者`Image`具有所需属性的对象。这允许您进一步自定义标题，包括超链接、不同的字体样式或其他视觉元素。

#### 问：如何确保内联图像和文本在不同的设备和查看器上保持正确对齐和格式？

答：Aspose.PDF for .NET 可确保内联图像和文本正确对齐和格式化，从而实现不同设备和 PDF 查看器之间的一致外观。

#### 问：我也可以将内联段落应用到页脚部分吗？

答：是的，您可以通过创建`Footer`对象并向其中添加文本和图像等内联元素。

#### 问：是否可以将内联段落与其他页眉或页脚自定义方法结合起来？

答：是的，您可以将内联段落与 Aspose.PDF for .NET 提供的其他页眉或页脚自定义方法相结合，以创建更复杂、更量身定制的页眉或页脚设计。

#### 问：如果需要，我可以从标题中删除或清除内联元素吗？

答：是的，你可以通过修改`HeaderFooter`对象并删除相应的内联段落。

#### 问：如何将内联段落应用到 PDF 文档的特定页面？

答：要将内联段落应用于特定页面，您可以创建单独的`HeaderFooter`每个页面的对象，并使用`Header`各自财产`Aspose.Pdf.Page`对象。