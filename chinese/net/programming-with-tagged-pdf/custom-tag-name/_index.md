---
title: 自定义标签名称
linktitle: 自定义标签名称
second_title: Aspose.PDF for .NET API 参考
description: 在 Aspose.PDF for .NET 中使用自定义标签名称的分步指南。使用自定义标签改进 PDF 的结构。
type: docs
weight: 90
url: /zh/net/programming-with-tagged-pdf/custom-tag-name/
---
在这个循序渐进的指南中，我们将带您了解如何在 Aspose.PDF for .NET 中使用自定义标签名称。 Aspose.PDF 是一个功能强大的库，可让您以编程方式操作 PDF 文档。使用自定义标签允许您将特定的结构信息添加到 PDF 文档中，使其更易于使用和访问。

让我们深入研究代码并了解如何将自定义标签名称与 Aspose.PDF for .NET 一起使用。

## 先决条件

在开始之前，请确保您具备以下条件：

1. 安装了 .NET 的 Aspose.PDF 库。
2. C# 编程语言的基本知识。

## 第 1 步：设置环境

首先，打开您的 C# 开发环境并创建一个新项目。确保您已在项目中添加对 .NET 的 Aspose.PDF 库的引用。

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

## 第 3 步：处理标记的内容

然后我们获取要使用的文档的标记内容。

```csharp
//获取文档的标记内容
ITaggedContent taggedContent = document.TaggedContent;
```

## 第四步：设置文档标题和语言

我们现在可以设置文档标题和语言。

```csharp
//定义文档标题和语言
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## 第 5 步：创建逻辑结构元素

现在让我们创建一些逻辑结构元素来组织我们的内容。

```csharp
//创建逻辑结构元素
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1.");
p2.SetText("P2.");
p3.SetText("P3.");
p4.SetText("P4.");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);
```

在这里，我们为我们的内容创建段落元素和跨度元素，并为它们分配自定义标签。

## 第 6 步：保存标记的 PDF 文档

最后，我们保存标记的 PDF 文档。

```csharp
//保存标记的 PDF 文档
document.Save(dataDir + "CustomTag.pdf");
```

### 使用 Aspose.PDF for .NET 的自定义标签名称示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//创建 PDF 文档
Document document = new Document();

//使用 TaggedPdf 获取内容
ITaggedContent taggedContent = document.TaggedContent;

//为 Documnet 设置标题和语言
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

//创建逻辑结构元素
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1. ");
p2.SetText("P2. ");
p3.SetText("P3. ");
p4.SetText("P4. ");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);

//保存标记的 Pdf 文档
document.Save(dataDir + "CustomTag.pdf");

```

## 结论

恭喜！您已经学习了如何在 Aspose.PDF for .NET 中使用自定义标签名称。您现在可以使用自定义标签将特定的结构信息添加到您的 PDF 文档中。探索 Aspose.PDF 的更多功能以发现其全部潜力。
