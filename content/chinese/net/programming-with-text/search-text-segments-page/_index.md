---
title: 在 PDF 文件中搜索文本段页面
linktitle: 在 PDF 文件中搜索文本段页面
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件页面上搜索文本段并检索其属性。
type: docs
weight: 470
url: /zh/net/programming-with-text/search-text-segments-page/
---
本教程介绍如何使用 Aspose.PDF for .NET 搜索 PDF 文件页面上的特定文本段并检索其属性。提供的 C# 源代码逐步演示了该过程。

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

## 第三步：设置文档目录路径

使用以下命令设置文档目录的路径`dataDir`多变的：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

## 第 4 步：加载 PDF 文档

使用加载 PDF 文档`Document`班级：

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

代替`"SearchTextSegmentsPage.pdf"`与您的 PDF 文件的实际名称。

## 第5步：创建一个TextFragmentAbsorber

创建一个`TextFragmentAbsorber`对象查找输入搜索短语的所有实例：

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

代替`"text"`与您想要的搜索短语。

## 第 6 步：接受特定页面的吸收器

接受文档所需页面的吸收器：

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

代替`2`与所需的页码（从 1 开始的索引）。

## 步骤 7：检索提取的文本片段

使用以下命令获取提取的文本片段`TextFragments`的财产`TextFragmentAbsorber`目的：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 第 8 步：循环文本段

循环检索到的文本段并访问它们的属性：

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

### 使用 Aspose.PDF for .NET 搜索文本段页面的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
//创建 TextAbsorber 对象以查找输入搜索短语的所有实例
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

恭喜！您已成功学习如何使用 Aspose.PDF for .NET 在 PDF 文档页面上搜索特定文本段。本教程提供了从加载文档到访问提取的文本段的分步指南。您现在可以将此代码合并到您自己的 C# 项目中，以在 PDF 文件中执行高级文本段搜索。

### 常见问题解答

#### 问：“在 PDF 文件中搜索文本段页面”教程的目的是什么？

答：“在 PDF 文件中搜索文本段页面”教程提供了有关如何利用 .NET 的 Aspose.PDF 库在 PDF 文档的特定页面上搜索特定文本段的全面指南。它涵盖了设置项目、加载 PDF 文档、搜索文本段以及使用 C# 代码检索其属性的过程。

#### 问：本教程如何帮助搜索 PDF 文档中的特定文本段？

答：本教程演示了在 PDF 文档的特定页面上定位和提取特定文本段的过程。通过遵循提供的步骤和代码示例，用户可以有效地搜索所需的文本片段并检索有关其属性的信息。

#### 问：学习本教程需要什么先决条件？

答：在开始本教程之前，您应该对 C# 编程语言有基本的了解。此外，您需要安装 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它或使用 NuGet 将其安装到您的项目中。

#### 问：如何设置我的项目来遵循本教程？

答：首先，在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目，并添加对 Aspose.PDF for .NET 库的引用。这将使您能够利用库的功能来搜索和处理 PDF 文档。

#### 问：我可以使用本教程搜索 PDF 任何页面上的特定文本段吗？

答：是的，本教程提供了如何在 PDF 文档的选定页面上搜索特定文本段的说明。它指导用户设置项目、加载 PDF 以及使用 Aspose.PDF 库来查找和检索所需文本段的属性。

#### 问：如何在本教程中指定要搜索的文本？

答：要指定要搜索的文本，请创建一个`TextFragmentAbsorber`对象并使用以下命令设置其搜索参数`Text`财产。替换默认值`"text"`在教程的代码中添加您所需的搜索短语。

#### 问：如何检索提取的文本段的属性？

接受后`TextFragmentAbsorber`对于 PDF 的特定页面，您可以使用以下命令检索提取的文本片段`TextFragments`吸收体对象的属性。这提供了对文本片段集合的访问，每个文本片段包含多个文本片段。

#### 问：我可以自定义代码以对每个文本段执行其他操作吗？

答：当然。本教程的示例代码提供了一个循环来迭代检索到的文本段。您可以自定义此循环中的代码，以便根据您的项目要求对每个文本段执行其他操作。

#### 问：提取文本段后如何保存修改后的PDF文档？

答：本教程主要关注搜索文本段并检索其属性。如果您打算对 PDF 进行修改，您可以参考其他 Aspose.PDF 文档，了解如何根据您的具体需求操作和保存文档。