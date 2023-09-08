---
title: 将结构元素添加到元素中
linktitle: 将结构元素添加到元素中
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将结构元素添加到 PDF 文档中的元素的分步指南。
type: docs
weight: 20
url: /zh/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
在本教程中，我们将为您提供有关如何使用 Aspose.PDF for .NET 将结构元素添加到 PDF 文档中的元素的分步指南。 Aspose.PDF 是一个功能强大的库，允许您以编程方式创建、操作和转换 PDF 文档。使用Aspose.PDF的标记内容结构功能，您可以在PDF文档中创建层次结构。

## 先决条件

在开始之前，请确保您具备以下先决条件：

1. 随 .NET Framework 安装的 Visual Studio。
2. 适用于 .NET 的 Aspose.PDF 库。

## 第 1 步：项目设置

首先，在 Visual Studio 中创建一个新项目并添加对 Aspose.PDF for .NET 库的引用。您可以从Aspose官方网站下载该库并将其安装到您的计算机上。

## 第 2 步：导入必要的命名空间

在您的 C# 代码文件中，导入访问 Aspose.PDF 提供的类和方法所需的命名空间：

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 步骤 3：创建 PDF 文档并定义结构化元素

使用以下代码创建 PDF 文档并定义结构化元素：

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

此代码创建一个空的 PDF 文档并添加结构化元素，例如段落和跨度。每个结构元素都是使用 Aspose.PDF 提供的方法创建的。

## 步骤 4：保存 PDF 文档

使用以下代码保存PDF文档：

```csharp
document. Save(outFile);
```

此代码将带有结构化元素的 PDF 文档保存到指定文件中。

### 使用 Aspose.PDF for .NET 将结构元素添加到元素中的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
//创建文档并获取标记的 Pdf 内容
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
//设置文档的标题和自然语言
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
//获取根结构元素（文档结构元素）
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
//保存标记的 PDF 文档
document.Save(outFile);
//检查 PDF/UA 合规性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 结论

在本教程中，您学习了如何使用 Aspose.PDF for .NET 将结构元素添加到 PDF 文档中的元素。使用Aspose.PDF的标记内容结构功能，您可以在PDF文档中创建层次结构，这使得管理和浏览内容变得更加容易。

### 常见问题解答

#### 问：使用 Aspose.PDF for .NET 将结构元素添加到 PDF 文档中的元素的目的是什么？

答：使用 Aspose.PDF for .NET 将结构元素添加到 PDF 文档中的元素允许您在文档内容中创建层次结构。这种层次结构增强了内容的组织和导航，使管理和访问特定元素变得更加容易。

#### 问：Aspose.PDF 库如何协助向 PDF 文档添加结构元素？

答：Aspose.PDF for .NET 是一个功能强大的库，提供以编程方式创建、操作和转换 PDF 文档的功能。在本教程中，利用库的标记内容结构功能来创建结构元素并将其附加到 PDF 文档的内容。

#### 问：使用 Aspose.PDF for .NET 将结构元素添加到 PDF 文档的先决条件是什么？

答：开始之前，请确保您已安装了带有 .NET 框架的 Visual Studio，并在项目中引用了适用于 .NET 的 Aspose.PDF 库。

#### 问：提供的 C# 代码如何创建结构元素并将其附加到 PDF 文档的内容？

答：该代码演示了如何创建 PDF 文档、定义根结构元素以及向其附加各种结构化元素（例如段落和跨度）。每个结构化元素都是使用 Aspose.PDF 提供的方法创建的，允许您构建层次结构。

#### 问：我可以自定义附加到 PDF 文档的结构元素类型吗？

答：是的，您可以通过探索 Aspose.PDF 库提供的不同方法来自定义结构元素的类型。该代码展示了段落和跨度作为示例，但您可以根据需要创建和附加其他类型的结构化元素。

#### 问：如何定义添加的结构元素之间的层次关系？

答：结构元素之间的层次关系由将它们附加到其父元素的顺序定义。在代码中，父子关系是通过使用`AppendChild`方法。

#### 问：在 PDF 文档中创建层次结构有什么好处？

答：在 PDF 文档中创建层次结构可以增强其可访问性、导航和组织。它允许辅助技术更好地解释和传达文档的内容，使其对残疾人士来说更加用户友好。

#### 问：添加结构元素后如何验证 PDF/UA 合规性？

答：本教程中提供的代码演示了如何使用以下方法验证 PDF/UA 合规性：`Validate`方法。通过根据 PDF/UA 标准验证文档，您可以确保添加的结构元素符合辅助功能指南。

#### 问：我可以使用此方法向现有 PDF 文档添加结构元素吗？

答：是的，您可以修改提供的方法以将结构元素添加到现有 PDF 文档中。您可以使用 Aspose.PDF 加载现有文档，然后按照类似的步骤附加结构元素，而不是创建新文档。