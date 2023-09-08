---
title: 提取 PDF 文件中的全部文本
linktitle: 提取 PDF 文件中的所有文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 提取 PDF 文件中的所有文本。
type: docs
weight: 180
url: /zh/net/programming-with-text/extract-text-all/
---
本教程将指导您完成使用 Aspose.PDF for .NET 提取 PDF 文件中所有文本的过程。提供的 C# 源代码演示了必要的步骤。

## 要求
在开始之前，请确保您具备以下条件：

- Visual Studio 或计算机上安装的任何其他 C# 编译器。
- Aspose.PDF for .NET 库。您可以从 Aspose 官方网站下载它或使用 NuGet 等包管理器来安装它。

## 第 1 步：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 第2步：导入所需的命名空间
在要提取文本的代码文件中，在文件顶部添加以下 using 指令：

```csharp
using Aspose.Pdf;
using System.IO;
```

## 第三步：设置文档目录
在代码中，找到显示以下内容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`以及存储文档的目录的路径。

## 步骤 4：打开 PDF 文档
使用以下命令打开现有 PDF 文档`Document`构造函数并将路径传递给输入 PDF 文件。

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## 第 5 步：提取所有文本
创建一个`TextAbsorber`对象从文档中提取文本。然后，接受所有页面的吸收器。

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## 第6步：获取提取的文本
访问提取的文本`TextAbsorber`目的。

```csharp
string extractedText = textAbsorber.Text;
```

## 第7步：保存提取的文本
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
//创建编写器并打开文件
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
//将一行文本写入文件
tw.WriteLine(extractedText);
//关闭流
tw.Close();
```

## 结论
您已使用 Aspose.PDF for .NET 成功从 PDF 文档中提取了所有文本。提取的文本已保存到指定的输出文件中。

### 常见问题解答

#### 问：本教程的目的是什么？

答：本教程作为指南，帮助您使用 Aspose.PDF for .NET 从 PDF 文件中提取所有文本。随附的 C# 源代码提供了完成此任务的分步说明。

#### 问：我应该导入哪些命名空间？

答：在要提取文本的代码文件中，在文件开头包含以下 using 指令：

```csharp
using Aspose.Pdf;
using System.IO;
```

#### 问：如何指定文档目录？

答：找到该线`string dataDir = "YOUR DOCUMENT DIRECTORY";`在代码中并替换`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

#### 问：如何打开现有的 PDF 文档？

答：在步骤 4 中，您将使用以下命令打开现有的 PDF 文档：`Document`构造函数并提供输入 PDF 文件的路径。

#### 问：如何从文档中提取所有文本？

答：第 5 步涉及创建`TextAbsorber`对象从 PDF 文档中提取文本。然后，您将接受所有页面的吸收器。

#### 问：如何访问提取的文本？

答：第 6 步将引导您访问从`TextAbsorber`目的。

#### 问：如何将提取的文本保存到文件中？

答：在第 7 步中，您将创建一个`TextWriter`，打开要保存提取的文本的文件，将提取的文本写入该文件，然后关闭流。

#### 问：本教程的主要内容是什么？

答：通过学习本教程，您已经了解了如何使用 Aspose.PDF for .NET 从 PDF 文档中提取所有文本。提取的文本已保存到指定的输出文件中，使您能够分析和操作文档的文本内容。