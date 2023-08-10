---
title: 搜索并获取文本页面
linktitle: 搜索并获取文本页面
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 文档的特定页面搜索和获取文本。
type: docs
weight: 430
url: /zh/net/programming-with-text/search-and-get-text-page/
---

本教程介绍如何使用 Aspose.PDF for .NET 从 PDF 文档的特定页面搜索和获取文本。提供的 C# 源代码逐步演示了该过程。

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