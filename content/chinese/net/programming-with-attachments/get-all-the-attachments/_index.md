---
title: 获取PDF文件中的所有附件
linktitle: 获取PDF文件中的所有附件
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 获取 PDF 文件中的所有附件。分步指南，方便操作。
type: docs
weight: 40
url: /zh/net/programming-with-attachments/get-all-the-attachments/
---
在本教程中，我们将引导您逐步完成以下 C# 源代码，以使用 Aspose.PDF for .NET 获取 PDF 文件中的所有附件。

在开始之前，请确保您已经安装了 Aspose.PDF 库并设置了开发环境。还具备 C# 编程的基础知识。

### 第 1 步：文档目录设置

在提供的源代码中，您需要指定要从中获取附件的 PDF 文件所在的目录。将“dataDir”变量更改为所需的目录。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 步骤 2：打开现有 PDF 文档

我们使用指定的路径打开现有的 PDF 文档。

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### 第三步：获取附件集合

我们从文档中获取附件集合。

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### 第 4 步：检索附件

我们浏览集合以获取所有附件并显示它们的信息。我们还将附件保存在单独的文件中。

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

//检查对象参数是否包含附加信息
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

//检索附件并保存在文件中
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### 使用 Aspose.PDF for .NET 获取所有附件的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
//获取嵌入文件集合
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
//获取嵌入文件的数量
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
//循环遍历集合以获取所有附件
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
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
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## 结论

在本教程中，我们解释了如何使用 Aspose.PDF for .NET 从 PDF 文件中获取所有附件。您现在可以使用这些知识从 PDF 文件中提取和操作附件。

## 获取 PDF 文件中所有附件的常见问题解答

#### 问：为什么我需要从 PDF 文档中检索所有附件？

答：检索附件允许您访问和操作 PDF 中嵌入的其他文件，这对于存档、共享或进一步处理非常有用。

#### 问：PDF 文档中可以附加哪些类型的文件？

答：PDF 文档可以包含各种附加文件，包括图像、文档、电子表格、音频文件等。

#### 问：本教程如何帮助我使用 Aspose.PDF for .NET 从 PDF 检索附件？

答：本教程提供了访问和检索 PDF 文档中所有附件的分步说明和 C# 源代码。

#### 问：我可以使用本教程检索特定附件而不是所有附件吗？

答：是的，您可以修改提供的代码以根据您的要求有选择地检索附件。

#### 问：使用本教程我可以获得有关每个附件的哪些信息？

答：本教程演示如何检索和显示附件的名称、描述、MIME 类型、创建日期、修改日期和大小等详细信息。

#### 问：如何使用本教程保存检索到的附件？

答：本教程将指导您将每个检索到的附件另存为指定目录中的单独文件。

#### 问：我可以使用这些知识从受密码保护的 PDF 文件中提取附件吗？

答：是的，您可以应用类似的原理，使用 Aspose.PDF for .NET 从受密码保护的 PDF 文件中检索附件。

#### 问：Aspose.PDF for .NET 如何促进附件检索？

答：Aspose.PDF for .NET 提供了直观的 API，使您可以轻松访问和操作 PDF 文档中的附件。

#### 问：是否存在建议检索附件的特定场景？

答：当您需要访问 PDF 中嵌入的文件（例如提取图像、音频文件或其他文档）时，检索附件非常有用。