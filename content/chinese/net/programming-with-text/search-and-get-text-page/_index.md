---
title: 在 PDF 文件中搜索并获取文本页面
linktitle: 在 PDF 文件中搜索并获取文本页面
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中的特定页面中搜索并获取文本。
type: docs
weight: 430
url: /zh/net/programming-with-text/search-and-get-text-page/
---
本教程讲解如何使用 Aspose.PDF for .NET 搜索并获取 PDF 文件中特定页面的文本。提供的 C# 源代码逐步演示了该过程。

## 先决条件

在继续本教程之前，请确保您已具备以下条件：

- C# 编程语言的基本知识。
- 已安装 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它，也可以使用 NuGet 将其安装在您的项目中。

## 步骤 1：设置项目

首先在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目，并添加对 Aspose.PDF for .NET 库的引用。

## 第 2 步：导入必要的命名空间

在 C# 文件的开头添加以下使用指令来导入所需的命名空间：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 步骤 3：加载 PDF 文档

设置 PDF 文档目录的路径，然后使用`Document`班级：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

确保更换`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

## 步骤 4：从页面中搜索并提取文本

创建一个`TextFragmentAbsorber`对象来查找特定页面上输入搜索短语的所有实例：

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

代替`"Figure"`使用您想要搜索的实际文本。

## 步骤 5：在特定页面上搜索

接受文档特定页面的吸收器：

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 步骤 6：获取提取的文本片段

使用获取提取的文本片段`TextFragments`的财产`TextFragmentAbsorber`目的：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 步骤 7：循环遍历文本片段和段

循环遍历获取的文本片段及其段，并访问它们的属性：

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

您可以修改循环内的代码以对每个文本段执行进一步的操作。

### 使用 Aspose.PDF for .NET 进行搜索和获取文本页面的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
//创建 TextAbsorber 对象来查找输入搜索短语的所有实例
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
//接受所有页面的吸收器
pdfDocument.Pages.Accept(textFragmentAbsorber);
//获取提取的文本片段
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
//循环遍历片段
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## 结论

恭喜！您已成功学习了如何使用 Aspose.PDF for .NET 搜索和获取 PDF 文档特定页面中的文本。本教程提供了分步指南，从加载文档到访问提取的文本段。您现在可以合并

### 常见问题解答

#### 问： “搜索并获取文本页面”教程的目的是什么？

答：“搜索并获取文本页面”教程旨在说明如何使用 .NET 的 Aspose.PDF 库在 PDF 文件中的特定页面中搜索和检索文本。该教程提供了详细说明和示例 C# 代码来演示该过程。

#### 问：本教程如何帮助从 PDF 文档中的特定页面提取文本？

答：本教程将指导您使用 Aspose.PDF 库从 PDF 文档的特定页面中提取文本。它概述了必要的步骤，并提供了 C# 代码来在选定页面上搜索指定的文本短语并检索相关的文本段。

#### 问：学习本教程的先决条件是什么？

答：在开始本教程之前，您应该对 C# 编程语言有基本的了解。此外，您还需要安装 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它，也可以使用 NuGet 将其集成到您的项目中。

#### 问：如何设置我的项目来遵循本教程？

答：首先，在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目，并添加对 Aspose.PDF for .NET 库的引用。这将使您能够在项目中利用该库的功能。

#### 问：我可以搜索 PDF 文档特定页面上的文本吗？

答：是的，本教程演示了如何在 PDF 文档的特定页面上搜索文本。它涉及使用`TextFragmentAbsorber`类来定位所选页面上特定文本短语的实例。

#### 问：如何访问从特定页面提取的文本片段？

答：在指定页面上搜索文本后，您可以使用`TextSegments`的财产`TextFragment`对象。此属性提供对以下对象的集合的访问：`TextSegment`包含提取的文本和相关信息的对象。

#### 问：我可以从提取的文本片段中检索什么信息？

答：您可以从提取的文本段中检索各种详细信息，包括文本内容、位置（X 和 Y 坐标）、字体信息（名称、大小、颜色等）等。本教程的示例代码演示了如何访问和打印每个文本段的这些详细信息。

#### 问：我可以对提取的文本段执行自定义操作吗？

答：当然。提取文本片段后，您可以自定义循环内的代码，以对每个片段执行其他操作。这可能包括保存提取的文本、分析文本模式或应用格式更改。