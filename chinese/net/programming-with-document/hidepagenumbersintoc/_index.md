---
title: 隐藏目录中的页码
linktitle: 隐藏目录中的页码
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南，了解如何使用 Aspose.PDF for .NET 在目录中隐藏页码。
type: docs
weight: 220
url: /zh/net/programming-with-document/hidepagenumbersintoc/
---
在本文中，我们将讨论使用 C# 实现 Aspose.PDF for .NET 的“在目录中隐藏页码”功能。我们将从 Aspose.PDF for .NET 的简要介绍开始，然后深入了解实现此功能的分步指南。 

## Aspose.PDF for .NET 简介

Aspose.PDF for .NET 是一个功能强大的 PDF 操作组件，允许开发人员以编程方式创建、编辑和操作 PDF 文件。它提供了广泛的特性和功能，可以轻松处理 PDF 文档。 Aspose.PDF for .NET 支持 32 位和 64 位操作系统，并且可与 .NET Framework、.NET Core 和 Xamarin 平台一起使用。 

## 什么是在目录中隐藏页码功能？

目录 (TOC) 是 PDF 文档的重要组成部分，可让用户快速概览内容。有时，用户可能希望隐藏目录中的页码以使其更加用户友好。 Aspose.PDF for .NET 提供了一个内置功能来隐藏目录中的页码。此功能可用于创建更加用户友好的 PDF 文档。 

## 先决条件

要学习本教程，您将需要以下内容：

- Visual Studio 2010 或更高版本
- 您的系统上安装了 Aspose.PDF for .NET
- C# 编程语言基础知识

## 实施“在目录中隐藏页码”功能的分步指南

请按照以下步骤使用 Aspose.PDF for .NET 实现隐藏目录中的页码功能：

## 步骤 1：在 Visual Studio 中创建新的 C# 控制台应用程序

打开 Visual Studio 并创建一个新的 C# 控制台应用程序。

## 步骤 2：添加对 Aspose.PDF for .NET 的引用

右键单击项目中的“引用”文件夹，然后选择“添加引用”。浏览到系统上安装 Aspose.PDF for .NET 的位置并添加对其的引用。

## 第 1 步：创建一个新的 PDF 文档

使用以下代码创建一个新的 PDF 文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## 第 2 步：创建目录页面

使用以下代码为目录创建一个新页面并将其添加到 PDF 文档中：

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## 步骤 3：将列表部分添加到 PDF 文档的部分集合中

使用以下代码将列表部分添加到 PDF 文档的部分集合中：

```csharp
tocPage.TocInfo = tocInfo;
```

## 步骤4：定义四级列表的格式

通过使用以下代码设置每个级别的左边距和文本格式设置来定义四级列表的格式：

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## 步骤 5：在该部分中添加四个标题

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### 使用 Aspose.PDF for .NET 在目录中隐藏页码的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//将列表部分添加到 Pdf 文档的部分集合中
tocPage.TocInfo = tocInfo;
//通过设置左边距和定义四级列表的格式
//各级别文本格式设置

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//在该部分中添加四个标题
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

## 结论

在本教程中，我们探讨了如何使用 Aspose.PDF for .NET 处理 PDF 文档中的 XMP 元数据。 XMP 元数据提供有关 PDF 文档的宝贵信息，包括标题、作者、创建日期等。 Aspose.PDF for .NET 允许开发人员访问和操作这些元数据，提供灵活而强大的 API 来处理 PDF 文档。

### 常见问题解答

#### 问：PDF 文档中的 XMP 元数据是什么？

答：PDF 文档中的 XMP（可扩展元数据平台）元数据是用于存储有关文档的元数据信息的标准格式。它包括文档标题、作者、创建日期、关键字等详细信息。 XMP 元数据提供了一种结构化且标准化的方式来存储和共享有关 PDF 文档的信息。

#### 问：我可以使用 Aspose.PDF for .NET 修改 PDF 文档的 XMP 元数据吗？

答：是的，您可以使用 Aspose.PDF for .NET 以编程方式修改 PDF 文档的 XMP 元数据。您可以访问`Info`的财产`Document`对象，它使您可以访问 XMP 元数据属性。然后，您可以更新这些属性的值以修改 PDF 文档的 XMP 元数据。

#### 问：我可以使用 Aspose.PDF for .NET 从 PDF 文档中提取自定义 XMP 元数据属性吗？

答：是的，您可以使用 Aspose.PDF for .NET 从 PDF 文档中提取自定义 XMP 元数据属性。您可以使用`Metadata`的财产`Document`对象，它提供对 PDF 文档的所有 XMP 元数据属性的访问。然后，您可以提取自定义属性并根据需要使用它们的值。