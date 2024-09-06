---
title: 内联结构元素
linktitle: 内联结构元素
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在线结构元素的分步指南。使用标题和段落组织您的 PDF。
type: docs
weight: 110
url: /zh/net/programming-with-tagged-pdf/inline-structure-elements/
---
在本分步指南中，我们将向您展示如何使用 Aspose.PDF for .NET 中的内联结构元素。Aspose.PDF 是一个功能强大的库，可让您以编程方式操作 PDF 文档。内联结构元素允许您使用不同级别的标题和段落在 PDF 文档中创建层次结构。

让我们深入研究代码并学习如何使用 Aspose.PDF for .NET 的内联结构元素。

## 先决条件

开始之前，请确保您已准备好以下物品：

1. 已安装用于.NET 的 Aspose.PDF 库。
2. C# 编程语言的基本知识。

## 步骤 1：设置环境

首先，打开 C# 开发环境并创建一个新项目。确保您已在项目中添加了对 .NET 的 Aspose.PDF 库的引用。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
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
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## 步骤 5：在线添加结构元素

现在我们要向文档中添加不同级别的标题和段落等内联结构元素。

```csharp
//获取根结构元素
StructureElement rootElement = taggedContent.RootElement;

//添加不同级别的标题
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

//向每个标题添加内容
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

//添加段落
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

//向段落添加内容
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

在这里我们创建内联结构元素，例如不同级别的标题和段落，并向其中添加内容。

## 步骤 6：保存标记的 PDF 文档

最后，我们保存标记的PDF文档。

```csharp
//保存标记的 PDF 文档
document.Save(dataDir + "InlineStructureElements.pdf");
```

### 使用 Aspose.PDF for .NET 的内联结构元素示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//创建 PDF 文档
Document document = new Document();

//获取使用 TaggedPdf 工作的内容
ITaggedContent taggedContent = document.TaggedContent;

//设置 Documnet 的标题和语言
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

//获取根结构元素
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

//保存带标签的 PDF 文档
document.Save(dataDir + "InlineStructureElements.pdf");

```

## 结论

恭喜！您已经学会了如何使用 Aspose.PDF for .NET 中的内联结构元素。现在，您可以使用不同级别的标题和段落在 PDF 文档中创建层次结构。探索 Aspose.PDF 的更多功能，发掘其全部潜力。

### 常见问题解答

#### 问：PDF 文档中的内联结构元素是什么，它们如何有助于创建层次结构？

答：PDF 文档中的内联结构元素（例如不同级别的标题和段落）用于创建层次结构，以结构化的方式组织和呈现内容。这些元素可让您在文档中建立清晰的层次结构和信息流。

#### 问：内联结构元素如何增强 PDF 文档的可读性和组织性？

答：内联结构元素（尤其是标题和段落）通过提供逻辑结构，有助于提高 PDF 文档的可读性和组织性。标题表示不同级别的重要性并帮助读者浏览内容，而段落将相关信息组合在一起。

#### 问：Aspose.PDF for .NET 如何促进内联结构元素的使用？

答：Aspose.PDF for .NET 提供类和方法来创建和操作内联结构元素，例如标题和段落。这些元素可以自定义、分层组织并丰富内容，以改善文档的视觉呈现和可访问性。

#### 问：`taggedContent` object in relation to inline structure elements?

答：`taggedContent`对象，从`TaggedContent`的财产`Document`，允许您使用结构化元素，包括内联结构元素。它使您能够在文档中创建、自定义和组织标题和段落。

#### 问：内联结构元素如何帮助创建清晰的文档层次结构？

答：内联结构元素（例如不同级别的标题）有助于在文档中建立清晰且明确的层次结构。读者可以快速识别主要主题、子主题和相关内容，使文档更易于浏览和理解。

#### 问：我可以使用 Aspose.PDF for .NET 自定义内联结构元素的外观和格式吗？

答：是的，您可以自定义内联结构元素的外观和格式。您可以设置字体样式、大小、颜色、对齐方式、缩进和间距等属性，以实现标题和段落所需的视觉呈现效果。

#### 问：如何使用 Aspose.PDF for .NET 中的内联结构元素为 PDF 文档创建和添加不同级别的标题？

答：您可以使用`CreateHeaderElement`方法，然后将它们附加到根结构元素。随后，您可以使用`CreateSpanElement`创建文本跨度的方法。

#### 问：我可以使用内联结构元素在 PDF 文档中创建列表、项目符号或其他类型的内容组织吗？

答：虽然内联结构元素本身主要用于标题和段落，但您可以将它们与 Aspose.PDF for .NET 提供的其他功能结合使用，以创建列表、项目符号、表格和其他类型的内容组织，从而形成全面的文档结构。

#### 问：内联结构元素如何有助于文档可访问性？

答：内联结构元素在增强文档可访问性方面起着至关重要的作用。结构合理的标题和段落提供了清晰的文档层次结构，可帮助屏幕阅读器和其他辅助技术准确地解释和向残障用户传达内容。

#### 问：我可以探索内联结构元素的更多高级用途，例如创建交互元素或嵌入多媒体吗？

答：当然！虽然本教程重点介绍如何创建标题和段落，但 Aspose.PDF for .NET 提供了创建交互元素、嵌入多媒体、添加超链接等高级功能。查看库的文档和示例，深入了解这些高级功能。