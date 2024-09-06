---
title: 创建带标记图像的 PDF
linktitle: 创建带标记图像的 PDF
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 创建带有标记图像的 PDF 的分步指南。
type: docs
weight: 40
url: /zh/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
在本教程中，我们将为您提供分步指南，指导您如何使用 Aspose.PDF for .NET 创建带有标记图像的 PDF 文档。Aspose.PDF 是一个功能强大的库，允许您以编程方式创建、操作和转换 PDF 文档。使用 Aspose.PDF 的标记内容结构功能，您可以将标记图像添加到 PDF 文档中。

## 先决条件

开始之前，请确保您已满足以下先决条件：

1. 安装了 .NET 框架的 Visual Studio。
2. 适用于 .NET 的 Aspose.PDF 库。

## 步骤 1：项目设置

首先，在 Visual Studio 中创建一个新项目并添加对 Aspose.PDF for .NET 库的引用。您可以从 Aspose 官方网站下载该库并将其安装在您的机器上。

## 第 2 步：导入必要的命名空间

在您的 C# 代码文件中，导入访问 Aspose.PDF 提供的类和方法所需的命名空间：

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 步骤 3：创建带有标记图像的 PDF 文档

使用以下代码创建带有标记图像的 PDF 文档：

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

此代码创建一个空的 PDF 文档，并使用 Aspose.PDF 提供的方法添加带标签的图像。该图像指定了替代文本、标题和标签。

## 步骤 4：保存 PDF 文档

使用以下代码保存PDF文档：

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

此代码将带有标记图像的 PDF 文档保存到指定的文件。

### 使用 Aspose.PDF for .NET 创建带标记图像的 PDF 的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
//添加分辨率为 300 DPI 的图像（默认）
figure1.SetImage(dataDir + @"aspose-logo.jpg");
//保存 PDF 文档
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## 结论

在本教程中，您学习了如何使用 Aspose.PDF for .NET 创建带有标记图像的 PDF 文档。标记图像会向您的 PDF 文档添加额外的结构化信息。

### 常见问题解答

#### 问：使用 Aspose.PDF for .NET 创建带有标记图像的 PDF 文档的目的是什么？

答：使用 Aspose.PDF for .NET 创建带有标记图像的 PDF 文档，您可以将标记图像添加到文档内容中。标记图像提供结构化信息，例如替代文本和标题，从而增强可访问性和组织性。

#### 问：Aspose.PDF 库如何帮助创建带有标记图像的 PDF 文档？

答：Aspose.PDF for .NET 是一个强大的库，它提供了以编程方式创建、操作和转换 PDF 文档的功能。在本教程中，该库的标记内容结构功能用于将标记图像添加到 PDF 文档。

#### 问：使用 Aspose.PDF for .NET 创建带有标记图像的 PDF 文档的先决条件是什么？

答：在开始之前，请确保您已安装了带有 .NET 框架的 Visual Studio，并且在项目中引用了 .NET 的 Aspose.PDF 库。

#### 问：提供的 C# 代码如何创建带有标记图像的 PDF 文档？

答：代码演示了如何创建 PDF 文档、定义标记图像元素并将其添加到文档内容中。标记图像包括替代文本、标题和使用 Aspose.PDF 提供的方法的标记。

#### 问：我可以对标记图像使用不同的图像格式吗？

答：是的，您可以对标记图像使用不同的图像格式，例如 JPEG、PNG、GIF 等。教程中提供的代码示例使用了 JPEG 图像，但您可以将其替换为您喜欢的格式的图像文件的路径。

#### 问：标记图像中的替代文本（alt text）如何使用？

答：替代文本提供了图像的文字描述，屏幕阅读器会为视障用户朗读该描述。在提供的代码中，替代文本是使用`AlternativeText`的财产`IllustrationElement`代表标记的图像。

#### 问：`SetTitle` method contribute to the PDF document's tagged image?

答：`SetTitle`方法设置 PDF 文档标记内容的标题，为标记图像提供附加上下文。此标题可帮助识别标记内容的用途或主题。

#### 问：我可以自定义标记图片的标签和标题吗？

答：是的，您可以使用`SetTag`和`Title`方法`IllustrationElement`。代码示例演示了如何将标签设置为“Fig”，将标题设置为“Picture 1”。

#### 问：如何确保标记的图像可访问且符合可访问性标准？

答：通过使用 Aspose.PDF 的标记内容结构功能并提供替代文本和其他相关信息，您可以为标记图像的可访问性做出贡献。确保符合可访问性标准涉及遵循替代文本和文档结构的最佳实践。

#### 问：是否可以使用类似的技术将多个标记图像添加到同一个 PDF 文档？

答：是的，您可以使用类似的技术将多个标记图像添加到同一个 PDF 文档中。您可以创建额外的`IllustrationElement`每个标记图像的实例并根据需要自定义其属性。