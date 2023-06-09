---
title: 创建注释结构元素
linktitle: 创建注释结构元素
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 文档中创建结构化注释项的分步指南。
type: docs
weight: 30
url: /zh/net/programming-with-tagged-pdf/create-note-structure-element/
---
在本教程中，我们将为您提供有关如何使用 Aspose.PDF for .NET 在 PDF 文档中创建注释结构元素的分步指南。 Aspose.PDF 是一个功能强大的库，允许您以编程方式创建、操作和转换 PDF 文档。使用 Aspose.PDF 的标记内容结构功能，您可以将结构化注释添加到您的 PDF 文档中。

## 先决条件

在开始之前，请确保您具备以下先决条件：

1. Visual Studio 安装了 .NET 框架。
2. .NET 的 Aspose.PDF 库。

## 第 1 步：项目设置

首先，在 Visual Studio 中创建一个新项目并添加对 Aspose.PDF for .NET 库的引用。您可以从 Aspose 官方网站下载该库并将其安装在您的机器上。

## 第 2 步：导入必要的命名空间

在您的 C# 代码文件中，导入访问 Aspose.PDF 提供的类和方法所需的命名空间：

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 第 3 步：创建 PDF 文档和注释结构化元素

使用以下代码创建PDF文档并添加note结构化元素：

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

此代码创建一个空的 PDF 文档并将结构化注释元素添加到段落中。每个注释都是使用 Aspose.PDF 提供的方法创建的。

## 第 4 步：保存 PDF 文档

使用以下代码保存 PDF 文档：

```csharp
document. Save(outFile);
```

此代码将带有 note 结构化元素的 PDF 文档保存到指定的文件中。

### 使用 Aspose.PDF for .NET 创建笔记结构元素的示例源代码 

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
//创建 PDF 文档
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
//添加段落元素
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
//添加注释元素
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
//添加注释元素
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
//添加注释元素
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
//必须抛出异常 - Aspose.Pdf.Tagged.TaggedException：ID='note_002' 的结构元素已存在
//note3.SetId("note_002");
//如果 ClearId() 用于注释结构元素，生成的文档不符合 PDF/UA
//注意3.ClearId();
//保存标记的 Pdf 文档
document.Save(outFile);
//检查 PDF/UA 合规性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 结论

在本教程中，您学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中创建注释结构元素。结构化注释元素允许您向 PDF 文档添加额外的结构化信息。
