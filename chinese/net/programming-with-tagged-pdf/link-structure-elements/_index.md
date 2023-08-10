---
title: 链接结构元素
linktitle: 链接结构元素
second_title: Aspose.PDF for .NET API 参考
description: 将链接结构元素与 Aspose.PDF for .NET 结合使用的分步指南。在 PDF 文档中创建超链接。
type: docs
weight: 120
url: /zh/net/programming-with-tagged-pdf/link-structure-elements/
---
在本分步指南中，我们将向您展示如何将链接结构元素与 Aspose.PDF for .NET 结合使用。 Aspose.PDF 是一个功能强大的库，可让您以编程方式创建和操作 PDF 文档。链接结构元素允许您向 PDF 文档添加超链接，从而允许用户单击链接并导航到在线资源。

让我们深入研究代码并了解如何在 Aspose.PDF for .NET 中使用链接结构元素。

## 先决条件

在开始之前，请确保您具备以下条件：

1. 安装了适用于.NET 的 Aspose.PDF 库。
2. C# 编程语言的基础知识。

## 第一步：搭建环境

首先，打开 C# 开发环境并创建一个新项目。确保您已在项目中添加对 .NET 的 Aspose.PDF 库的引用。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## 第 2 步：创建文档

第一步是使用以下命令创建一个新的 PDF 文档`Document`班级。

```csharp
//创建 PDF 文档
Document document = new Document();
```

## 第 3 步：处理标记内容

然后我们获取要使用的文档的标记内容。

```csharp
//获取文档的标记内容
ITaggedContent taggedContent = document.TaggedContent;
```

## 步骤 4：设置文档标题和语言

我们现在可以设置文档标题和语言。

```csharp
//定义文档标题和语言
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## 第5步：添加链接结构元素

现在让我们将链接结构元素添加到我们的文档中。我们将创建不同类型的链接，包括简单的文本链接、图像链接和多行链接。
```csharp
//获取根结构元素（文档结构元素）
StructureElement rootElement = taggedContent.RootElement;

//添加带有超链接的段落
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://谷歌.com”）；
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

//添加带有包含富文本的超链接的段落
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://谷歌.com”）；
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

//添加带有包含部分格式化文本的超链接的段落
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://谷歌.com”）；
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

//添加带有多行超链接的段落
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://谷歌.com”）；
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

//添加带有包含图像的超链接的段落
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://谷歌.com”）；
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## 步骤 6：保存标记的 PDF 文档

最后，我们保存标记的 PDF 文档。

```csharp
//保存标记的 PDF 文档
document. Save(outFile);
```

## 第 7 步：检查 PDF/UA 合规性

我们还可以使用以下命令检查文档的 PDF/UA 合规性`Validate`的方法`Document`班级。

```csharp
//检查 PDF/UA 合规性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### 使用 Aspose.PDF for .NET 的链接结构元素的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

//创建文档并获取标记的 Pdf 内容
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

//设置文档的标题和自然语言
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

//获取根结构元素（文档结构元素）
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://谷歌.com”）；
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://谷歌.com”）；
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://谷歌.com”）；
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://谷歌.com”）；
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://谷歌.com”）；
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

//保存标记的 PDF 文档
document.Save(outFile);

//检查 PDF/UA 合规性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## 结论

恭喜！您已经学习了如何通过 Aspose.PDF for .NET 使用链接结构元素。现在，您可以在 PDF 文档中创建超链接，允许用户导航到在线资源。实验并探索 Aspose.PDF 的更多功能，以创建交互式且丰富的 PDF 文档。

### 常见问题解答

#### 问：PDF 文档中的链接结构元素是什么？它们如何增强文档交互性？

答：PDF 文档中的链接结构元素用于创建超链接，允许用户导航到在线资源或文档中的特定位置。这些元素通过提供可点击的链接来增强交互性，使用户能够访问相关内容或外部网站。

#### 问：链接结构元素在 PDF 文档中有何用处？

答：链接结构元素通过使 PDF 文档具有交互性来增强用户体验。它们提供对附加信息、相关内容、外部网站或文档中特定部分的快速访问，从而改进导航并促进信息检索。

#### 问：我可以使用 Aspose.PDF for .NET 中的链接结构元素创建不同类型的超链接吗？

答：是的，您可以使用链接结构元素创建各种类型的超链接。 Aspose.PDF for .NET 允许您创建纯文本、富文本、图像和多行描述的超链接，为您链接到文档中的外部内容或位置提供了多功能性。

#### 问：如何使用 Aspose.PDF for .NET 在 PDF 文档中设置和初始化链接结构元素？

答：要使用链接结构元素，您首先需要使用以下命令创建一个新的 PDF 文档：`Document`班级。然后，使用以下方法获取标记的内容`TaggedContent`文档的属性。从那里，您可以创建和自定义链接结构元素并将它们添加到根结构元素。

#### 问：如何使用链接结构元素创建简单的文本超链接？
答：您可以通过创建一个简单的文本超链接`LinkElement`并设置其`Hyperlink`财产给一个`WebHyperlink`以及您想要链接到的 URL。您还可以使用以下命令设置链接的显示文本`SetText`方法。

#### 问：是否可以使用链接结构元素创建带有图像的超链接？

答：是的，您可以使用链接结构元素创建带有图像的超链接。你会创建一个`LinkElement`然后附加一个`FigureElement`并带有图像。这允许您创建基于图像的超链接。

#### 问：如何确保带有超链接的 PDF 文档符合 PDF/UA 标准的可访问性？

答：Aspose.PDF for .NET 能够使用以下方法验证您的 PDF 文档是否符合 PDF/UA 标准：`Validate`的方法`Document`班级。这可确保残障用户可以访问文档的超链接。

#### 问：链接结构元素的替代描述是什么，为什么它们很重要？

答：链接结构元素的替代描述（替代文本）提供超链接的文本描述。这些描述对于可访问性至关重要，可以让有视觉障碍的用户了解链接的用途及其目的地。

#### 问：我可以自定义使用链接结构元素创建的超链接的外观和行为吗？

答：虽然链接结构元素主要专注于创建超链接，但您可以使用 Aspose.PDF for .NET 提供的其他功能进一步自定义超链接的外观和行为。这包括指定颜色、样式和链接操作。

#### 问：链接结构元素如何有助于使 PDF 文档更具交互性和用户友好性？

答：链接结构元素通过添加可点击的超链接将静态 PDF 文档转换为交互式体验。这种交互性提高了用户参与度，实现了相关内容之间的无缝导航，并增强了文档的整体可用性。