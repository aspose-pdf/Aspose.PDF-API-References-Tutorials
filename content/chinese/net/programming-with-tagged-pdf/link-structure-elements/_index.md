---
title: 链接结构元素
linktitle: 链接结构元素
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 中创建链接结构元素。添加可访问链接、图像和合规性验证的分步指南。
type: docs
weight: 120
url: /zh/net/programming-with-tagged-pdf/link-structure-elements/
---
## 介绍

对于需要可访问性和流畅导航的文档来说，在 PDF 中创建和管理链接结构元素至关重要。在本教程中，我们将引导您了解如何使用 Aspose.PDF for .NET 执行此操作。如果您是 Aspose.PDF 或 PDF 操作的新手，请不要担心。我将详细解释每个步骤，以便您轻松跟上！

## 先决条件  

在开始编码之前，我们先解决一些问题。这些是确保顺畅的开发体验的基本要求。

1.  Aspose.PDF for .NET：您可以下载最新版本[这里](https://releases.aspose.com/pdf/net/).
2. .NET 开发环境：无论是 Visual Studio 还是任何与 .NET 兼容的 IDE，都请安装并准备好。
3.  Aspose 许可证：您可以使用 Aspose.PDF 的免费试用版[这里](https://releases.aspose.com/)或获取[临时执照](https://purchase.aspose.com/temporary-license/).
4. C# 基础知识：我们将使用一些 C# 代码，因此了解基础知识将使事情变得容易得多。

## 导入包

在编写链接结构元素的代码之前，您需要导入一些包。首先在项目中引用必要的 Aspose.PDF 库：

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

这些导入使我们能够处理 PDF 文档、添加标签和管理结构元素。

我们现在将创建具有不同类型链接结构的 PDF 文档，并将分解每个步骤以帮助您彻底了解该过程。

## 步骤 1：初始化文档  

让我们首先创建一个新的 PDF 文档并设置标记内容以供辅助功能使用。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

//创建新的 PDF 文档
Document document = new Document(); 

//检索 TaggedContent 接口
ITaggedContent taggedContent = document.TaggedContent;
```
  
在这里，我们正在初始化`Document`对象，它代表我们的 PDF 文件。我们还检索`TaggedContent`界面，允许我们添加段落、链接和图像等结构元素。

## 第 2 步：设置标题和语言  

每个 PDF 都应该有一个标题和语言设置，特别是当您希望符合 PDF/UA 标准时。

```csharp
//设置文档标题和语言
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");
```
  
此步骤可确保您的 PDF 具有有意义的标题，并将语言设置为英语（`en-US`）。这对于可访问性至关重要，可确保屏幕阅读器或其他辅助技术可以正确解释您的文档。

## 步骤 3：创建并附加段落  

在此步骤中，我们将添加段落来保存链接元素。

```csharp
//创建根元素
StructureElement rootElement = taggedContent.RootElement;

//创建一个段落并将其添加到根元素
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```
  
我们创建一个根结构元素，它本质上是所有其他元素的顶级容器。然后我们创建一个段落（`p1`) 并将其附加到根元素。

## 步骤 4：添加简单链接  

现在让我们添加一个指向 Google 的基本超链接。

```csharp
//创建链接元素并将其添加到段落
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);

//设置链接的超链接和文本
link1.Hyperlink = new WebHyperlink("http://google.com”);
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
```
  
在此步骤中，我们创建了一个链接元素，将其超链接设置为“http://google.com”，并为该链接提供了文本（“Google”）。我们还添加了备用描述以确保可访问性。

## 步骤 5：添加带有 Spans 的链接  

我们还可以创建具有不同文本跨度的链接。

```csharp
//创建另一个段落
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);

//使用 span 元素创建链接
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com”);

SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);

link2.AlternateDescriptions = "Link to Google";
```
  
在这里，我们使用 span 元素将部分文本括在链接内，从而允许我们自定义链接某些部分的显示方式。

## 步骤 6：多行链接  

如果您的链接文本太长怎么办？不用担心，您可以将其分成多行。

```csharp
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);

LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com”);
link4.SetText("The multiline link: Google Google Google Google Google...");
link4.AlternateDescriptions = "Link to Google (multiline)";
```
  
在这种情况下，我们只需设置一个长文本值即可创建多行链接，并且文本将自动换行到多行。

## 步骤 7：向链接添加图像  

最后，您还可以在链接内添加图像。

```csharp
//创建新的段落和链接元素
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);

LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com”);

//向链接添加图片
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
link5.AppendChild(figure5);

link5.AlternateDescriptions = "Link to Google";
```
  
此步骤演示了如何使用图片增强链接。在本例中，我们在链接内添加了一个 Google 图标。我们还通过为图片设置替代文本来确保可访问性。

## 步骤 8：验证 PDF 是否合规  

如果您希望符合 PDF/UA 标准（可访问性标准），那么验证您的文档是一种很好的做法。

```csharp
//保存 PDF 文档
document.Save(outFile);

//验证文档是否符合 PDF/UA 要求
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```
  
我们保存了该文档并根据 PDF/UA 标准对其进行了验证，以确保 PDF 符合可访问性要求。

## 结论  

在本教程中，我们介绍了如何使用 Aspose.PDF for .NET 创建结构化 PDF 文档。从添加基本超链接到更复杂的结构（如跨度、多行链接甚至图像），本指南为操作 PDF 中的链接元素提供了坚实的基础。借助 PDF/UA 合规性的额外优势，您现在可以制作可访问且可导航的 PDF。

## 常见问题解答

### 我可以添加更复杂的结构，比如链接内的表格吗？  
不，链接主要用于文本和图像，但您可以在附近嵌入复杂元素。

### PDF/UA 验证是强制性的吗？  
并非总是如此，但如果您担心可访问性，则强烈建议您这样做。

### 如果图像文件路径不正确会发生什么情况？  
该文档将不会显示图像，并且可能会在渲染过程中引发错误。

### 我可以设置链接内文本的样式吗？  
是的，您可以使用 span 元素应用文本样式。

### 是否可以创建内部文档链接？  
当然可以！您可以链接到同一文档中的特定部分。