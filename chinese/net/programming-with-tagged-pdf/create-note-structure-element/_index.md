---
title: 创建注释结构元素
linktitle: 创建注释结构元素
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 文档中创建结构化注释项目的分步指南。
type: docs
weight: 30
url: /zh/net/programming-with-tagged-pdf/create-note-structure-element/
---
在本教程中，我们将为您提供有关如何使用 Aspose.PDF for .NET 在 PDF 文档中创建注释结构元素的分步指南。 Aspose.PDF 是一个功能强大的库，允许您以编程方式创建、操作和转换 PDF 文档。使用Aspose.PDF的标记内容结构功能，您可以向PDF文档添加结构化注释。

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

## 步骤 3：创建 PDF 文档并注释结构化元素

使用以下代码创建 PDF 文档并添加注释结构化元素：

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

此代码创建一个空 PDF 文档并将结构化注释元素添加到段落中。每个注释都是使用 Aspose.PDF 提供的方法创建的。

## 步骤 4：保存 PDF 文档

使用以下代码保存PDF文档：

```csharp
document. Save(outFile);
```

此代码将带有注释结构化元素的 PDF 文档保存到指定文件中。

### 使用 Aspose.PDF for .NET 创建注释结构元素的示例源代码 

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
//如果 ClearId() 用于注释结构元素，则生成的文档不符合 PDF/UA
//note3.ClearId();
//保存标记的 PDF 文档
document.Save(outFile);
//检查 PDF/UA 合规性
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 结论

在本教程中，您学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中创建注释结构元素。结构化注释元素允许您向 PDF 文档添加附加的结构化信息。

### 常见问题解答

#### 问：使用 Aspose.PDF for .NET 在 PDF 文档中创建注释结构元素的目的是什么？

答：使用 Aspose.PDF for .NET 在 PDF 文档中创建注释结构元素允许您向文档内容添加结构化注释。这些注释可以提供额外的上下文、解释或对内容特定部分的引用。

#### 问：Aspose.PDF 库如何协助在 PDF 文档中创建注释结构元素？

答：Aspose.PDF for .NET 是一个功能强大的库，提供以编程方式创建、操作和转换 PDF 文档的功能。在本教程中，库的标记内容结构功能用于在 PDF 文档内容中创建结构化注释元素。

#### 问：使用 Aspose.PDF for .NET 在 PDF 文档中创建注释结构元素的先决条件是什么？

答：开始之前，请确保您已安装了带有 .NET 框架的 Visual Studio，并在项目中引用了适用于 .NET 的 Aspose.PDF 库。

#### 问：所提供的 C# 代码如何在 PDF 文档的内容中创建注释结构元素？

答：该代码演示了如何创建 PDF 文档、定义注释结构化元素并将它们添加到段落中。每个注释都是使用 Aspose.PDF 提供的方法创建的，允许您将结构化注释合并到内容中。

#### 问：我可以自定义我创建的笔记结构元素的内容和属性吗？

答：是的，您可以使用Aspose.PDF库提供的方法和属性来自定义注释结构元素的内容和属性。该代码展示了如何设置注释元素的文本和 ID，但您可以根据需要进一步自定义它们。

#### 问：笔记结构元素与文档内容之间的层次关系是如何建立的？

答：层次关系是通过添加注释结构元素作为其他结构元素（例如段落）的子元素来建立的。在代码中，使用以下方法将注释元素附加到段落元素`AppendChild`方法。

#### 问：我可以为注释结构元素分配唯一的 ID 吗？

答：是的，您可以使用以下命令为注释结构元素分配唯一的 ID：`SetId`方法。该代码演示了如何将注释元素的 ID 设置为唯一值。

#### 问：如果我尝试将重复的 ID 分配给注释结构元素，会发生什么情况？

答：尝试将重复的 ID 分配给注释结构元素将导致异常。本教程中提供的代码包含说明此场景的注释。

#### 问：创建笔记结构元素时如何确保 PDF/UA 合规性？

答：本教程中提供的代码演示了如何使用以下方法验证 PDF/UA 合规性：`Validate`方法。通过根据 PDF/UA 标准验证文档，您可以确保添加的注释结构元素符合辅助功能指南。

#### 问：我可以使用此方法向现有 PDF 文档添加注释结构元素吗？

答：是的，您可以修改提供的方法，将注释结构元素添加到现有 PDF 文档中。您可以使用 Aspose.PDF 加载现有文档，然后按照类似的步骤附加注释元素，而不是创建新文档。
