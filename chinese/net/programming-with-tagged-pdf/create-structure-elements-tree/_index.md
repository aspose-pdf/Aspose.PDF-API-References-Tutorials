---
title: 创建结构元素树
linktitle: 创建结构元素树
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 创建树元素结构。创建结构化 PDF 文档的分步指南。
type: docs
weight: 70
url: /zh/net/programming-with-tagged-pdf/create-structure-elements-tree/
---
在本分步指南中，我们将解释 C# 中的源代码，以使用 Aspose.PDF for .NET 创建树元素结构。我们将向您展示如何创建具有结构化元素的 PDF 文档以及如何分层组织它们。使用 Aspose.PDF 库大大简化了 PDF 元素的操作，并提供了处理结构化文档的高级功能。

## 第 1 步：设置环境
在您开始之前，请确保您已经使用 Aspose.PDF for .NET 设置了您的开发环境。还要确保您在中设置了文档目录的路径`dataDir`多变的。

## 第 2 步：创建 PDF 文档
首先，我们将使用`Document`Aspose.PDF 提供的类。这是此步骤的代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建 PDF 文档
Document document = new Document();
```

## 第 3 步：让内容与 TaggedPdf 一起使用
Aspose.PDF 库允许使用标记 PDF 的概念处理结构化 PDF 文档。为此，我们需要使用文档的`TaggedContent`财产。这是此步骤的代码：

```csharp
//获取内容以使用 TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;
```

## 第四步：设置文档标题和语言
在开始创建元素结构之前，我们需要定义文档的标题和语言。这可以使用`SetTitle`和`SetLanguage`的方法`taggedContent`目的。这是此步骤的代码：

```csharp
//定义文档标题和语言
taggedContent.SetTitle("Structured PDF Document");
taggedContent.SetLanguage("fr-FR");
```

## 第 5 步：创建逻辑结构元素
现在我们已经设置了文档并设置了标题和语言，我们可以开始创建逻辑结构元素了。这些元素将被分层组织以形成结构树。这是此步骤的代码：

```csharp
//获取根结构元素（Document）
StructureElement rootElement = taggedContent.RootElement;

//创建逻辑结构
SectElement sect1 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect1);

SectElement sect2 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect2);

DivElement div11 = taggedContent.CreateDivElement();
sect1.AppendChild(div11);

DivElement div12 = taggedContent.CreateDivElement();
sect1.AppendChild(div12);

ArtElement art21 = taggedContent.CreateArtElement();
sect2.AppendChild(art21);

ArtElement art22

  = taggedContent.CreateArtElement();
sect2.AppendChild(art22);

DivElement div211 = taggedContent.CreateDivElement();
art21.AppendChild(div211);

DivElement div212 = taggedContent.CreateDivElement();
art21.AppendChild(div212);

DivElement div221 = taggedContent.CreateDivElement();
art22.AppendChild(div221);

DivElement div222 = taggedContent.CreateDivElement();
art22.AppendChild(div222);

SectElement sect3 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect3);

DivElement div31 = taggedContent.CreateDivElement();
sect3.AppendChild(div31);
```

## 步骤 6：保存标记的 PDF 文档
一旦我们创建了元素结构，我们就可以保存 PDF 文档。使用`Save`的方法`document`对象指定要保存的 PDF 文件的路径和名称。这是此步骤的代码：

```csharp
//保存标记的 PDF 文档
document.Save(dataDir + "StructureElementsTree.pdf");
```

### 使用 Aspose.PDF for .NET 创建结构元素树的示例源代码 
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
//获取根结构元素（文档）
StructureElement rootElement = taggedContent.RootElement;
//创建逻辑结构
SectElement sect1 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect1);
SectElement sect2 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect2);
DivElement div11 = taggedContent.CreateDivElement();
sect1.AppendChild(div11);
DivElement div12 = taggedContent.CreateDivElement();
sect1.AppendChild(div12);
ArtElement art21 = taggedContent.CreateArtElement();
sect2.AppendChild(art21);
ArtElement art22 = taggedContent.CreateArtElement();
sect2.AppendChild(art22);
DivElement div211 = taggedContent.CreateDivElement();
art21.AppendChild(div211);
DivElement div212 = taggedContent.CreateDivElement();
art21.AppendChild(div212);
DivElement div221 = taggedContent.CreateDivElement();
art22.AppendChild(div221);
DivElement div222 = taggedContent.CreateDivElement();
art22.AppendChild(div222);
SectElement sect3 = taggedContent.CreateSectElement();
rootElement.AppendChild(sect3);
DivElement div31 = taggedContent.CreateDivElement();
sect3.AppendChild(div31);
//保存标记的 Pdf 文档
document.Save(dataDir + "StructureElementsTree.pdf");

```

## 结论
您已经学习了如何使用 Aspose.PDF for .NET 创建树元素结构。本指南向您展示了设置 PDF 文档、创建逻辑结构元素和保存最终文档所需的步骤。通过使用 Aspose.PDF，您可以轻松地操作 PDF 元素并创建结构化文档。
