---
title: 删除所有附件
linktitle: 删除所有附件
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 文件中删除所有附件。易于操作的分步指南。
type: docs
weight: 20
url: /zh/net/programming-with-attachments/delete-all-attachments/
---
在本教程中，我们将逐步引导您完成以下 C# 源代码，以使用 Aspose.PDF for .NET 从 PDF 文件中删除所有附件。

在开始之前，请确保您已经安装了 Aspose.PDF 库并设置了您的开发环境。还具有 C# 编程的基本知识。

### 第 1 步：文档目录设置

在提供的源代码中，您需要指定要从中删除附件的 PDF 文件所在的目录。将“dataDir”变量更改为所需的目录。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 第 2 步：打开现有的 PDF 文档

我们使用指定的路径打开现有的 PDF 文档。

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
```

### 第 3 步：删除所有附件

我们从文档中删除所有附件。

```csharp
pdfDocument.EmbeddedFiles.Delete();
```

### 第 4 步：保存更新的文件

最后，我们将更新后的 PDF 文件保存在指定目录中，名称为“DeleteAllAttachments_out.pdf”。

```csharp
pdfDocument.Save(dataDir + "DeleteAllAttachments_out.pdf");
```

### 使用 Aspose.PDF for .NET 删除所有附件的示例源代码 

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
//删除所有附件
pdfDocument.EmbeddedFiles.Delete();
dataDir = dataDir + "DeleteAllAttachments_out.pdf";
//保存更新的文件
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll attachments deleted successfully.\nFile saved at " + dataDir);

```

## 结论

在本教程中，我们解释了如何使用 Aspose.PDF for .NET 从 PDF 文件中删除所有附件。您现在可以使用这些知识通过删除所有不需要的附件来清理您的 PDF 文档。
