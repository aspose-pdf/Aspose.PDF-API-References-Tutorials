---
title: 提取 PDF 文件中的列文本
linktitle: 提取 PDF 文件中的列文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 提取 PDF 文件中的列文本。
type: docs
weight: 150
url: /zh/net/programming-with-text/extract-columns-text/
---
本教程将指导您使用 Aspose.PDF for .NET 提取 PDF 文件中的列文本。提供的 C# 源代码演示了必要的步骤。

## 要求
开始之前，请确保您已准备好以下物品：

- 您的机器上安装的 Visual Studio 或任何其他 C# 编译器。
- Aspose.PDF for .NET 库。您可以从 Aspose 官方网站下载它，也可以使用 NuGet 等包管理器来安装它。

## 步骤 1：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 步骤 2：导入所需的命名空间
在您想要提取列文本的代码文件中，在文件顶部添加以下使用指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## 步骤3：设置文档目录
在代码中，找到以下行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`使用存储文档的目录路径。

## 步骤 4：打开 PDF 文档
使用打开现有 PDF 文档`Document`构造函数并将路径传递给输入的 PDF 文件。

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## 步骤 5：调整字体大小
将文本片段的字体大小减小 0.7 倍，以增强可读性并更好地呈现柱状文本。

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

## 步骤 7：保存提取的文本
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
	//需要将字体大小至少缩小 70%
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
您已成功使用 Aspose.PDF for .NET 从 PDF 文档中提取列文本。提取的文本已保存到指定的输出文件。

### 常见问题解答

#### 问：本教程的目的是什么？

答：本教程提供了使用 Aspose.PDF for .NET 从 PDF 文件中提取文本列的分步指南。随附的 C# 源代码提供了所需程序的实际演示。

#### 问：我应该导入哪些命名空间？

答：在您打算提取文本列的代码文件中，在文件开头包含以下使用指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### 问：如何指定文档目录？

答：找到该线`string dataDir = "YOUR DOCUMENT DIRECTORY";`在代码中替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

#### 问：如何打开现有的 PDF 文档？

答：在第 4 步中，您将使用`Document`构造函数并提供输入 PDF 文件的路径。

#### Q：为什么字体大小会调整？

答：第 5 步涉及将文本片段的字体大小缩小 0.7 倍。此调整可增强可读性并更准确地表示分栏文本。

#### 问：如何从列中提取文本？

答：第 6 步包括将修改后的 PDF 文档保存到内存流，将其重新加载为新文档，然后使用`TextAbsorber`类从列中提取文本。

#### 问：保存提取的文本有什么用处？

答：在第 7 步中，您将把提取的文本保存到指定的输出文件路径的文本文件中。

#### 问：为什么要在提取之前缩小字体？

答：减小字体大小有助于确保提取的文本在列内正确对齐，从而更准确地表示原始布局。

#### 问：本教程的重点是什么？

答：通过本教程，您已经掌握了使用 Aspose.PDF for .NET 从 PDF 文档中提取文本列所需的知识和技能。生成的文本已保存到指定的输出文件中。