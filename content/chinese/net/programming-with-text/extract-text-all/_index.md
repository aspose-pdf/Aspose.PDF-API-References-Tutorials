---
title: 提取PDF文件中的全部文本
linktitle: 提取PDF文件中的全部文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 提取 PDF 文件中的所有文本。
type: docs
weight: 180
url: /zh/net/programming-with-text/extract-text-all/
---
本教程将指导您使用 Aspose.PDF for .NET 提取 PDF 文件中所有文本的过程。提供的 C# 源代码演示了必要的步骤。

## 要求
开始之前，请确保您已准备好以下物品：

- 您的机器上安装的 Visual Studio 或任何其他 C# 编译器。
- Aspose.PDF for .NET 库。您可以从 Aspose 官方网站下载它，也可以使用 NuGet 等包管理器来安装它。

## 步骤 1：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 步骤 2：导入所需的命名空间
在要提取文本的代码文件中，在文件顶部添加以下使用指令：

```csharp
using Aspose.Pdf;
using System.IO;
```

## 步骤3：设置文档目录
在代码中，找到以下行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`使用存储文档的目录路径。

## 步骤 4：打开 PDF 文档
使用打开现有 PDF 文档`Document`构造函数并将路径传递给输入的 PDF 文件。

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## 步骤 5：提取所有文本
创建一个`TextAbsorber`对象从文档中提取文本。然后，接受所有页面的吸收器。

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## 步骤 6：获取提取的文本
从访问提取的文本`TextAbsorber`目的。

```csharp
string extractedText = textAbsorber.Text;
```

## 步骤 7：保存提取的文本
创建一个`TextWriter`并打开要保存提取文本的文件。将提取的文本写入文件并关闭流。

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### 使用 Aspose.PDF for .NET 提取全部文本的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
//创建 TextAbsorber 对象来提取文本
TextAbsorber textAbsorber = new TextAbsorber();
//接受所有页面的吸收器
pdfDocument.Pages.Accept(textAbsorber);
//获取提取的文本
string extractedText = textAbsorber.Text;
//创建一个写入器并打开文件
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
//向文件写入一行文本
tw.WriteLine(extractedText);
//关闭流
tw.Close();
```

## 结论
您已成功使用 Aspose.PDF for .NET 从 PDF 文档中提取所有文本。提取的文本已保存到指定的输出文件。

### 常见问题解答

#### 问：本教程的目的是什么？

答：本教程可作为指南帮助您使用 Aspose.PDF for .NET 从 PDF 文件中提取所有文本。随附的 C# 源代码提供了完成此任务的分步说明。

#### 问：我应该导入哪些命名空间？

答：在您打算提取文本的代码文件中，在文件开头包含以下使用指令：

```csharp
using Aspose.Pdf;
using System.IO;
```

#### 问：如何指定文档目录？

答：找到该线`string dataDir = "YOUR DOCUMENT DIRECTORY";`在代码中替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

#### 问：如何打开现有的 PDF 文档？

答：在第 4 步中，您将使用`Document`构造函数并提供输入 PDF 文件的路径。

#### 问：如何从文档中提取所有文本？

答：第 5 步涉及创建`TextAbsorber`对象从 PDF 文档中提取文本。然后，您将接受所有页面的吸收器。

#### 问：如何访问提取的文本？

答：第 6 步将引导您访问从`TextAbsorber`目的。

#### 问：如何将提取的文本保存到文件？

答：在第 7 步中，您将创建一个`TextWriter`，打开要保存提取文本的文件，将提取的文本写入文件，然后关闭流。

#### 问：本教程的重点是什么？

答：通过本教程，您学会了如何使用 Aspose.PDF for .NET 从 PDF 文档中提取所有文本。提取的文本已保存到指定的输出文件中，使您能够分析和操作文档的文本内容。