---
title: 提取 PDF 文件中的列文本
linktitle: 提取 PDF 文件中的列文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 文件中提取文本列。本指南通过代码示例和说明分解每个步骤。
type: docs
weight: 150
url: /zh/net/programming-with-text/extract-columns-text/
---
## 介绍

您是否正在处理 PDF 文件并需要提取特定列格式的文本？无论您处理的是发票、报告还是任何结构化文档，从 PDF 中准确提取文本都可能是一件棘手的事情。这就是 Aspose.PDF for .NET 可以简化流程的地方。在本教程中，我们将引导您了解如何轻松地从 PDF 文件中提取文本列。 

## 先决条件

在深入研究代码之前，让我们先介绍一下您需要的基本内容：

-  Aspose.PDF for .NET：确保您已安装最新版本的 Aspose.PDF for .NET。如果没有，您可以[点击下载](https://releases.aspose.com/pdf/net/).
- 开发环境：您需要 Visual Studio 或其他 .NET 开发环境来处理代码。
- PDF 文档：手头准备一个示例 PDF 文档，最好是包含文本列的文档，因为我们将从中提取文本。

如果你还没有安装 Aspose.PDF for .NET，你可以获取[免费试用](https://releases.aspose.com/)或者[购买许可证](https://purchase.aspose.com/buy)获得完整功能。您还可以申请[临时执照](https://purchase.aspose.com/temporary-license)如果需要的话。

## 导入命名空间

要在您的项目中使用 Aspose.PDF for .NET，您需要导入以下命名空间：

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## 分步指南：从 PDF 中提取文本列

现在，让我们分解代码的每个部分，以便更好地了解其工作原理。跟随我们一步一步解释该过程的每个部分。

## 步骤 1：加载 PDF 文档

您需要做的第一件事是将 PDF 文件加载到`Document`对象。这就是 Aspose.PDF 与您的文档交互的方式。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

在此步骤中，我们只是定义存储 PDF 文档的目录。替换`"YOUR DOCUMENT DIRECTORY"`以及您的本地 PDF 文件的路径。`Document`对象将 PDF 加载到内存中，以便进行进一步处理。

## 第 2 步：设置文本片段吸收器

接下来，我们将使用`TextFragmentAbsorber`吸收或捕获 PDF 文件中的全部文本。此吸收器类旨在从 PDF 中的特定区域提取文本片段，因此非常适合提取文本列。

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
```

在这里，我们创建一个实例`TextFragmentAbsorber`并将其应用于 PDF 的所有页面，使用`Accept()` 。 这`TextFragmentCollection`存储提取的文本，从这个集合中，我们可以根据需要操作或提取文本。

## 步骤3：调整提取文本的字体大小

捕获文本片段后，您可能希望减小其字体大小，尤其是当原始文本太大时。在此示例中，我们将字体大小减小了 70%。

```csharp
foreach (TextFragment tf in tfc)
{
    //将字体大小缩小 70%
    tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

此代码循环遍历每个`TextFragment`并将其字体大小缩小 70%。调整字体大小可以使提取的文本更易于管理，尤其是在您为不同目的设置格式时。

## 步骤 4：将文档保存到内存流

修改文本后，我们将 PDF 保存为`MemoryStream`这使得我们能够将文档保存在内存中以便进一步处理，而无需将其写回磁盘。

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
```

这里，我们将 PDF 保存到内存流中，然后重新加载文档。当您处理大文件并希望避免不必要的磁盘操作时，此方法非常有用。

## 步骤 5：使用 Text Absorber 提取所有文本

现在我们已经准备好了 PDF，是时候提取文本了。我们将使用`TextAbsorber`从文档中获取所有文本。

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
```

在此步骤中，`TextAbsorber`吸收 PDF 中的所有文本，提取的文本存储在`extractedText`字符串。这就是奇迹发生的地方——您的文本列现在是纯文本格式！

## 步骤 6：将提取的文本保存到文件

最后，我们将提取的文本保存到`.txt`文件以便于访问和进一步使用。

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

此代码将提取的文本写入新的`.txt`文件并将其保存到您指定的目录中。控制台中将显示一条消息以确认该过程已成功。

## 结论

就是这样！使用 Aspose.PDF for .NET 从 PDF 文件中提取文本列比您想象的要容易。只需几行代码，您就可以加载 PDF、提取特定文本、调整格式并将结果保存到文本文件中。

此技术对于处理结构化文档（如表格、报告或任何按列组织的内容）非常有用。无论您需要自动提取数据还是处理批量文档，Aspose.PDF 都能提供高效实现这一目标的工具。

## 常见问题解答

### 我可以从 PDF 的特定页面提取文本吗？  
是的！您可以修改`TextFragmentAbsorber`使用`pdfDocument.Pages[pageIndex].Accept(tfa);`方法。

### 是否可以仅从多列 PDF 中的一列中提取文本？  
是的，但您需要使用以下方法处理文本片段的坐标`TextFragment.Rectangle`以文档的特定区域为目标。

### 如何提高文本提取的准确率？  
为了提高准确性，请确保 PDF 的结构清晰，避免使用布局复杂的文档。您还可以微调`TextFragmentAbsorber`根据字体样式、大小或区域提取文本。

### Aspose.PDF 是否支持从扫描文档中提取文本？  
是的，但您需要使用 OCR（光学字符识别）技术。Aspose 也提供了相关工具。

### 如何处理包含数千页的大型 PDF 文件？  
对于大型 PDF，可分块处理文档，每次从几页中提取文本，以避免占用过多内存。