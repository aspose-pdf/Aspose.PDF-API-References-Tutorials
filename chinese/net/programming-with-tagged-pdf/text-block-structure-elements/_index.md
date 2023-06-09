---
title: 文本块结构元素
linktitle: 文本块结构元素
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 向现有 PDF 文档添加文本块结构元素，例如标题和标记段落。
type: docs
weight: 220
url: /zh/net/programming-with-tagged-pdf/text-block-structure-elements/
---

在这个详细的教程中，我们将逐步引导您通过提供的 C# 源代码，使用 Aspose.PDF for .NET 在带标签的 PDF 文档中创建文本块结构元素。按照以下说明了解如何将多级标题和标记段落添加到您的 PDF 文档。

## 第 1 步：设置环境

在开始之前，请确保您已将开发环境配置为使用 Aspose.PDF for .NET。这包括安装 Aspose.PDF 库和配置您的项目以引用它。

## 第 2 步：创建 PDF 文档

在这一步中，我们将使用 Aspose.PDF 创建一个新的 PDF 文档对象。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建 PDF 文档
Document document = new Document();
```

我们用 Aspose.PDF 创建了一个新的 PDF 文档。

## 第 3 步：获取标记内容并设置标题和语言

现在让我们获取 PDF 文档的标记内容并设置文档标题和语言。

```csharp
//获取标记内容
ITaggedContent taggedContent = document.TaggedContent;

//定义文档标题和语言
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

我们已经设置了标记 PDF 文档的标题和语言。

## 第四步：获取根结构元素

现在让我们获取 PDF 文档的根结构元素。

```csharp
//获取根结构元素
StructureElement rootElement = taggedContent.RootElement;
```

我们已经获得了 PDF 文档的根结构元素。

## 第 5 步：添加标题和段落

现在我们将向我们的 PDF 文档添加不同级别的标题和标记的段落。

```csharp
//创建不同级别的标题
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);

//标题文本的定义
h1.SetText("H1. Level 1 header");
h2.SetText("H2. Level 2 header");
h3.SetText("H3. Level 3 header");
h4.SetText("H4. Level 4 header");
h5.SetText("H5. Heading level 5");
h6.SetText("H6. Level 6 header");

//将标题添加到根结构元素
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

//创建段落
ParagraphElement p = taggedContent.CreateParagraphElement();

//段落文本的定义
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet Nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");

//将段落添加到根结构元素
rootElement.AppendChild(p);
```

我们在 PDF 文档的根结构元素中添加了不同级别的标题和带标签的段落。

## 步骤 6：保存 PDF 文档

现在我们已经完成了 PDF 文档的编辑，让我们将它保存到一个文件中。

```csharp
//保存标记的 PDF 文档
document.Save(dataDir + "ElementsDeStructureDeBlocsDeTexte.pdf");
```

我们将带有文本块结构元素的标记 PDF 文档保存在指定目录中。

### 使用 Aspose.PDF for .NET 的文本块结构元素示例源代码 
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

//获取根结构元素
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
h1.SetText("H1. Header of Level 1");
h2.SetText("H2. Header of Level 2");
h3.SetText("H3. Header of Level 3");
h4.SetText("H4. Header of Level 4");
h5.SetText("H5. Header of Level 5");
h6.SetText("H6. Header of Level 6");
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
rootElement.AppendChild(p);

//保存标记的 Pdf 文档
document.Save(dataDir + "TextBlockStructureElements.pdf");
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 向 PDF 文档添加文本块结构元素，例如标题和标记段落。您现在可以使用这些功能来改善 PDF 文档的结构和可访问性。
