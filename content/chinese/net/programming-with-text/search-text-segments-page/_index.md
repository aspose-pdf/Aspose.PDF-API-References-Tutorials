---
title: 在 PDF 文件中搜索文本片段页面
linktitle: 在 PDF 文件中搜索文本片段页面
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件的页面上搜索文本段并检索其属性。
type: docs
weight: 470
url: /zh/net/programming-with-text/search-text-segments-page/
---
本教程讲解如何使用 Aspose.PDF for .NET 在 PDF 文件页面上搜索特定文本段并检索其属性。提供的 C# 源代码逐步演示了该过程。

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

## 步骤3：设置文档目录的路径

使用以下方式设置文档目录的路径：`dataDir`多变的：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

## 步骤 4：加载 PDF 文档

使用加载 PDF 文档`Document`班级：

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

代替`"SearchTextSegmentsPage.pdf"`使用您的 PDF 文件的实际名称。

## 步骤 5：创建 TextFragmentAbsorber

创建一个`TextFragmentAbsorber`对象来查找输入搜索短语的所有实例：

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

代替`"text"`使用您想要的搜索短语。

## 步骤 6：接受特定页面的吸收器

接受所需文档页面的吸收器：

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

代替`2`使用所需的页码（基于 1 的索引）。

## 步骤 7：检索提取的文本片段

使用获取提取的文本片段`TextFragments`的财产`TextFragmentAbsorber`目的：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 步骤 8：循环遍历文本段

循环遍历检索到的文本段并访问其属性：

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

如果需要，修改循环内的代码以对每个文本段执行进一步的操作。

### 使用 Aspose.PDF for .NET 的搜索文本片段页面的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
//创建 TextAbsorber 对象来查找输入搜索短语的所有实例
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
//接受所有页面的吸收器
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
//获取提取的文本片段
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
//循环遍历片段
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## 结论

恭喜！您已成功学习了如何使用 Aspose.PDF for .NET 在 PDF 文档的页面上搜索特定文本段。本教程提供了分步指南，从加载文档到访问提取的文本段。您现在可以将此代码合并到您自己的 C# 项目中，以在 PDF 文件中执行高级文本段搜索。

### 常见问题解答

#### 问： “在 PDF 文件中搜索文本段页面”教程的目的是什么？

答：“在 PDF 文件中搜索文本段页面”教程提供了有关如何利用 Aspose.PDF 库 for .NET 在 PDF 文档的特定页面上搜索特定文本段的全面指南。它涵盖了设置项目、加载 PDF 文档、搜索文本段以及使用 C# 代码检索其属性的过程。

#### 问：本教程如何帮助您在 PDF 文档中搜索特定文本段？

答：本教程演示了在 PDF 文档的特定页面上定位和提取特定文本段的过程。通过遵循提供的步骤和代码示例，用户可以有效地搜索所需的文本段并检索有关其属性的信息。

#### 问：学习本教程需要满足哪些先决条件？

答：在开始本教程之前，您应该对 C# 编程语言有基本的了解。此外，您还需要安装 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它，也可以使用 NuGet 将其安装在您的项目中。

#### 问：如何设置我的项目来遵循本教程？

答：首先，在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目，并添加对 Aspose.PDF for .NET 库的引用。这将使您能够利用该库的功能来搜索和处理 PDF 文档。

#### 问：我可以使用本教程在 PDF 的任意页面上搜索特定文本段吗？

答：是的，本教程提供了如何在 PDF 文档的选定页面上搜索特定文本段的说明。它指导用户设置项目、加载 PDF 以及使用 Aspose.PDF 库来查找和检索所需文本段的属性。

#### 问：如何指定我想在本教程中搜索的文本？

答：要指定要搜索的文本，请创建一个`TextFragmentAbsorber`对象并使用设置其搜索参数`Text`属性。替换默认`"text"`在教程的代码中使用您想要的搜索短语。

#### 问：如何检索提取的文本段的属性？

接受后`TextFragmentAbsorber`对于 PDF 的特定页面，您可以使用`TextFragments`吸收器对象的属性。这可以访问文本片段的集合，每个文本片段包含多个文本段。

#### 问：我可以自定义代码来对每个文本段执行附加操作吗？

答：当然可以。本教程的示例代码提供了一个循环来迭代检索到的文本段。您可以根据项目需求自定义此循环中的代码，以对每个文本段执行其他操作。

#### 问：提取文本片段后，如何保存修改后的 PDF 文档？

答：本教程主要介绍如何搜索文本段并检索其属性。如果您打算对 PDF 进行修改，可以参考其他 Aspose.PDF 文档，了解如何根据特定需求操作和保存文档。