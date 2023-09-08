---
title: 使用子集策略在 PDF 文件中嵌入字体
linktitle: 使用子集策略嵌入字体
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 通过子集策略在 PDF 文件中嵌入字体。通过仅嵌入必要的字符来优化 PDF 大小。
type: docs
weight: 130
url: /zh/net/programming-with-document/embedfontsusingsubsetstrategy/
---
在本教程中，我们将讨论如何使用 Aspose.PDF for .NET 通过子集策略在 PDF 文件中嵌入字体。 Aspose.PDF for .NET 是一个功能强大的库，允许开发人员以编程方式创建、编辑和操作 PDF 文档。在 PDF 文件中嵌入字体是确保文档在不同设备上正确显示的重要步骤，无论这些设备上是否安装了所需的字体。

## 步骤 1：创建一个新的 C# 控制台应用程序
首先，在 Visual Studio 中创建一个新的 C# 控制台应用程序。您可以将其命名为任何您喜欢的名称。创建项目后，您需要添加对 Aspose.PDF for .NET 库的引用。

## 第2步：导入Aspose.PDF命名空间
在 C# 文件顶部添加以下代码行以导入 Aspose.PDF 命名空间：

```csharp
using Aspose.Pdf;
```

## 第 3 步：加载现有 PDF 文件
要将字体嵌入到现有 PDF 文件中，您需要使用 Document 类加载该文件。以下代码演示了如何加载现有的 PDF 文件：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载现有 PDF 文件
Document doc = new Document(dataDir + "input.pdf");
```

## 步骤 4：使用子集策略嵌入字体
Aspose.PDF for .NET 提供了两种字体嵌入策略：SubsetAllFonts 和 SubsetEmbeddedFontsOnly。

SubsetAllFonts 策略将把所有字体作为子集嵌入到文档中。子集是字体的一部分，仅包含文档中使用的字符。此策略对于减小 PDF 文档的文件大小非常有用。

SubsetEmbeddedFontsOnly 策略将仅嵌入已嵌入文档中的字体子集。如果未嵌入字体，则不会受到此策略的影响。

以下代码演示了如何使用子集策略在 PDF 文件中嵌入字体：

```csharp
//对于 SubsetAllFonts，所有字体都将作为子集嵌入到文档中。
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

//对于完全嵌入的字体，将嵌入字体子集，但未嵌入文档的字体不会受到影响。
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## 第5步：保存PDF文档
使用子集策略将所有字体嵌入 PDF 文件后，您需要保存文档。以下代码演示了如何保存PDF文件：

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### 使用 Aspose.PDF for .NET 通过子集策略嵌入字体的示例源代码。 

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
//对于 SubsetAllFonts，所有字体都将作为子集嵌入到文档中。
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
//对于完全嵌入的字体，将嵌入字体子集，但未嵌入文档的字体不会受到影响。
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
doc.Save(dataDir + "Output_out.pdf");
```

## 结论
在本文中，我们讨论了如何使用 Aspose.PDF for .NET 通过子集策略在 PDF 文件中嵌入字体。 Aspose.PDF for .NET 提供了一个简单易用的 API 来处理 PDF 文档，包括使用不同策略添加和嵌入字体。在PDF文件中嵌入字体是确保文档在不同设备上正确显示的重要步骤，而子集策略是减少PDF文档文件大小的有用功能。

### 使用子集策略在 PDF 文件中嵌入字体的常见问题解答

#### 问：PDF 文件中字体嵌入的子集策略是什么？

答：PDF 文件中字体嵌入的子集策略意味着仅嵌入包含文档中使用的字符的字体部分。这有助于通过消除不必要的字体数据来减小 PDF 文档的文件大小。

#### 问：SubsetAllFonts 和 SubsetEmbeddedFontsOnly 策略有什么区别？

答： 的`SubsetAllFonts`策略将把所有字体作为子集嵌入到文档中，而`SubsetEmbeddedFontsOnly`策略将仅嵌入已嵌入文档中的字体子集。后一种策略不会影响尚未嵌入的字体。

#### 问：为什么采用子集策略的字体嵌入很重要？

答：采用子集策略的字体嵌入对于确保 PDF 文件包含正确显示文本所需的字体数据非常重要，同时还可以通过仅包含文档中使用的字符来保持较小的文件大小。

#### 问：我可以使用 Aspose.PDF for .NET 嵌入不同策略的字体吗？

答：是的，Aspose.PDF for .NET 提供了各种字体嵌入策略，包括`SubsetAllFonts`和`SubsetEmbeddedFontsOnly`。您可以根据您的需求选择合适的策略。

#### 问：Aspose.PDF for .NET 是处理 PDF 文档的可靠库吗？

答：是的，Aspose.PDF for .NET 是一个可靠且功能强大的 PDF 文档库。它提供了在 .NET 应用程序中创建、编辑和操作 PDF 文件的丰富功能。