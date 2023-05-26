---
title: 在目录中隐藏页码
linktitle: 在目录中隐藏页码
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南了解如何使用 Aspose.PDF for .NET 隐藏目录中的页码。
type: docs
weight: 220
url: /zh/net/programming-with-document/hidepagenumbersintoc/
---
在本文中，我们将讨论使用 C# 实现 Aspose.PDF for .NET 的在 TOC 中隐藏页码功能。我们将从简要介绍 Aspose.PDF for .NET 开始，然后深入介绍实现此功能的分步指南。 

### 目录

- Aspose.PDF for .NET 简介
- 什么是在目录中隐藏页码功能？
- 先决条件
- 实施在目录中隐藏页码功能的分步指南
- 使用 Aspose.PDF for .NET 在 TOC 中隐藏页码的示例源代码
- 结论

### Aspose.PDF for .NET 简介

Aspose.PDF for .NET 是一个强大的 PDF 操作组件，允许开发人员以编程方式创建、编辑和操作 PDF 文件。它提供了广泛的特性和功能，可以轻松处理 PDF 文档。 Aspose.PDF for .NET 同时支持 32 位和 64 位操作系统，可与 .NET Framework、.NET Core 和 Xamarin 平台一起使用。 

### 什么是在目录中隐藏页码功能？

目录 (TOC) 是 PDF 文档的重要组成部分，可为用户提供内容的快速概览。有时，用户可能希望在 TOC 中隐藏页码以使其更加用户友好。 Aspose.PDF for .NET 提供了一个内置功能来隐藏 TOC 中的页码。此功能可用于创建更加用户友好的 PDF 文档。 

### 先决条件

要学习本教程，您需要具备以下条件：

- Visual Studio 2010 或更高版本
- Aspose.PDF for .NET 安装在您的系统上
- C#编程语言的基础知识

### 实施在目录中隐藏页码功能的分步指南

按照以下步骤使用 Aspose.PDF for .NET 实现在 TOC 中隐藏页码功能：

#### 步骤 1：在 Visual Studio 中创建一个新的 C# 控制台应用程序

打开 Visual Studio 并创建一个新的 C# 控制台应用程序。

#### 第 2 步：添加对 Aspose.PDF for .NET 的引用

右键单击项目中的引用文件夹，然后选择添加引用。浏览到系统上安装 Aspose.PDF for .NET 的位置并添加对它的引用。

## 第 1 步：创建一个新的 PDF 文档

使用以下代码创建一个新的 PDF 文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## 第 2 步：创建目录页面

为 TOC 创建一个新页面并使用以下代码将其添加到 PDF 文档：

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## 第 3 步：将列表部分添加到 PDF 文档的部分集合

使用以下代码将列表部分添加到 PDF 文档的部分集合：

```csharp
tocPage.TocInfo = tocInfo;
```

## 第四步：定义四级列表的格式

通过使用以下代码设置每个级别的左边距和文本格式设置来定义四个级别列表的格式：

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

## 第 5 步：在部分中添加四个标题

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

### 使用 Aspose.PDF for .NET 在 TOC 中隐藏页码的示例源代码

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
	//将列表部分添加到 Pdf 文档的部分集合
	tocPage.TocInfo = tocInfo;
	//通过设置左边距和
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
	//在部分中添加四个标题
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
