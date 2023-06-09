---
title: 禁用文件压缩
linktitle: 禁用文件压缩
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中禁用文件压缩。易于操作的分步指南。
type: docs
weight: 30
url: /zh/net/programming-with-attachments/disable-files-compression/
---
在本教程中，我们将逐步引导您完成以下 C# 源代码，以使用 Aspose.PDF for .NET 禁用 PDF 中的文件压缩。

在开始之前，请确保您已经安装了 Aspose.PDF 库并设置了您的开发环境。还具有 C# 编程的基本知识。

### 第 1 步：文档目录设置

在提供的源代码中，您需要指定要禁用文件压缩的 PDF 文件所在的目录。将“dataDir”变量更改为所需的目录。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 第 2 步：打开现有的 PDF 文档

我们使用指定的路径打开现有的 PDF 文档。

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### 第 3 步：设置要添加为附件的新文件

我们将要添加的新文件配置为附件。在此示例中，我们添加了一个名为“test_out.txt”和描述为“Example text file”的文本文件。

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### 第 4 步：禁用文件压缩

我们通过将 FileSpecification 对象的编码属性设置为 FileEncoding.None 来禁用文件压缩。

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### 第 5 步：将附件添加到文档的附件集合

我们将附件添加到文档的附件集合中。

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### 第 6 步：保存新的输出文件

最后，我们将生成的新 PDF 文件保存在指定目录中，名称为“DisableFilesCompression_out.pdf”。

```csharp
pdfDocument.Save(dataDir + "DisableFilesCompression_out.pdf");
```


### 使用 Aspose.PDF for .NET 禁用文件压缩的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
//设置要添加为附件的新文件
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
//指定编码代理将其设置为 FileEncoding.None
fileSpecification.Encoding = FileEncoding.None;
//将附件添加到文档的附件集合
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
//保存新输出
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## 结论

在本教程中，我们解释了如何使用 Aspose.PDF for .NET 在 PDF 中禁用文件压缩。您现在可以使用这些知识来保持附加文件的完整性而无需压缩。