---
title: 使用子集策略嵌入字体
linktitle: 使用子集策略嵌入字体
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 通过子集策略将字体嵌入 PDF 文件。通过仅嵌入必要的字符来优化您的 PDF 大小。
type: docs
weight: 130
url: /zh/net/programming-with-document/embedfontsusingsubsetstrategy/
---

在本教程中，我们将讨论如何使用 Aspose.PDF for .NET 使用子集策略在 PDF 文件中嵌入字体。 Aspose.PDF for .NET 是一个功能强大的库，允许开发人员以编程方式创建、编辑和操作 PDF 文档。在 PDF 文件中嵌入字体是确保文档在不同设备上正确显示的重要步骤，无论这些设备上是否安装了所需的字体。

## 第 1 步：创建一个新的 C# 控制台应用程序
首先，在 Visual Studio 中创建一个新的 C# 控制台应用程序。您可以随意命名。创建项目后，您需要添加对 Aspose.PDF for .NET 库的引用。

## 第 2 步：导入 Aspose.PDF 命名空间
在 C# 文件的顶部添加以下代码行以导入 Aspose.PDF 命名空间：

```csharp
using Aspose.Pdf;
```

## 第 3 步：加载现有的 PDF 文件
要在现有 PDF 文件中嵌入字体，您需要使用 Document 类加载该文件。以下代码演示了如何加载现有的 PDF 文件：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载现有的 PDF 文件
Document doc = new Document(dataDir + "input.pdf");
```

## 第 4 步：使用子集策略嵌入字体
Aspose.PDF for .NET 提供了两种字体嵌入策略：SubsetAllFonts 和 SubsetEmbeddedFontsOnly。

SubsetAllFonts 策略将所有字体作为子集嵌入到文档中。子集是字体的一部分，仅包含文档中使用的字符。此策略对于减小 PDF 文档的文件大小很有用。

SubsetEmbeddedFontsOnly 策略将仅嵌入已嵌入文档中的字体子集。如果未嵌入字体，则不会受到此策略的影响。

以下代码演示了如何使用子集策略将字体嵌入到 PDF 文件中：

```csharp
//在 SubsetAllFonts 的情况下，所有字体都将作为子集嵌入到文档中。
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);

//字体子集将嵌入完全嵌入的字体，但未嵌入文档的字体不会受到影响。
doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
```

## 步骤 5：保存 PDF 文档
使用子集策略将所有字体嵌入 PDF 文件后，您需要保存文档。以下代码演示了如何保存 PDF 文件：

```csharp
doc.Save(dataDir + "Output_out.pdf");
```

### 使用 Aspose.PDF for .NET 使用子集策略嵌入字体的示例源代码。 

```csharp

            
            //文档目录的路径。
            string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "input.pdf");
            //在 SubsetAllFonts 的情况下，所有字体都将作为子集嵌入到文档中。
            doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetAllFonts);
            //字体子集将嵌入完全嵌入的字体，但未嵌入文档的字体不会受到影响。
            doc.FontUtilities.SubsetFonts(FontSubsetStrategy.SubsetEmbeddedFontsOnly);
            doc.Save(dataDir + "Output_out.pdf");
            

        
```

## 结论
在本文中，我们讨论了如何使用 Aspose.PDF for .NET 使用子集策略在 PDF 文件中嵌入字体。 Aspose.PDF for .NET 提供了一个简单易用的 API 来处理 PDF 文档，包括使用不同的策略添加和嵌入字体。在 PDF 文件中嵌入字体是确保文档在不同设备上正确显示的重要步骤，而子集策略是减小 PDF 文档文件大小的有用特性。

