---
title: 使用文本设备提取文本
linktitle: 使用文本设备提取文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 中的文本设备从 PDF 文档中提取文本。
type: docs
weight: 210
url: /zh/net/programming-with-text/extract-text-using-text-device/
---
## 介绍

从 PDF 中提取文本可能很棘手，尤其是在处理具有各种格式、嵌入字体或复杂布局的文档时。但使用 Aspose.PDF for .NET，这个过程变得轻而易举！无论您是想将 PDF 的页面转换为纯文本以进行进一步分析，还是只需要提取特定部分，Aspose.PDF 都能满足您的需求。在本教程中，我们将逐步介绍如何使用 Aspose.PDF 中的 TextDevice 类从 PDF 中提取文本。我们还将提供清晰的解释，以便您可以轻松地将相同的方法应用于您自己的项目。

## 先决条件

在我们开始编写代码之前，请确保您已准备好一切。以下是您需要的内容：

1.  Aspose.PDF for .NET: 从下载最新版本[Aspose.PDF for .NET 下载页面](https://releases.aspose.com/pdf/net/).
2. 开发环境：Visual Studio 或任何其他 C# 开发环境。
3. .NET Framework：确保您的项目针对的是.NET Framework 4.x 或更高版本。
4. 输入 PDF 文件：用于文本提取的 PDF 文件。将其放在机器上的目录中（我们将其称为`YOUR DOCUMENT DIRECTORY`）。

## 导入包

在代码顶部，您需要导入使用 Aspose.PDF 所需的命名空间：

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Devices;
using System;
using System.Text;
```

## 步骤 1：加载 PDF 文档

在提取文本之前，我们需要将 PDF 文档加载到内存中。在此步骤中，您将使用 Aspose.PDF 的`Document`类。这将允许您访问文件内的所有页面和内容。

```csharp
//定义 PDF 文档的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载 PDF 文档
Document pdfDocument = new Document(dataDir + "input.pdf");
```

在这里，我们使用`Document pdfDocument = new Document(dataDir + "input.pdf");`加载 PDF。`dataDir`变量保存 PDF 文件的目录路径。这将使我们能够访问整个文档，从而允许我们循环遍历页面并提取内容。

## 步骤 2：设置用于文本存储的字符串生成器

现在文档已加载，我们需要一种方法来存储提取的文本。为此，我们将使用`StringBuilder`这使得字符串连接更有效率。

```csharp
// StringBuilder 用于保存提取的文本
StringBuilder builder = new StringBuilder();
```

我们初始化一个`StringBuilder`实例，它将收集从每个页面提取的文本。与循环中的常规字符串连接相比，这是一种处理大字符串的更有效的方法。

## 步骤 3：循环遍历 PDF 页面

接下来，我们循环遍历 PDF 文档的每一页以提取文本。我们将使用`TextDevice`类，负责将PDF内容转换为文本格式。

```csharp
//循环遍历 PDF 中的所有页面
foreach (Page pdfPage in pdfDocument.Pages)
{
    //处理每个页面以提取文本
}
```

此循环遍历 PDF 的每一页（`pdfDocument.Pages` ）对于每个页面，我们将提取文本并将其添加到我们的`StringBuilder`.

## 步骤 4：从每个页面提取文本

现在，我们为每个页面设置文本提取过程。在这里，我们将创建一个`TextDevice`对象并用它来处理 PDF 页面。`TextDevice`根据我们设置的提取选项提取原始或格式化的文本。

```csharp
using (MemoryStream textStream = new MemoryStream())
{
    //创建用于文本提取的文本设备
    TextDevice textDevice = new TextDevice();
    
    //将文本提取选项设置为“纯”模式
    TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
    textDevice.ExtractionOptions = textExtOptions;

    //从当前页面中提取文本并保存到内存流中
    textDevice.Process(pdfPage, textStream);

    //将内存流转换为文本
    string extractedText = Encoding.Unicode.GetString(textStream.ToArray());

    //将提取的文本附加到 StringBuilder
    builder.Append(extractedText);
}
```

- `TextDevice textDevice = new TextDevice();` ： 这`TextDevice`类用于从 PDF 中提取文本。
- `TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);` ：此选项提取原始文本而不保留任何格式（如字体或位置）。您还可以使用`TextFormattingMode.Raw`如果您需要对格式进行更多的控制。
- `textDevice.Process(pdfPage, textStream);` ：这将处理 PDF 的每一页并将提取的文本存储在`MemoryStream`.
- 最后，我们将文本从`MemoryStream`添加到字符串并将其附加到`StringBuilder`.

## 步骤 5：将提取的文本保存到文件

处理完所有页面后，文本将存储在`StringBuilder`。最后一步是将提取的文本保存到文件中。

```csharp
//定义文本文件的输出路径
dataDir = dataDir + "input_Text_Extracted_out.txt";

//将提取的文本保存到文件
File.WriteAllText(dataDir, builder.ToString());

Console.WriteLine("\nText extracted successfully from PDF document.\nFile saved at " + dataDir);
```

- `File.WriteAllText(dataDir, builder.ToString());`：这将写入`StringBuilder`保存到文本文件中。
- 输出文件的路径是通过在文件名后面附加一个 (`"input_Text_Extracted_out.txt"` ）到`dataDir`小路。

## 结论

使用 Aspose.PDF for .NET 从 PDF 中提取文本是一个简单而有效的过程。按照本指南中概述的步骤，您可以轻松打开 PDF 文档、循环浏览页面并将文本提取到文本文件中。这对于处理大量 PDF 数据、执行文本分析或转换文档以供进一步操作特别有用。

使用 Aspose.PDF，您不仅限于文本提取 - 您可以处理注释、处理图像，甚至可以将 PDF 转换为其他格式，如 HTML 或 Word。该库的灵活性和强大功能使其成为 .NET 应用程序中 PDF 管理的宝贵工具。

## 常见问题解答

### Aspose.PDF 可以从基于图像的 PDF 中提取文本吗？
不是，Aspose.PDF 旨在从基于内容的 PDF 中提取文本。对于基于图像的 PDF，需要 OCR 技术。

### Aspose.PDF 在提取文本时是否保留格式？
默认情况下，提取的文本没有格式，但如果您想保留一些格式，可以调整提取选项。

### 我可以从特定的页面范围中提取文本吗？
是的，您可以修改代码以循环遍历特定范围的页面而不是所有页面。

### Aspose.PDF 中的文本提取模式有哪些？
Aspose.PDF 提供两种模式：Raw 和 Pure。Raw 模式尝试保留原始布局，而 Pure 模式仅提取文本而不进行格式化。

### Aspose.PDF for .NET 是否与 .NET Core 兼容？
是的，Aspose.PDF for .NET 与 .NET Core 和 .NET Framework 完全兼容。