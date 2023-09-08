---
title: 禁用 PDF 文件中的文件压缩
linktitle: 禁用 PDF 文件中的文件压缩
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 禁用 PDF 文件中的文件压缩。分步指南，方便操作。
type: docs
weight: 30
url: /zh/net/programming-with-attachments/disable-files-compression/
---
在本教程中，我们将引导您逐步完成以下 C# 源代码，以使用 Aspose.PDF for .NET 禁用 PDF 中的文件压缩。

在开始之前，请确保您已经安装了 Aspose.PDF 库并设置了开发环境。还具备 C# 编程的基础知识。

### 第 1 步：文档目录设置

在提供的源代码中，您需要指定要禁用文件压缩的 PDF 文件所在的目录。将“dataDir”变量更改为所需的目录。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 步骤 2：打开现有 PDF 文档

我们使用指定的路径打开现有的 PDF 文档。

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### 步骤 3：设置新文件以添加为附件

我们配置要添加为附件的新文件。在此示例中，我们添加一个名为“test_out.txt”和描述“示例文本文件”的文本文件。

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### 步骤 4：禁用文件压缩

我们通过将 FileSpecification 对象的 Encoding 属性设置为 FileEncoding.None 来禁用文件压缩。

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### 步骤 5：将附件添加到文档的附件集合中

我们将附件添加到文档的附件集合中。

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### 第 6 步：保存新的输出文件

最后，我们将生成的新 PDF 文件以名称“DisableFilesCompression_out.pdf”保存在指定目录中。

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
//指定 Encoding proparty 将其设置为 FileEncoding.None
fileSpecification.Encoding = FileEncoding.None;
//将附件添加到文档的附件集合
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
//保存新输出
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## 结论

在本教程中，我们解释了如何使用 Aspose.PDF for .NET 禁用 PDF 中的文件压缩。您现在可以使用这些知识来维护附加文件的完整性，而无需压缩。

## 在 PDF 文件中禁用文件压缩的常见问题解答

#### 问：为什么我要在 PDF 文档中禁用文件压缩？

答：禁用文件压缩可确保 PDF 文档中的附加文件保持未压缩状态，从而保留其原始质量和内容。

#### 问：禁用文件压缩对 PDF 附件有何好处？

答：禁用压缩可以防止压缩过程中可能发生的任何数据或质量损失，从而确保附加文件按原样呈现。

#### 问：我可以使用本教程选择性地禁用特定附件的压缩吗？

答：是的，本教程将指导您禁用 PDF 文档中各个附件的文件压缩，从而提供细粒度的控制。

#### 问：我可以对哪些类型的附件禁用压缩？

答：您可以对任何类型的附件（例如图像、文档、电子表格等）禁用压缩，以确保保持其完整性。

#### 问：禁用压缩会影响 PDF 文档的整体文件大小吗？

答：禁用附件压缩可能会导致 PDF 文档的整体文件大小略有增加，因为未压缩的文件会占用更多空间。

#### 问：Aspose.PDF for .NET 如何促进禁用文件压缩的过程？

答：Aspose.PDF for .NET 提供了一个易于使用的 API，允许您禁用附件的文件压缩，如提供的源代码中所示。

#### 问：如果需要，我可以稍后重新启用附件压缩吗？

答：是的，如有必要，您可以修改附件的设置以再次启用压缩。

#### 问：如果我在支持压缩的设备或软件上打开 PDF，会发生什么情况？

答：如果您在支持压缩的设备或软件上打开 PDF，附件可能会以未压缩的形式显示，这可能会影响文件大小和渲染性能。

#### 问：是否存在建议禁用压缩的特定场景？

答：对于优先考虑保持原始质量和数据完整性的附件（例如高分辨率图像或敏感文档），建议禁用压缩。