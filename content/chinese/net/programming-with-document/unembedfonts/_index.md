---
title: 取消嵌入字体并优化 PDF 文件
linktitle: 取消嵌入字体并优化 PDF 文件
second_title: Aspose.PDF for .NET API 参考
description: 在本分步教程中了解如何使用 Aspose.PDF for .NET 取消嵌入字体和优化 PDF 文件。
type: docs
weight: 370
url: /zh/net/programming-with-document/unembedfonts/
---
## 介绍

在数字时代，PDF 无处不在。无论您共享的是报告、演示文稿还是电子书，便携式文档格式 (PDF) 都是维护文档完整性的首选。但是，随着我们创建和共享的 PDF 越来越多，文件大小也会膨胀，发送或存储起来很麻烦。这就是 Aspose.PDF for .NET 发挥作用的地方，它提供了强大的工具来优化您的 PDF 文件。在本教程中，我们将深入研究如何使用 Aspose.PDF for .NET 取消嵌入字体和优化 PDF 文件。

## 先决条件

在我们讨论细节之前，让我们确保您已准备好开始所需的一切：

1. Visual Studio：确保您的机器上安装了 Visual Studio。这是我们用来编写和运行 .NET 代码的 IDE。
2.  Aspose.PDF for .NET：您需要下载并安装 Aspose.PDF 库。您可以从[下载链接](https://releases.aspose.com/pdf/net/).
3. C# 基础知识：熟悉 C# 编程将帮助您理解我们将使用的代码片段。
4.  PDF 文件：准备好要优化的 PDF 文件。您可以使用任何 PDF，但为了演示，我们将其称为`OptimizeDocument.pdf`.

## 导入包

首先，您需要在 C# 项目中导入必要的包。具体操作如下：

1. 在 Visual Studio 中打开您的项目。
2. 添加对 Aspose.PDF 的引用：在解决方案资源管理器中右键单击您的项目，选择“管理 NuGet 包”，然后搜索`Aspose.PDF`安装包。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

现在我们已经完成所有设置，让我们将优化过程分解为易于管理的步骤。

## 步骤 1：设置文档目录

首先，您需要定义文档目录的路径。这是存储 PDF 文件的位置。操作方法如下：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`与您的 PDF 文件所在的实际路径。这很重要，因为程序需要知道在哪里找到您想要优化的 PDF。

## 第 2 步：打开 PDF 文档

现在我们已经设置了目录，是时候打开我们要优化的 PDF 文档了。以下是执行此操作的代码：

```csharp
//打开文档
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

这行代码创建一个新的`Document`对象，代表您的 PDF 文件。请确保文件名与您目录中的文件名匹配。

## 步骤 3：设置优化选项

接下来，我们需要指定优化选项。在本例中，我们要取消嵌入字体。设置方法如下：

```csharp
//设置 UnembedFonts 选项
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    UnembedFonts = true
};
```

通过设置`UnembedFonts`到`true`，我们指示 Aspose.PDF 通过取消嵌入字体来优化 PDF。这可以显著减小文件大小，特别是当 PDF 包含许多嵌入字体时。

## 步骤4：优化PDF文档

设置好选项后，就该优化 PDF 文档了。以下是执行此操作的代码：

```csharp
Console.WriteLine("Start");
//使用 OptimizationOptions 优化 PDF 文档
pdfDocument.OptimizeResources(optimizeOptions);
```

此代码片段调用`OptimizeResources`方法`pdfDocument`对象，应用我们之前定义的优化选项。您将在控制台中看到一条消息，表明优化过程已开始。

## 步骤 5：保存更新后的文档

优化 PDF 后，我们需要保存更新后的文档。操作方法如下：

```csharp
//保存更新的文档
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
```

此代码将优化的 PDF 保存为`OptimizeDocument_out.pdf`在同一目录中。您可以根据需要选择不同的名称，但保持相似有助于识别原始版本和优化版本。

## 步骤 6：比较文件大小

最后，检查一下节省了多少空间总是好的。下面介绍如何比较原始文件和优化文件的大小：

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

此代码检索原始 PDF 和优化 PDF 的文件大小并将其打印到控制台。看到文件大小减少了多少，真是令人欣慰！

## 结论

就这样！您已成功使用 Aspose.PDF for .NET 取消嵌入字体并优化 PDF 文件。此过程不仅有助于减小文件大小，而且还能提高 PDF 文档的性能。无论您是通过电子邮件共享文件还是将其存储在云中，较小的文件大小都会带来巨大的变化。

## 常见问题解答

### 什么是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一个功能强大的库，允许开发人员以编程方式创建、操作和优化 PDF 文档。

### 我可以免费使用 Aspose.PDF 吗？
是的，Aspose 提供免费试用版。您可以从以下网址下载[这里](https://releases.aspose.com/).

### 如何获得 Aspose.PDF 的支持？
您可以通过以下方式获得支持[Aspose 论坛](https://forum.aspose.com/c/pdf/10).

### 我可以对 PDF 执行哪些类型的优化？
您可以取消嵌入字体、压缩图像、删除未使用的对象等来优化您的 PDF 文件。

### 我可以在哪里购买 Aspose.PDF for .NET？
您可以从[Aspose 购买页面](https://purchase.aspose.com/buy).