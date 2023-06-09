---
title: 添加附件
linktitle: 添加附件
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 将附件添加到您的 PDF 文件。易于操作的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-attachments/add-attachment/
---

在本教程中，我们将引导您逐步完成以下 C# 源代码，以使用 Aspose.PDF for .NET 向 PDF 文件添加附件。

在开始之前，请确保您已经安装了 Aspose.PDF 库并设置了您的开发环境。还具有 C# 编程的基本知识。

### 第 1 步：文档目录设置

在提供的源代码中，您需要指定要添加附件的PDF文件所在的目录。将“dataDir”变量更改为所需的目录。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 第 2 步：打开现有的 PDF 文档

我们使用指定的路径打开现有的 PDF 文档。

```csharp
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
```

### 第 3 步：设置要添加为附件的新文件

我们将要添加的新文件配置为附件。在此示例中，我们添加了一个名为“test.txt”和描述为“Example text file”的文本文件。

```csharp
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
```

### 第 4 步：将附件添加到文档的附件集合

我们将附件添加到文档的附件集合中。

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### 第 5 步：保存新的输出文件

最后，我们将生成的新 PDF 文件保存在指定目录中，名称为“AddAttachment_out.pdf”。

```csharp
pdfDocument.Save(dataDir + "AddAttachment_out.pdf");
```

### 使用 Aspose.PDF for .NET 添加附件的示例源代码
 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
//设置要添加为附件的新文件
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
//将附件添加到文档的附件集合
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "AddAttachment_out.pdf";
//保存新输出
pdfDocument.Save(dataDir);
Console.WriteLine("\nSample text file attached successfully.\nFile saved at " + dataDir);

```

## 结论

在本教程中，我们解释了如何使用 Aspose.PDF for .NET 向 PDF 文件添加附件。您现在可以使用这些知识将其他文件作为附件添加到您的 PDF 文档中。
