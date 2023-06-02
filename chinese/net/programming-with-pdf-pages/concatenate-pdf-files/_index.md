---
title: 连接 PDF 文件
linktitle: 连接 PDF 文件
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 连接 PDF 文件的分步指南。易于在您的项目中遵循和实施。
type: docs
weight: 20
url: /zh/net/programming-with-pdf-pages/concatenate-pdf-files/
---
在本教程中，我们将逐步引导您使用 Aspose.PDF for .NET 连接 PDF 文件。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，以帮助您了解并在您自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.PDF for .NET 连接 PDF 文件。

## 先决条件
在开始之前，请确保您具备以下条件：

- C#编程语言的基本知识
- 安装在您的开发环境中的 Aspose.PDF for .NET

## 第一步：定义文档目录
首先，您需要设置文档目录的路径。这是要连接的 PDF 文件所在的位置。用适当的路径替换“您的文档目录”。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：打开 PDF 文件
然后您可以打开 PDF 文件以使用`Document`Aspose.PDF 类。请务必为每个 PDF 文件指定正确的路径。

```csharp
Document pdfDocument1 = new Document(dataDir + "Concat1.pdf");
Document pdfDocument2 = new Document(dataDir + "Concat2.pdf");
```

## 第 3 步：连接页面
现在您可以使用将第二个文档的页面添加到第一个文档`Add()`文档的方法`Pages`收藏。这会将两个文档的页面连接成一个文档。

```csharp
pdfDocument1.Pages.Add(pdfDocument2.Pages);
```

## 第 4 步：保存串联的 PDF 文件
最后，您可以使用文档的`Save()`方法。请务必指定正确的路径和文件名。

```csharp
dataDir = dataDir + "ConcatenatePdfFiles_out.pdf";
pdfDocument1.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 连接 Pdf 文件的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开第一个文档
Document pdfDocument1 = new Document(dataDir + "Concat1.pdf");
//打开第二个文件
Document pdfDocument2 = new Document(dataDir + "Concat2.pdf");
//将第二个文档的页面添加到第一个
pdfDocument1.Pages.Add(pdfDocument2.Pages);
dataDir = dataDir + "ConcatenatePdfFiles_out.pdf";
//保存串联的输出文件
pdfDocument1.Save(dataDir);
System.Console.WriteLine("\nPDFs are concatenated successfully.\nFile saved at " + dataDir);

```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 连接 PDF 文件。按照上述步骤，您可以轻松地在自己的项目中实现此功能。随意进一步探索 Aspose.PDF 文档以发现处理 PDF 文件的其他有用功能。
