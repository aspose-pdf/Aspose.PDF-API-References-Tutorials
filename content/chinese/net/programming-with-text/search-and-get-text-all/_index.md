---
title: 搜索并获取全部文本
linktitle: 搜索并获取全部文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 文档的所有页面搜索和获取文本。
type: docs
weight: 420
url: /zh/net/programming-with-text/search-and-get-text-all/
---
本教程介绍如何使用 Aspose.PDF for .NET 从 PDF 文档的所有页面搜索和获取文本。提供的 C# 源代码逐步演示了该过程。

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
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

确保更换`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

## 第 4 步：搜索并提取文本

创建一个`TextFragmentAbsorber`对象查找输入搜索短语的所有实例：

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

代替`"text"`与您要搜索的实际文本。

## 第5步：在所有页面上搜索

接受文档所有页面的吸收器：

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 第6步：获取提取的文本片段

使用以下命令获取提取的文本片段`TextFragments`的财产`TextFragmentAbsorber`目的：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 第 7 步：循环文本片段

循环遍历 getd 文本片段并访问它们的属性：

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
    Console.WriteLine("Text: {0} ", textFragment.Text);
    Console.WriteLine("Position: {0} ", textFragment.Position);
    Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
    Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
    Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
    Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
    Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
    Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
    Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
    Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

您可以修改循环内的代码以对每个文本片段执行进一步的操作。

### 使用 Aspose.PDF for .NET 搜索并获取全部文本的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//创建 TextAbsorber 对象以查找输入搜索短语的所有实例
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
//接受所有页面的吸收器
pdfDocument.Pages.Accept(textFragmentAbsorber);
//获取提取的文本片段
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
//循环遍历片段
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## 结论

恭喜！您已成功学习如何使用 Aspose.PDF for .NET 从 PDF 文档的所有页面搜索和获取文本。本教程提供了从加载文档到访问提取的文本片段的分步指南。现在，您可以将此代码合并到您自己的 C# 项目中，以分析和处理 PDF 文件中的文本内容。

### 常见问题解答

#### 问：“搜索并获取全部文本”教程的目的是什么？

答：“搜索并获取全部文本”教程演示了如何利用 .NET 的 Aspose.PDF 库从 PDF 文档的所有页面中搜索和提取文本。本教程提供了用于执行文本搜索和检索的分步说明以及示例 C# 代码。

#### 问：本教程如何帮助从 PDF 文档中提取文本？

答：本教程将指导您完成从 PDF 文档的所有页面中提取文本的过程。它使用 Aspose.PDF 库来定位特定文本短语并检索相关信息，例如位置、字体属性和颜色。

#### 问：学习本教程的先决条件是什么？

答：在开始本教程之前，您应该对 C# 编程语言有基本的了解。此外，您需要安装 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它或使用 NuGet 将其集成到您的项目中。

#### 问：如何设置我的项目来遵循本教程？

答：首先，在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目，并添加对 Aspose.PDF for .NET 库的引用。这将允许您在项目中访问该库的功能。

#### 问：如何搜索 PDF 文档中的特定文本？

答：您可以使用`TextFragmentAbsorber`类来查找 PDF 文档中特定搜索短语的实例。通过创建此类的实例并指定目标文本，您可以捕获该文本的所有出现位置。

#### 问：我可以搜索 PDF 文档所有页面的文本吗？

答：是的，本教程演示了如何在 PDF 文档的所有页面中搜索文本。这`pdfDocument.Pages.Accept(textFragmentAbsorber)`方法用于接受所有页面的吸收器，允许您在每个页面上搜索所需的文本。

#### 问：如何访问提取的文本片段？

答：搜索文本后，您可以使用以下命令访问提取的文本片段：`TextFragments`的财产`TextFragmentAbsorber`目的。此属性提供对集合的访问`TextFragment`包含提取的文本和相关信息的对象。

#### 问：我可以从提取的文本片段中检索哪些信息？

答：您可以从提取的文本片段中检索各种详细信息，例如实际文本内容、位置（X 和 Y 坐标）、字体信息（名称、大小、颜色等）等。本教程的示例代码演示了如何访问和打印这些详细信息。

#### 问：我可以对提取的文本片段执行进一步的操作吗？

答：当然。提取文本片段后，您可以修改循环中的代码以对每个片段执行自定义操作。这可能包括保存提取的文本、分析文本模式或应用格式更改。