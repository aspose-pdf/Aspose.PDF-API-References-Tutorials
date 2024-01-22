---
title: 页眉页脚部分内嵌的图像和页码
linktitle: 页眉页脚部分内嵌的图像和页码
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 的内联段落在页眉和页脚中添加图像和页码。
type: docs
weight: 120
url: /zh/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉和页脚部分添加图像和页码。我们将使用提供的 C# 源代码创建页面、设置页眉和页脚、使用 PDF 文档页眉中的内联段落添加图像和文本。

## 第一步：搭建环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 下载用于 .NET 的 Aspose.PDF 库并在您的项目中引用。

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

上面的代码在 PDF 文档中创建一个新的 Document 对象和一个空页面。

## 步骤 3：添加带有图像和内嵌文本的标题

现在页面已创建，我们可以使用内联段落添加带有图像和文本的标题部分。就是这样：

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

//为图像创建一个 Image 对象
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//设置图片路径
image1.File = dataDir + "aspose-logo.jpg";

//定义图像的尺寸
image1.FixWidth = 50;
image1.FixHeight = 20;

//指示第一个内嵌文本是图像
image1.IsInLineParagraph = true;

//创建第二个内嵌文本
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

//将项目添加到标题
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

上面的代码创建一个标题部分，使用此部分设置页面标题，添加一个带有内联文本和内联图像对象的 TextFragment。

## 第四步：保存修改后的PDF文档

添加带有图像和内嵌文本的标题后，我们可以保存修改后的 PDF 文档。就是这样：

```csharp
//保存修改后的PDF文档
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

上述代码将编辑后的PDF文档保存到指定目录。

### 使用 Aspose.PDF for .NET 在页眉页脚部分内联中的图像和页码示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//通过调用其空构造函数来实例化 Document 对象
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

//在该部分中创建图像对象
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

//设置图片文件路径
image1.File = dataDir + "aspose-logo.jpg";

//设置图像宽度信息
image1.FixWidth = 50;
image1.FixHeight = 20;

//指示 seg1 的 InlineParagraph 是图像。
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

恭喜！您已经了解了如何使用 Aspose.PDF for .NET 的内联段落在 PDF 文档的页眉和页脚部分添加图像和页码。您现在可以灵活自定义 PDF 文档的页眉和页脚。

### 常见问题解答

#### 问：使用内联段落将图像和文本添加到 PDF 文档的页眉有什么好处？

答：使用内联段落可以让您将图像和文本无缝集成在同一段落中，从而精确控制它们的位置和格式。此方法对于创建具有视觉元素的自定义标题特别有用。

#### 问：提供的C#源代码如何实现PDF文档中标题的内联段落？

答：提供的代码演示了如何创建 PDF 文档、添加页面以及使用内联段落自定义页眉。它添加一个带有内联文本的 TextFragment、一个内联图像和另一个内联 TextFragment。

#### 问：如何指定页眉内嵌文本的颜色？

答：内联文本的颜色是使用`ForegroundColor`的财产`TextState`的`TextFragment`目的。

#### 问：我可以调整页眉内嵌图像的尺寸吗？

答：是的，您可以使用`FixWidth`和`FixHeight`的属性`Image`目的。这允许您控制标题内图像的宽度和高度。

#### 问：我可以在标题中包含其他内联元素，例如超链接或不同的字体样式吗？

答：是的，您可以通过创建更多内容在标题中包含其他内联元素`TextFragment`或者`Image`具有所需属性的对象。这允许您进一步自定义标题，包括超链接、不同的字体样式或其他视觉元素。

#### 问：如何确保内嵌图像和文本在不同设备和查看器中保持正确对齐和格式？

答：Aspose.PDF for .NET 可确保内联图像和文本正确对齐和格式化，从而在不同设备和 PDF 查看器中获得一致的外观。

#### 问：我可以将内联段落也应用到页脚部分吗？

答：是的，您可以通过创建一个`Footer`对象并向其添加内联元素（例如文本和图像）。

#### 问：是否可以将内联段落与其他页眉或页脚自定义方法结合起来？

答：是的，您可以将内联段落与 Aspose.PDF for .NET 提供的其他页眉或页脚自定义方法结合起来，以创建更复杂和定制的页眉或页脚设计。

#### 问：如果需要，我可以从标题中删除或清除内联元素吗？

 A：是的，可以通过修改内容来移除或清除内联元素`HeaderFooter`对象并删除相应的内联段落。

#### 问：如何将内嵌段落应用于 PDF 文档的特定页面？

答：要将内联段落应用于特定页面，您可以创建单独的段落`HeaderFooter`每个页面的对象并使用`Header`各自的财产`Aspose.Pdf.Page`对象。