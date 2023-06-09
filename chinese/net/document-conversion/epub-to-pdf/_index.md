---
title: EPUB 转 PDF
linktitle: EPUB 转 PDF
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 EPUB 转换为 PDF 的分步指南。
type: docs
weight: 30
url: /zh/net/document-conversion/epub-to-pdf/
---

在本教程中，我们将指导您使用适用于 .NET 的 Aspose.PDF 库将 EPUB 文件转换为 PDF。 EPUB（电子出版物）是一种广泛使用的电子书格式，而 PDF（便携式文档格式）是一种文档交换标准。按照下面给出的步骤，您将能够毫不费力地将 EPUB 文件转换为 PDF 格式。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- .NET 的 Aspose.PDF 库安装在您的系统上。
- 开发环境，例如 Visual Studio。

## 第 1 步：上传 EPUB 文件
在此步骤中，我们将使用 Aspose.PDF for .NET 上传 EPUB 文件。请遵循以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//使用 EPUB 加载选项实例化 LoadOption 对象
EpubLoadOptions epubload = new EpubLoadOptions();

//创建文档对象
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`与您的 EPUB 文件所在的实际目录。

## 第 2 步：EPUB 到 PDF 转换
现在我们已经上传了 EPUB 文件，我们可以继续转换为 PDF。使用以下代码：

```csharp
//保存生成的 PDF 文档
pdf. Save(dataDir + "EPUBToPDF_out.pdf");
```

以上代码将加载的EP文件EPUB转换为PDF格式，并保存为filename`"EPUBToPDF_out.pdf"`.请务必为输出 PDF 文件提供正确的路径和文件名。


代替`"YOUR DOCUMENTS DIRECTORY"`使用要保存输出 PDF 文件的所需目录。

### 使用 Aspose.PDF for .NET 将 EPUB 转换为 PDF 的示例源代码

```csharp
try
{
	
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//使用 EPUB 加载选项实例化 LoadOption 对象
	EpubLoadOptions epubload = new EpubLoadOptions();

	//创建文档对象
	Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);

	//保存生成的 PDF 文档
	pdf.Save(dataDir + "EPUBToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}

```

## 结论
在本教程中，我们介绍了使用 .NET 的 Aspose.PDF 库将 EPUB 文件转换为 PDF 的分步过程。按照上述说明，您现在应该能够毫不费力地将 EPUB 文件转换为 PDF 格式。这种转换为共享、打印和存档文档开辟了可能性。

