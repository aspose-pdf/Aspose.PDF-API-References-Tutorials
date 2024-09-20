---
title: 从 PDF 文件的页面区域提取文本
linktitle: 从 PDF 文件的页面区域提取文本
second_title: Aspose.PDF for .NET API 参考
description: 通过本分步指南学习如何使用 Aspose.PDF for .NET 从 PDF 中的特定区域提取文本。高效地从文档中收集和保存文本。
type: docs
weight: 190
url: /zh/net/programming-with-text/extract-text-from-page-region/
---
## 介绍

处理 PDF 通常需要提取特定内容，无论是从表单、表格还是文档的某些部分提取数据。在本教程中，我们将介绍如何使用 Aspose.PDF for .NET 从 PDF 的特定区域提取文本。我们无需筛选整个文档，而是准确找到文本所在的位置并高效地提取它。

## 先决条件

在我们开始编写代码之前，请确保您已准备好以下项目：

1.  Aspose.PDF for .NET：如果您还没有，请下载并安装 Aspose.PDF for .NET 库。[下载 Aspose.PDF for .NET](https://releases.aspose.com/pdf/net/).
2. IDE：任何 .NET 开发环境，如 Visual Studio。
3. .NET Framework：确保您的项目设置了适当的.NET 框架。
4. PDF 文档：我们将从中提取文本的示例 PDF。

别忘了你可以[获得免费试用](https://releases.aspose.com/)Aspose.PDF 或者使用[临时执照](https://purchase.aspose.com/temporary-license/)以实现全部功能。

## 导入必要的包

要开始使用 Aspose.PDF for .NET，您需要将所需的命名空间导入到您的项目中。这些包提供了处理 PDF 文档所需的类和方法。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## 步骤 1：设置文档目录并加载 PDF

第一步是指定 PDF 文件的位置并将其加载到项目中。您可以使用要处理的 PDF 文件的本地目录路径。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开 PDF 文档
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

此步骤可确保 PDF 文件正确加载并可供处理。`Document` Aspose.PDF 库中的类允许您操作 PDF 文件。

## 步骤 2：初始化文本吸收器以进行提取

在此步骤中，我们创建一个`TextAbsorber`对象，用于从 PDF 文档中提取文本。`TextAbsorber`具有灵活性，可以定制以关注特定区域或页面。

```csharp
//创建 TextAbsorber 对象来提取文本
TextAbsorber absorber = new TextAbsorber();
```

这`TextAbsorber`class 是一个强大的工具，可以捕获指定范围内的所有文本。

## 步骤 3：定义要提取文本的区域

神奇的事情就在这里发生。我们不必从整个页面提取文本，而是将提取范围限制在页面的特定矩形区域。当您确切知道内容所在的位置时，这种方法非常有效。

```csharp
//将文本提取限制在特定区域
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
```

这`Rectangle`对象允许您定义要从中提取文本的区域的坐标（以点为单位）。`TextSearchOptions.LimitToPageBounds`确保只提取指定矩形内的文本。

## 步骤 4：在所需页面上接受吸收器

设置区域后，下一步是接受`TextAbsorber`您要从中提取文本的特定页面。这里，我们将重点关注 PDF 的第一页。

```csharp
//接受第一页的吸收器
pdfDocument.Pages[1].Accept(absorber);
```

通过调用`Accept`方法在页面上，我们指示 Aspose.PDF 运行吸收器并从定义的区域收集文本。

## 步骤 5：检索并存储提取的文本

吸收器完成工作后，就该收集提取的文本并保存了。此步骤包括检索文本并将其写入`.txt`文件。

```csharp
//获取提取的文本
string extractedText = absorber.Text;

//创建一个 writer 来保存提取的文本
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");

//将文本写入文件
tw.WriteLine(extractedText);

//关闭流
tw.Close();
```

在这里，`TextWriter`类用于将提取的文本写入文本文件。这可确保您提取的内容安全存储以供日后使用。

## 结论

从 PDF 文档中的特定区域提取文本非常有用，尤其是在处理表单或表格等结构化内容时。使用 Aspose.PDF for .NET，您只需几行代码即可完成此任务。通过定义区域、初始化`TextAbsorber`，并保存提取的文本，您可以完全控制从 PDF 中提取的内容。

无论您正在处理小型项目还是管理大型文档，此方法都提供了一种有效的方法，可以从 PDF 中提取相关数据，而无需梳理整个文档。

## 常见问题解答

### 我可以一次从多个页面提取文本吗？
是的，通过迭代`Pages`收集`pdfDocument`，您可以应用`TextAbsorber`到多个页面。

### 如果文本位于 PDF 的不同区域内怎么办？
您可以轻松调整`Rectangle`坐标以匹配您的文本所在的区域。

### 这适用于扫描的 PDF 吗？
不，扫描的 PDF 需要 OCR（光学字符识别）才能将图像转换为文本。Aspose.PDF 也提供 OCR 功能。

### 有没有办法根据特定关键词提取文本？
是的，你可以使用`TextFragmentAbsorber`用于基于关键字的文本提取。

### 如何从加密的 PDF 中提取文本？
您需要先提供正确的密码来解密 PDF，然后继续提取文本。