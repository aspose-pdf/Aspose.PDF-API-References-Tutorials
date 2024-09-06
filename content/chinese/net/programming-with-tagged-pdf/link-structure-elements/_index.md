---
title: 链接结构元素
linktitle: 链接结构元素
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 链接结构元素的分步指南。在您的 PDF 文档中创建超链接。
type: docs
weight: 120
url: /zh/net/programming-with-tagged-pdf/link-structure-elements/
---
在本分步指南中，我们将向您展示如何使用 Aspose.PDF for .NET 中的链接结构元素。Aspose.PDF 是一个功能强大的库，可让您以编程方式创建和操作 PDF 文档。链接结构元素允许您向 PDF 文档添加超链接，让用户可以单击链接并导航到在线资源。

让我们深入研究代码并学习如何使用 Aspose.PDF for .NET 的链接结构元素。

## 先决条件

开始之前，请确保您已准备好以下物品：

1. 已安装用于.NET 的 Aspose.PDF 库。
2. C# 编程语言的基本知识。

## 步骤 1：设置环境

首先，打开 C# 开发环境并创建一个新项目。确保您已在项目中添加了对 .NET 的 Aspose.PDF 库的引用。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
```

## 第 2 步：创建文档

第一步是使用`Document`班级。

```csharp
//创建 PDF 文档
Document document = new Document();
```

## 步骤 3：处理标记内容

然后我们得到要处理的文档的标记内容。

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

## 步骤 5：添加链接结构元素

现在让我们将链接结构元素添加到文档中。我们将创建不同类型的链接，包括简单文本链接、图像链接和多行链接。
```csharp
//获取根结构元素（文档结构元素）
StructureElement rootElement = taggedContent.RootElement;

//添加带有超链接的段落
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com”);
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

//添加包含富文本的超链接段落
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com”);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

//添加包含部分格式化文本的超链接段落
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com”);
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
link4.Hyperlink = new WebHyperlink("http://google.com”);
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

//添加带有图像的超链接的段落
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com”);
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

最后，我们保存标记的PDF文档。

```csharp
//保存标记的 PDF 文档
document. Save(outFile);
```

## 步骤 7：检查 PDF/UA 合规性

我们还可以使用以下工具检查文档是否符合 PDF/UA 标准：`Validate`方法`Document`班级。

```csharp
//检查 PDF/UA 合规性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### 使用 Aspose.PDF for .NET 的链接结构元素示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

//创建文档并获取带标签的 PDF 内容
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
link1.Hyperlink = new WebHyperlink("http://google.com”);
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com”);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com”);
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
link4.Hyperlink = new WebHyperlink("http://google.com”);
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com”);
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

//保存带标签的 PDF 文档
document.Save(outFile);

//检查 PDF/UA 合规性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## 结论

恭喜！您已经学会了如何使用 Aspose.PDF for .NET 中的链接结构元素。现在您可以在 PDF 文档中创建超链接，让用户导航到在线资源。尝试并探索 Aspose.PDF 的更多功能，以创建交互式且丰富的 PDF 文档。

### 常见问题解答

#### 问：PDF 文档中的链接结构元素是什么，它们如何增强文档交互性？

答：PDF 文档中的链接结构元素用于创建超链接，使用户可以导航到在线资源或文档内的特定位置。这些元素通过提供可点击的链接来增强交互性，使用户能够访问相关内容或外部网站。

#### 问：链接结构元素在 PDF 文档中有何益处？

答：链接结构元素通过使 PDF 文档具有交互性来增强用户体验。它们提供对附加信息、相关内容、外部网站或文档内特定部分的快速访问，从而改善导航并促进信息检索。

#### 问：我可以使用 Aspose.PDF for .NET 中的链接结构元素创建不同类型的超链接吗？

答：是的，您可以使用链接结构元素创建各种类型的超链接。Aspose.PDF for .NET 允许您使用纯文本、富文本、图像和多行描述创建超链接，为您提供链接到外部内容或文档内位置的多功能性。

#### 问：如何使用 Aspose.PDF for .NET 设置和初始化 PDF 文档中的链接结构元素？

答：要使用链接结构元素，首先需要使用`Document`类。然后，使用`TaggedContent`文档的属性。从那里，您可以创建和自定义链接结构元素，并将它们添加到根结构元素。

#### 问：如何使用链接结构元素创建简单的文本超链接？
答：您可以通过创建`LinkElement`并设定其`Hyperlink`财产`WebHyperlink`替换为要链接到的 URL。您还可以使用`SetText`方法。

#### 问：是否可以使用链接结构元素创建带有图像的超链接？

答：是的，您可以使用链接结构元素创建带有图像的超链接。您可以创建一个`LinkElement`然后附加一个`FigureElement`并添加图片。这样您就可以创建基于图片的超链接。

#### 问：如何确保带有超链接的 PDF 文档符合 PDF/UA 可访问性标准？

答：Aspose.PDF for .NET 可以使用以下工具验证 PDF 文档是否符合 PDF/UA 标准：`Validate`方法`Document`类。这可确保残障用户可以访问文档的超链接。

#### 问：链接结构元素的替代描述是什么，为什么它们很重要？

答：链接结构元素的替代描述 (alt text) 提供超链接的文本描述。这些描述对于可访问性至关重要，可让有视觉障碍的用户了解链接的目的及其目的地。

#### 问：我可以自定义使用链接结构元素创建的超链接的外观和行为吗？

答：虽然链接结构元素主要侧重于创建超链接，但您可以使用 Aspose.PDF for .NET 提供的其他功能进一步自定义超链接的外观和行为。这包括指定颜色、样式和链接操作。

#### 问：链接结构元素如何使 PDF 文档更具交互性和用户友好性？

答：链接结构元素通过添加可点击的超链接将静态 PDF 文档转变为交互式体验。这种交互性提高了用户参与度，实现了相关内容之间的无缝导航，并增强了文档的整体可用性。