---
title: PDF 文件中的文本和图像作为段落
linktitle: PDF 文件中的文本和图像作为段落
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 创建包含文本和图像的 PDF。了解如何逐步添加文本和内联图像。
type: docs
weight: 530
url: /zh/net/programming-with-text/text-and-image-as-paragraph/
---
## 介绍

在当今的数字世界中，PDF 是一种通用文档格式，我们大多数人每天都会遇到。无论是报告、电子书还是商业发票，PDF 都可以轻松地在各个平台之间共享信息。但是，如果您想以编程方式自定义 PDF，该怎么办？这就是 Aspose.PDF for .NET 的作用所在。在本教程中，我们将指导您使用 Aspose.PDF for .NET 将文本和图像作为内联段落插入 PDF 文件中。

## 先决条件

在深入研究代码之前，让我们确保您拥有顺利完成所需的一切：

-  Aspose.PDF for .NET 库：您需要安装 Aspose.PDF for .NET。您可以下载它[这里](https://releases.aspose.com/pdf/net/).
- Visual Studio：任何支持.NET 的版本都可以正常工作。
- 对 C# 的基本了解：熟悉一些 C# 会很有帮助，但不用担心 - 我会指导您完成每个步骤！
- PDF 文档准备就绪：如果您想添加自定义图像，请准备好。

您还可以免费试用该库[这里](https://releases.aspose.com/)或者如果你正在从事大型项目，可以考虑购买它[这里](https://purchase.aspose.com/buy)。需要更多详细信息？查看文档[这里](https://reference.aspose.com/pdf/net/).

## 导入包

要开始使用 Aspose.PDF for .NET，您需要导入所需的命名空间。这些命名空间允许您的 C# 代码与 Aspose.PDF 功能进行交互。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

很简单，对吧？现在让我们进入最有趣的部分——创建您自己的 PDF 文件。

## 分步指南：创建包含文本和内嵌图像的 PDF

让我们将其分解为易于理解、易于遵循的步骤。想象一下您正在拼拼图；每个步骤都像是找到并放置正确的拼图块。

## 步骤 1：初始化 PDF 文档

第一步是使用 Aspose.PDF 初始化一个新的 PDF 文档。此文档将作为添加文本和图像的基础。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//实例化 Document 实例
Document doc = new Document();
```

这里发生了什么？我们只是使用`Document`类并定义要保存 PDF 的目录。这就像为您的杰作开辟一块新画布！

## 第 2 步：向 PDF 添加页面

没有页面的文档就没什么用，对吧？让我们在文档中添加一个空白页。

```csharp
//将页面添加到 Document 实例的页面集合中
Page page = doc.Pages.Add();
```

此代码片段将新页面添加到文档的页面集合中。可以将其想象为翻开笔记本中的空白页。

## 步骤 3：添加段落文本

接下来，我们将添加一个文本段落。您可以在此处插入消息或标题。

```csharp
//创建 TextFragment
TextFragment text = new TextFragment("Hello World.. ");
//将文本片段添加到 Page 对象的段落集合中
page.Paragraphs.Add(text);
```

在这里，我们创建一个`TextFragment`对象保存文本“Hello World..”，然后将其作为段落添加到页面中。这就像在 PDF 文档中写下第一句话一样。

## 步骤 4：添加图像作为内联段落

现在我们已经有了文本，让我们通过添加图像作为内联段落来增添趣味。内联段落只是意味着图像将出现在文本之后，就像 Word 文档中显示图像的方式一样。

```csharp
//创建图像实例
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
//将图像设置为内联段落，以便其紧接着出现
//上一段对象（TextFragment）
image.IsInLineParagraph = true;
//指定图像文件路径
image.File = dataDir + "aspose-logo.jpg";
```

在此代码片段中，我们创建一个`Image`对象，告诉它与文本对齐，并指定图像文件的路径。这相当于在文档中的句子后面粘贴图像。您可以将“aspose-logo.jpg”替换为所需的图像。

## 步骤 5：设置图像大小（可选）

想要调整图像大小？没问题。Aspose.PDF 为您提供了在将图像添加到文档之前调整其高度和宽度的选项。

```csharp
//设置图像高度（可选）
image.FixHeight = 30;
//设置图像宽度（可选）
image.FixWidth = 100;
```

这部分是可选的，但它可以帮助您控制 PDF 中图像的大小。这就像在打印照片之前调整照片大小一样。

## 步骤 6：将图像添加到段落集合

我们已经准备好了图像。现在让我们将其作为内联段落插入到文档中。

```csharp
//将图像添加到页面对象的段落集合中
page.Paragraphs.Add(image);
```

此行将图像添加到段落集合中的文本后面。这就像在文本编辑器中点击“插入图像”按钮一样。

## 步骤 7：添加另一个内联文本段落

如果您想在图片后立即添加更多文本怎么办？让我们通过插入另一个内联文本片段来实现。

```csharp
//使用不同的内容重新初始化 TextFragment 对象
text = new TextFragment(" Hello Again..");
//将 TextFragment 设置为内联段落
text.IsInLineParagraph = true;
//将新创建的 TextFragment 添加到页面的段落集合中
page.Paragraphs.Add(text);
```

我们正在重复使用`TextFragment`在此处添加新文本（“Hello Again..”）并将其插入到内联中，紧接着图像。这会让您的 PDF 看起来流畅、连贯。

## 步骤 8：保存 PDF 文档

我们快完成了！现在，让我们将文档保存到您指定的目录中。

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as inline paragraphs.\nFile saved at " + dataDir);
```

最后一步将文件保存在您的目录中，名称为“TextAndImageAsParagraph_out.pdf”。恭喜您 - 您已创建包含文本和内联图像的 PDF！

## 结论

就这样，使用 Aspose.PDF for .NET 创建包含文本和图像作为内联段落的 PDF 非常简单，只需按照以下步骤操作即可。只需几行代码，您就可以将动态内容添加到 PDF 文件中，使其更具视觉吸引力和专业性。无论是商业报告还是电子书，控制 PDF 的布局都会带来很大的不同。

## 常见问题解答

### 我可以添加多张图片作为内联段落吗？  
是的，您可以通过创建单独的`Image`对象并将它们添加到段落集合中。

### 我可以控制 PDF 中文本和图像的位置吗？  
是的，使用边距等属性，您可以控制文本和图像的精确位置。

### Aspose.PDF for .NET 免费吗？  
不，这是授权产品，但你可以得到一个[免费试用](https://releases.aspose.com/)或购买许可证[这里](https://purchase.aspose.com/buy).

### 我可以在文本中添加超链接吗？  
是的，Aspose.PDF 允许您在文本片段中添加超链接。检查[文档](https://reference.aspose.com/pdf/net/)了解更多详情。

### 我可以自定义文本的字体和样式吗？  
当然！您可以轻松自定义文本片段的字体、颜色和其他样式属性。