---
title: 提取 PDF 文件中的列文本
linktitle: 提取 PDF 文件中的列文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 提取 PDF 文件中的列文本。
type: docs
weight: 150
url: /zh/net/programming-with-text/extract-columns-text/
---
本教程将指导您完成使用 Aspose.PDF for .NET 提取 PDF 文件中的列文本的过程。提供的 C# 源代码演示了必要的步骤。

## 要求
在开始之前，请确保您具备以下条件：

- Visual Studio 或计算机上安装的任何其他 C# 编译器。
- Aspose.PDF for .NET 库。您可以从 Aspose 官方网站下载它或使用 NuGet 等包管理器来安装它。

## 第 1 步：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 第2步：导入所需的命名空间
在要提取列文本的代码文件中，在文件顶部添加以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## 第三步：设置文档目录
在代码中，找到显示以下内容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`以及存储文档的目录的路径。

## 步骤 4：打开 PDF 文档
使用以下命令打开现有 PDF 文档`Document`构造函数并将路径传递给输入 PDF 文件。

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## 第5步：调整字体大小
将文本片段的字体大小减小 0.7 倍，以增强可读性并更好地表示柱状文本。

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## 步骤 6：从列中提取文本
将修改后的 PDF 文档保存到内存流并将其重新加载为新文档。然后，使用`TextAbsorber`类从列中提取文本。

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## 第7步：保存提取的文本
将提取的文本保存到指定输出文件路径的文本文件中。

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 提取列文本的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	//需要减小字体大小至少 70%
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## 结论
您已使用 Aspose.PDF for .NET 成功从 PDF 文档中提取了列文本。提取的文本已保存到指定的输出文件中。

### 常见问题解答

#### 问：本教程的目的是什么？

答：本教程提供了有关使用 Aspose.PDF for .NET 从 PDF 文件中提取文本列的分步指南。随附的 C# 源代码提供了所需过程的实际演示。

#### 问：我应该导入哪些命名空间？

答：在要提取文本列的代码文件中，在文件开头包含以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### 问：如何指定文档目录？

答：找到该线`string dataDir = "YOUR DOCUMENT DIRECTORY";`在代码中并替换`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

#### 问：如何打开现有的 PDF 文档？

答：在步骤 4 中，您将使用以下命令打开现有的 PDF 文档：`Document`构造函数并提供输入 PDF 文件的路径。

#### Q：为什么要调整字体大小？

答：第 5 步涉及将文本片段的字体大小减小 0.7 倍。此调整增强了可读性并更准确地表示柱状文本。

#### 问：如何从列中提取文本？

答：第 6 步包括将修改后的 PDF 文档保存到内存流，将其重新加载为新文档，然后使用`TextAbsorber`类从列中提取文本。

#### 问：保存提取的文本的目的是什么？

答：在步骤 7 中，您会将提取的文本保存到指定输出文件路径的文本文件中。

#### 问：为什么提取前要减小字体大小？

答：减小字体大小有助于确保提取的文本在列内正确对齐，从而更准确地表示原始布局。

#### 问：本教程的主要内容是什么？

答：通过学习本教程，您已经获得了使用 Aspose.PDF for .NET 从 PDF 文档中提取文本列所需的知识和技能。生成的文本已保存到指定的输出文件中。