---
title: 获得个人附件
linktitle: 获得个人附件
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 获取 PDF 文件中的单个附件。
type: docs
weight: 60
url: /zh/net/programming-with-attachments/get-individual-attachment/
---
在本教程中，我们将逐步引导您完成以下 C# 源代码，以使用 Aspose.PDF for .NET 获取 PDF 文件的单个附件。

在开始之前，请确保您已经安装了 Aspose.PDF 库并设置了您的开发环境。还具有 C# 编程的基本知识。

### 第 1 步：文档目录设置

在提供的源代码中，您需要指定要从中获取单个附件的 PDF 文件所在的目录。将“dataDir”变量更改为所需的目录。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 第 2 步：打开现有的 PDF 文档

我们使用指定的路径打开现有的 PDF 文档。

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
```

### 第 3 步：获取特定附件

我们从文档的附件集合中检索特定附件。在此示例中，我们使用索引 1 获取第一个附件。

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### 第 4 步：获取文件属性

我们显示附件属性，例如名称、描述、MIME 类型、控件散列、创建日期、修改日期和大小。

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

//检查对象参数是否包含附加信息
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### 第 5 步：检索附件并保存到文件

我们检索附件的内容并将其保存到文本文件中。在此示例中，文件以名称“test_out.txt”保存。

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### 使用 Aspose.PDF for .NET 获取个人附件的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
//获取特定的嵌入文件
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
//获取文件属性
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
//检查参数对象是否包含参数
if (fileSpecification.Params != null)
{
	Console.WriteLine("CheckSum: {0}",
	fileSpecification.Params.CheckSum);
	Console.WriteLine("Creation Date: {0}",
	fileSpecification.Params.CreationDate);
	Console.WriteLine("Modification Date: {0}",
	fileSpecification.Params.ModDate);
	Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
//获取附件并写入文件或流
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## 结论

在本教程中，我们解释了如何使用 Aspose.PDF for .NET 从 PDF 文件中获取单个附件。您现在可以使用这些知识从您的 PDF 文件中提取和保存附件。
