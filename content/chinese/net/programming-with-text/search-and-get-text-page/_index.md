---
title: 在 PDF 文件中搜索并获取文本页面
linktitle: 在 PDF 文件中搜索并获取文本页面
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中的特定页面中搜索并获取文本。
type: docs
weight: 430
url: /zh/net/programming-with-text/search-and-get-text-page/
---
## 介绍

您是否曾经需要在 PDF 文档中搜索特定文本并将其提取以供进一步使用？也许您正在构建一个处理文档并需要精确数据提取的应用程序，或者您只是需要高效地解析 PDF。无论您的情况如何，您都来对地方了！在本教程中，我们将深入研究如何使用 Aspose.PDF for .NET 搜索和获取 PDF 文件中页面的文本。无论您是初学者还是经验丰富的开发人员，本指南都将以对话和引人入胜的方式引导您完成每个步骤。准备好了吗？让我们开始吧！

## 先决条件

在开始编码之前，请确保您已准备好所需的一切：

1.  Aspose.PDF for .NET Library：你可以从以下网址下载[这里](https://releases.aspose.com/pdf/net/)或从同一链接获取免费试用版。如需购买，请前往[Aspose 商店](https://purchase.aspose.com/buy).
2. .NET Framework：您需要一个可运行的 .NET 开发环境，例如 Visual Studio。
3. PDF 文件：您需要一个示例 PDF 文件，我们可以在其中搜索和提取文本。在本教程中，我们假设文件名为`SearchAndGetTextPage.pdf`.

## 导入包

首先，我们需要导入必要的命名空间以使用 Aspose.PDF for .NET。确保这些命名空间包含在代码的顶部。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System
```

现在我们已经了解了先决条件，让我们逐步分解代码。每个步骤都已清晰列出，以便于理解。

## 步骤 1：设置文档目录的路径

在与 PDF 交互之前，您需要定义 PDF 文档的存储路径。这可确保程序可以访问该文件。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir：这是存储 PDF 文件的文件夹路径。替换`"YOUR DOCUMENT DIRECTORY"`与 PDF 所在的实际路径。

## 第 2 步：加载 PDF 文档

下一步是将 PDF 文档加载到内存中，以便您可以使用它。操作方法如下：

```csharp
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

- 文档：这是加载 PDF 文件的 Aspose.PDF 类。
- pdfDocument：加载 PDF 文件后存储该文件的变量。

## 步骤 3：创建文本吸收器对象

这`TextFragmentAbsorber`类允许您在 PDF 中搜索特定文本。让我们创建此类的一个实例来查找给定搜索短语的所有实例。

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

- TextFragmentAbsorber：此类负责从 PDF 中查找和提取文本。
- “图形”：将其替换为您想要在 PDF 中搜索的任何文本。

## 步骤 4：将文本吸收器应用于整个 PDF

一旦设置了文本吸收器，您需要告诉程序搜索 PDF 的所有页面。

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- Accept()：此方法将文本吸收器应用于 PDF，扫描每一页以查找您指定的文本。

## 步骤 5：检索并迭代提取的文本

现在我们已经扫描了 PDF，是时候检索结果并显示它们了。我们将循环遍历提取的文本片段。

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- TextFragmentCollection：此集合保存文本吸收器发现的所有文本片段实例。

## 步骤 6：循环遍历每个片段并提取数据

我们现在循环遍历`textFragmentCollection`并提取每个文本段的各种属性，例如其位置、字体细节和颜色。

```csharp
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

- TextFragment：每个片段包含找到的文本的部分。
- TextSegment：每个片段可以有多个段，代表文本的不同部分。
- TextState：提供有关文本的字体、大小和颜色的详细信息。

在这个循环中，我们打印出详细信息，例如实际文本、其位置（X 和 Y 坐标）、字体、字体是否嵌入在 PDF 中以及文本的前景色。

## 结论

就这样！现在，您已成功使用 Aspose.PDF for .NET 从 PDF 文件中搜索和提取文本。这个库的灵活性令人难以置信。无论您需要在大型文档中搜索特定文本、提取文本还是分析其属性，Aspose.PDF 都能轻松完成。此外，借助我们介绍的代码，您可以根据需要对其进行调整。 

## 常见问题解答

### 我可以一次搜索多个短语吗？  
是的，您可以通过创建多个来修改代码以搜索多个短语`TextFragmentAbsorber`对象。

### 如何从特定页面提取文本？  
您可以通过应用`TextFragmentAbsorber`到单个页面，而不是整个文档。例如：`pdfDocument.Pages[1].Accept(textFragmentAbsorber);`.

### Aspose.PDF for .NET 免费吗？  
 Aspose.PDF 是一个商业产品，但你可以使用它[免费试用](https://releases.aspose.com/).

### 我可以使用 Aspose.PDF 从 PDF 中提取图像吗？  
是的，Aspose.PDF 允许您提取除文本之外的图像。检查[文档](https://reference.aspose.com/pdf/net/)了解更多详情。

### 如果我需要更多帮助或支持怎么办？  
您可以随时获得帮助[Aspose 支持论坛](https://forum.aspose.com/c/pdf/10).