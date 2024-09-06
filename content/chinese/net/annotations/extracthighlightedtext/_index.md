---
title: 提取 PDF 文件中突出显示的文本
linktitle: 提取 PDF 文件中突出显示的文本
second_title: Aspose.PDF for .NET API 参考
description: 通过本教程学习如何使用 Aspose.PDF for .NET 从 PDF 文件高效提取突出显示的文本。非常适合数据分析和内容审查。
type: docs
weight: 60
url: /zh/net/annotations/extracthighlightedtext/
---
## 介绍

处理 PDF 文件时，提取突出显示的文本可能是一项至关重要的任务，无论是用于数据分析、内容审查还是简单地整理笔记。如果您使用的是 Aspose.PDF for .NET，则此过程简单而高效。在本教程中，我们将引导您了解如何使用 Aspose.PDF for .NET 从 PDF 文档中提取突出显示的文本。我们将涵盖从先决条件到分步指导的所有内容，确保您最终全面了解。

## 先决条件

在深入研究代码之前，您需要做好以下几件事：

-  Aspose.PDF for .NET 库：确保您已安装 Aspose.PDF 库。如果没有，您可以从[发布页面](https://releases.aspose.com/pdf/net/).
- 开发环境：您应该设置一个可用的开发环境，例如 Visual Studio。
- C# 基础知识：熟悉 C# 编程语言和面向对象编程至关重要。
- 有效的 Aspose 许可证：虽然你可以从免费试用开始，但可以考虑获取[临时执照](https://purchase.aspose.com/temporary-license/)或从以下网站购买[这里](https://purchase.aspose.com/buy)不受限制地使用。

## 导入包

首先，您需要在 C# 项目中导入必要的命名空间。这对于访问 Aspose.PDF for .NET 提供的类和方法至关重要。

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

现在，让我们分解使用 Aspose.PDF for .NET 从 PDF 文件中提取突出显示文本的过程。每个步骤都详细说明，以帮助您了解底层概念和实现。

## 步骤 1：设置项目目录

首先，你需要设置 PDF 文件所在的项目目录。这就是奇迹发生的地方。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`替换为 PDF 文件所在目录的实际路径。应用程序将从此目录获取 PDF 进行处理。

## 第 2 步：加载 PDF 文档

接下来，您需要加载要从中提取突出显示文本的 PDF 文档。这是使用`Document`Aspose.PDF 提供的类。

```csharp
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

这`Document`类使用 PDF 文件的路径进行实例化。这里，`"ExtractHighlightedText.pdf"`是包含突出显示文本的 PDF 文件的名称。请确保此文件存在于指定目录中。

## 步骤 3：访问注释集合

PDF 文档加载完成后，下一步是访问文档第一页上的注释。注释用于在 PDF 中添加其他信息，如突出显示、注释等。

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
```

这`Annotations`的财产`Page`对象提供对 PDF 特定页面上所有注释的访问。在这里，我们循环遍历第一页上的每个注释。

## 步骤 4：筛选突出显示的文本注释

现在我们可以访问所有注释，我们需要仅过滤掉突出显示的文本注释。这可以通过检查每个注释的类型来实现。

```csharp
if (annotation is TextMarkupAnnotation)
{
    TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
```

这`TextMarkupAnnotation`类用于表示文本标记注释，包括突出显示。`is`关键字检查注释是否属于类型`TextMarkupAnnotation`如果是，则将注释转换为`TextMarkupAnnotation`.

## 步骤 5：提取突出显示的文本

识别出突出显示的注释后，下一步是提取与突出显示相关的文本。

```csharp
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
foreach (TextFragment tf in collection)
{
    Console.WriteLine(tf.Text);
}
```

这`GetMarkedTextFragments()`方法返回`TextFragment`对象，每个对象代表突出显示的文本的一部分。我们循环遍历这个集合，并将每个片段的文本打印到控制台。

## 结论

使用 Aspose.PDF for .NET 从 PDF 中提取突出显示的文本是一项强大的功能，可以简化您的工作流程，尤其是在处理大型文档时。按照本教程中概述的步骤，您可以轻松地在自己的项目中实现此功能。无论您是整理笔记、准备报告还是进行数据分析，此方法都为提取和利用突出显示的文本提供了无缝的解决方案。

## 常见问题解答

### 我可以使用此方法提取其他类型的注释吗？  
是的，你可以通过修改`if`条件来检查不同的注释类型，例如`TextAnnotation`, `StampAnnotation`， ETC。

### 是否可以从 PDF 的所有页面中提取突出显示的文本？  
当然可以！您可以循环遍历 PDF 文档的每一页，并应用相同的提取逻辑来收集每一页的突出显示文本。

### 我需要许可证才能使用 Aspose.PDF for .NET 吗？  
虽然你可以从免费试用开始，但建议获取[临时执照](https://purchase.aspose.com/temporary-license/)或购买完整许可证以无限制访问所有功能。

### 我可以将提取的文本保存到文件中而不是将其打印到控制台吗？  
是的，您可以轻松修改代码，将提取的文本保存为文本文件或任何其他所需格式。

### Aspose.PDF 除了 .NET 之外还支持其他平台吗？  
是的，Aspose.PDF 还支持 Java 和其他平台，在不同的环境中提供类似的功能。