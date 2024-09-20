---
title: 插图结构元素
linktitle: 插图结构元素
second_title: Aspose.PDF for .NET API 参考
description: 按照我们的分步教程，在 Aspose.PDF for .NET 中创建带有插图元素的结构化 PDF。
type: docs
weight: 100
url: /zh/net/programming-with-tagged-pdf/illustration-structure-elements/
---
## 介绍

您准备好在 .NET 应用程序中创建令人惊叹的结构化 PDF 了吗？无论您是在处理需要标记内容的项目，还是只想将 PDF 提升到一个新的水平，Aspose.PDF for .NET 都拥有处理插图结构元素所需的所有工具。在本教程中，我将逐步指导您完成整个过程，确保即使是最复杂的部分也清晰明了。

## 先决条件

在我们深入讨论细节之前，让我们确保您已准备好顺利进行所需的一切。

1.  Aspose.PDF for .NET – 您需要安装 Aspose.PDF 库。还没有吗？您可以[点击下载](https://releases.aspose.com/pdf/net/)。如果你想先测试一下，你可以拿一个[免费试用](https://releases.aspose.com/).
2. Visual Studio – 我们将使用 C# 编码，因此请确保安装了 Visual Studio 或任何兼容的 IDE。
3. .NET Framework – 确保您拥有与 Aspose.PDF for .NET 兼容的版本。
4. 临时许可证 – Aspose.PDF 在试用模式下有一些限制，因此请获取[临时执照](https://purchase.aspose.com/temporary-license/)解锁全部功能。

就这样！现在让我们导入必要的命名空间并继续编码。

## 导入命名空间

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

这是基础 — 如果不导入这些命名空间，我们就无法与 Aspose.PDF 功能交互或处理带标签的 PDF 内容。现在让我们详细分解这些步骤。

## 步骤 1：设置文档目录

在开始创建 PDF 之前，您需要指定将保存文件的文档目录的路径。这是系统上存储图像或其他资产的文件夹。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

这一步很简单，但必不可少。你要告诉程序在哪里找到并存储你要处理的文件。这就像为你的 PDF 建立一个大本营。替换`"YOUR DOCUMENT DIRECTORY"`与您的机器上的实际路径。

## 步骤 2：创建新的 PDF 文档

现在，是时候创建 PDF 文档了。在此步骤中，我们将启动一个空的 PDF 文档，我们将在后续步骤中对其进行修改和增强。
 创建文档

```csharp
Document document = new Document();
```

这行代码可以发挥神奇的作用。它会创建一个完全空白的新 PDF 文件，等待您向其中添加内容。您可以将其视为打开了一块新画布。

## 步骤 3：访问带标签的 PDF 内容

要使用插图结构元素，我们需要利用文档的标记内容。这使我们能够定义特定标记，使 PDF 更加结构化且更易于访问。

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

这就是奇迹发生的地方！`TaggedContent`对象让我们定义如何解释 PDF 中的元素。如果您正在处理可访问性或结构，则此步骤至关重要。

## 步骤 4：设置文档的标题和语言

我们正在创建结构化的 PDF，因此定义标题和语言至关重要。这不仅有助于提高可访问性，还可以使文档更加专业且易于搜索。

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

通过指定标题和语言，您实际上是在赋予 PDF 一些个性。标题将显示在文档属性中，而设置语言可确保与屏幕阅读器和其他辅助工具兼容。

## 步骤5：创建插图（图形）元素

现在到了令人兴奋的部分 - 添加插图！在本例中，我们将创建一个包含图像、替代文本描述和标题的图形元素。

```csharp
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
```

此代码创建一个新的图形元素并将其附加到文档的根元素。可以将其视为向文档添加图像占位符。

## 步骤 6：添加替代文本、标题和图像

为了确保您的 PDF 可访问，您需要为插图添加替代文本和标题。我们还将附加一张图片。

```csharp
figure1.AlternativeText = "Figure One";
figure1.Title = "Image 1";
figure1.SetTag("Fig1");
figure1.SetImage(dataDir + "image.jpg");
```

这是最后的润色。我们为图像添加描述性替代文本（这对屏幕阅读器很有用）、标题，并设置实际图像文件。`SetTag`方法标记图形，使得以后更容易引用。

重要提示：确保图片路径`SetImage`指向您机器上的有效图像文件。

## 步骤 7：保存标记的 PDF 文档

添加并构建所有内容后，就可以保存 PDF 了。此步骤完成所有内容并生成实际文件。

```csharp
document.Save(dataDir + "IllustrationStructureElements.pdf");
```

很简单，对吧？此命令会获取您所做的所有工作，并在您之前指定的目录中创建一个新的 PDF 文件。现在，检查您的文件夹，瞧 — 您有一个包含插图元素的结构化 PDF！

## 结论

恭喜！您刚刚学会了如何使用 Aspose.PDF for .NET 创建带有插图结构元素的标记 PDF。这种方法可确保您的 PDF 不仅具有视觉吸引力，而且结构合理且易于访问。通过标记内容和添加替代文本，您可以确保每个人（包括使用辅助技术的人）都能享受您的文档。

## 常见问题解答

### 什么是标记的 PDF 内容？
带标记的 PDF 是包含标签或标记以识别不同元素（如标题、段落和图形）的 PDF，从而使文档更易于访问。

### 设置替代文本有何帮助？
替代文本为图像提供描述，可被屏幕阅读器读取，从而提高视障用户的可访问性。

### 我可以向标记的 PDF 添加多幅图像吗？
是的！您可以创建多个`FigureElement`对象并将每个对象附加到您的文档，就像我们对单个图像所做的那样。

### 我需要许可证才能使用 Aspose.PDF for .NET 吗？
是的，Aspose.PDF 是一个付费库，但你可以获得[临时执照](https://purchase.aspose.com/temporary-license/)或者从[免费试用](https://releases.aspose.com/).

### 创建 PDF 后可以修改图形元素吗？
一旦 PDF 被保存，您就不能直接修改它，但您可以重新打开文档，进行更改，然后使用 Aspose.PDF 再次保存它。