---
title: 使用文本设备提取文本
linktitle: 使用文本设备提取文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 中的文本设备从 PDF 文档中提取文本。
type: docs
weight: 210
url: /zh/net/programming-with-text/extract-text-using-text-device/
---
本教程将指导您使用 Aspose.PDF for .NET 中的文本设备从 PDF 文档中提取文本的过程。提供的 C# 源代码演示了必要的步骤。

## 要求
开始之前，请确保您已准备好以下物品：

- 您的机器上安装的 Visual Studio 或任何其他 C# 编译器。
- Aspose.PDF for .NET 库。您可以从 Aspose 官方网站下载它，或者使用 NuGet 等包管理器来安装它。

## 步骤 1：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 步骤 2：导入所需的命名空间
在要提取文本的代码文件中，在文件顶部添加以下使用指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## 步骤3：设置文档目录
在代码中，找到以下行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`使用存储文档的目录路径。

## 步骤 4：打开 PDF 文档
使用打开现有 PDF 文档`Document`构造函数并将路径传递给输入的 PDF 文件。

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## 步骤 5：使用文本设备提取文本
创建一个`StringBuilder`对象来保存提取的文本。遍历文档的每一页并使用`TextDevice`从每个页面中提取文本。

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## 步骤 6：保存提取的文本
指定输出文件路径并使用`File.WriteAllText`方法。

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### 使用 Aspose.PDF for .NET 的文本设备提取文本的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//用于保存提取文本的字符串
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		//创建文本设备
		TextDevice textDevice = new TextDevice();
		//设置文本提取选项 - 设置文本提取模式（原始或纯）
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		//转换特定页面并将文本保存到流中
		textDevice.Process(pdfPage, textStream);
		//转换特定页面并将文本保存到流中
		textDevice.Process(pdfDocument.Pages[1], textStream);
		//关闭内存流
		textStream.Close();
		//从内存流中获取文本
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
//将提取的文本保存在文本文件中
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## 结论
您已成功使用 Aspose.PDF for .NET 中的文本设备从 PDF 文档中提取文本。提取的文本已保存到指定的输出文件。

### 常见问题解答

#### 问：本教程的目的是什么？

答：本教程提供了使用 Aspose.PDF for .NET 中的文本设备功能从 PDF 文档中提取文本的指导。随附的 C# 源代码演示了完成此任务的必要步骤。

#### 问：我应该导入哪些命名空间？

答：在您计划提取文本的代码文件中，在文件开头包含以下使用指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### 问：如何指定文档目录？

答：在代码中，找到以下行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

#### 问：如何打开现有的 PDF 文档？

答：在第 4 步中，您将使用`Document`构造函数并提供输入 PDF 文件的路径。

#### 问：如何使用文本设备提取文本？

答：第 5 步涉及创建`StringBuilder`对象来保存提取的文本。然后，您将遍历文档的每一页，并使用`TextDevice`以及`TextExtractionOptions`从每个页面中提取文本。

#### 问：如何将提取的文本保存到文件？

答：在第 6 步中，您将指定输出文件路径并使用`File.WriteAllText`方法将提取的文本保存到文本文件。

#### 问：本教程的重点是什么？

答：通过本教程，您学会了如何利用 Aspose.PDF for .NET 中的文本设备功能从 PDF 文档中提取文本。提取的文本已保存到指定的输出文件中，使您能够根据需要操作和利用提取的内容。