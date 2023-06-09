---
title: 提取文本页面
linktitle: 提取文本页面
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 文档的特定页面中提取文本。
type: docs
weight: 200
url: /zh/net/programming-with-text/extract-text-page/
---

本教程将指导您完成使用 Aspose.PDF for .NET 从 PDF 文档的特定页面中提取文本的过程。提供的 C# 源代码演示了必要的步骤。

## 要求
在开始之前，请确保您具有以下内容：

- Visual Studio 或计算机上安装的任何其他 C# 编译器。
- .NET 库的 Aspose.PDF。您可以从 Aspose 官方网站下载它，或者使用像 NuGet 这样的包管理器来安装它。

## 第 1 步：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 第 2 步：导入所需的命名空间
在要提取文本的代码文件中，在文件顶部添加以下 using 指令：

```csharp
using Aspose.Pdf;
using System.IO;
```

## 第三步：设置文档目录
在代码中，找到显示的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并更换`"YOUR DOCUMENT DIRECTORY"`与存储文档的目录的路径。

## 第 4 步：打开 PDF 文档
使用打开现有的 PDF 文档`Document`构造函数并将路径传递到输入 PDF 文件。

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## 第 5 步：从特定页面中提取文本
创建一个`TextAbsorber`对象从文档中提取文本。通过访问它来接受所需页面的吸收器`Pages`的集合`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## 第 6 步：获取提取的文本
从中访问提取的文本`TextAbsorber`目的。

```csharp
string extractedText = textAbsorber.Text;
```

## 第 7 步：保存提取的文本
创建一个`TextWriter`并打开要保存提取文本的文件。将提取的文本写入文件并关闭流。

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### 使用 Aspose.PDF for .NET 提取文本页面的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
//创建 TextAbsorber 对象以提取文本
TextAbsorber textAbsorber = new TextAbsorber();
//接受特定页面的吸收器
pdfDocument.Pages[1].Accept(textAbsorber);
//获取提取的文本
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
//创建编写器并打开文件
TextWriter tw = new StreamWriter(dataDir);
//向文件写入一行文本
tw.WriteLine(extractedText);
//关闭流
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## 结论
您已经使用 Aspose.PDF for .NET 成功地从 PDF 文档的特定页面中提取了文本。提取的文本已保存到指定的输出文件中。