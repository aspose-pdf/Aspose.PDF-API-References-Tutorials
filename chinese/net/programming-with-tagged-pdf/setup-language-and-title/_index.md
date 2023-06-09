---
title: 设置语言和标题
linktitle: 设置语言和标题
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 配置 PDF 文档的语言和标题的分步指南。创建个性化的多语言文档。
type: docs
weight: 140
url: /zh/net/programming-with-tagged-pdf/setup-language-and-title/
---
在本指南中，我们将告诉您如何使用 .NET 的 Aspose.PDF 库配置 PDF 文档的语言和标题。 Aspose.PDF 是一个功能强大的库，可让您以编程方式创建、操作和转换 PDF 文件。

让我们深入研究代码，了解如何使用 Aspose.PDF for .NET 配置 PDF 文档的语言和标题。

## 先决条件

在开始之前，请确保您已经安装了 Aspose.PDF for .NET 并设置了您的开发环境。

## 第 1 步：创建文档

第一步是使用`Document`班级。

```csharp
//创建 PDF 文档
Document document = new Document();
```

## 第 2 步：访问标记的内容

接下来，我们使用`ITaggedContent`目的。

```csharp
//访问标记内容
Tagged.ITaggedContent taggedContent = document.TaggedContent;
```

## 第三步：设置标题和语言

现在我们可以使用`SetTitle`和`SetLanguage`的方法`ITaggedContent`目的。

```csharp
//定义文档的标题
taggedContent.SetTitle("Example of tagged document");

//设置文档语言
taggedContent.SetLanguage("fr-FR");
```

## 第 4 步：添加多语言内容

接下来，我们使用每种语言的段落元素向文档添加多语言内容。

```csharp
//加一段英文
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

//用德语添加一段
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hello Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

//添加法语段落
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Hello world!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

//添加一段西班牙语
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);
```

## 第 5 步：保存标记的 PDF 文档

最后，我们保存标记的 PDF 文档。

```csharp
//保存标记的 PDF 文档
document.Save(dataDir + "SetupLanguageAndTitle.pdf");
```

### 使用 Aspose.PDF for .NET 设置语言和标题的示例源代码 
```csharp

Document document = new Document();

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//获取标记内容
Tagged.ITaggedContent taggedContent = document.TaggedContent;

//设置标题和语言
taggedContent.SetTitle("Example Tagged Document");
taggedContent.SetLanguage("en-US");

//标头（en-US，继承自文档）
LogicalStructure.HeaderElement h1 = taggedContent.CreateHeaderElement(1);
h1.SetText("Phrase on different languages");
taggedContent.RootElement.AppendChild(h1);

//段落（英文）
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

//段落（德语）
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hallo Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

//段落（法文）
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Bonjour le monde!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

//段落（西班牙语）
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);

//保存标记的 Pdf 文档
document.Save(dataDir + "SetupLanguageAndTitle.pdf");

```

## 结论

恭喜！您现在知道如何使用 Aspose.PDF for .NET 配置 PDF 文档的语言和标题了。您可以进一步探索 Aspose.PDF 的功能来创建个性化和多语言的 PDF 文档。
