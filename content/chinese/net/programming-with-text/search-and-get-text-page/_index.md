---
title: 搜索并获取 PDF 文件中的文本页面
linktitle: 搜索并获取 PDF 文件中的文本页面
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 文件中的特定页面搜索和获取文本。
type: docs
weight: 430
url: /zh/net/programming-with-text/search-and-get-text-page/
---
本教程介绍如何使用 Aspose.PDF for .NET 从 PDF 文件中的特定页面搜索和获取文本。提供的 C# 源代码逐步演示了该过程。

## 先决条件

在继续学习本教程之前，请确保您具备以下条件：

- C# 编程语言的基础知识。
- 安装了 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它或使用 NuGet 将其安装到您的项目中。

## 第 1 步：设置项目

首先在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目，并添加对 Aspose.PDF for .NET 库的引用。

## 第2步：导入必要的命名空间

在 C# 文件的开头添加以下 using 指令以导入所需的命名空间：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第 3 步：加载 PDF 文档

设置 PDF 文档目录的路径并使用以下命令加载文档`Document`班级：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

确保更换`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

## 步骤 4：从页面中搜索并提取文本

创建一个`TextFragmentAbsorber`对象查找特定页面上输入搜索短语的所有实例：

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

代替`"Figure"`与您要搜索的实际文本。

## 第5步：在特定页面上搜索

接受文档特定页面的吸收器：

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 第6步：获取提取的文本片段

使用以下命令获取提取的文本片段`TextFragments`的财产`TextFragmentAbsorber`目的：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 第 7 步：循环遍历文本片段和片段

循环遍历 getd 文本片段及其段，并访问它们的属性：

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

### 使用 Aspose.PDF for .NET 搜索和获取文本页面的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
//创建 TextAbsorber 对象以查找输入搜索短语的所有实例
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

恭喜！您已成功学习如何使用 Aspose.PDF for .NET 从 PDF 文档的特定页面搜索和获取文本。本教程提供了从加载文档到访问提取的文本段的分步指南。您现在可以合并

### 常见问题解答

#### 问：“搜索并获取文本页面”教程的目的是什么？

答：“搜索并获取文本页面”教程旨在说明如何使用 .NET 的 Aspose.PDF 库从 PDF 文件中的特定页面搜索和检索文本。本教程提供了详细说明和示例 C# 代码来演示该过程。

#### 问：本教程如何帮助从 PDF 文档的特定页面中提取文本？

答：本教程将指导您完成使用 Aspose.PDF 库从 PDF 文档的特定页面提取文本的过程。它概述了必要的步骤并提供 C# 代码来搜索所选页面上的指定文本短语并检索关联的文本段。

#### 问：学习本教程的先决条件是什么？

答：在开始本教程之前，您应该对 C# 编程语言有基本的了解。此外，您需要安装 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它或使用 NuGet 将其集成到您的项目中。

#### 问：如何设置我的项目来遵循本教程？

答：首先，在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目，并添加对 Aspose.PDF for .NET 库的引用。这将使您能够在项目中利用该库的功能。

#### 问：我可以搜索 PDF 文档特定页面上的文本吗？

答：是的，本教程演示了如何在 PDF 文档的特定页面上搜索文本。它涉及使用`TextFragmentAbsorber`类来查找所选页面上特定文本短语的实例。

#### 问：如何访问从特定页面提取的文本片段？

 A：在指定页面搜索到文本后，您可以通过以下方式访问提取的文本片段：`TextSegments`的财产`TextFragment`目的。此属性提供对集合的访问`TextSegment`包含提取的文本和相关信息的对象。

#### 问：我可以从提取的文本片段中检索哪些信息？

答：您可以从提取的文本片段中检索各种详细信息，包括文本内容、位置（X 和 Y 坐标）、字体信息（名称、大小、颜色等）等。本教程的示例代码演示了如何访问和打印每个文本段的这些详细信息。

#### 问：我可以对提取的文本段执行自定义操作吗？

答：当然可以。提取文本段后，您可以自定义循环中的代码以对每个段执行其他操作。这可能包括保存提取的文本、分析文本模式或应用格式更改。