---
title: 从页面获取所有注释
linktitle: 从页面获取所有注释
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南了解如何使用 Aspose.PDF for .NET 从 PDF 页面检索所有注释。
type: docs
weight: 70
url: /zh/net/annotations/getallannotationsfrompage/
---
本文将指导您完成使用 Aspose.PDF for .NET 从 PDF 页面中提取所有注释的过程。 Aspose.PDF for .NET 是一个允许开发人员创建、编辑和转换 PDF 文档的库。在本指南的帮助下，您将能够使用提供的 C# 源代码从特定 PDF 页面获取所有注释。

按照以下步骤如何使用 Aspose.PDF for .NET 获取 PDF 页面的所有注释：

## 第 1 步：文档目录的路径

使用 Aspose.PDF for .NET 从 PDF 页面获取所有注释的第一步是设置存储 PDF 文件的文档目录的路径。您可以通过修改以下代码行来执行此操作：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
## 第 2 步：存储您的 PDF 文件

将“您的文档目录”替换为存储 PDF 文件的文件夹路径。例如：

```csharp
string dataDir = @"C:\Users\JohnDoe\Documents\PDFs\";
```

## 第 3 步：打开文档

下一步是打开包含要提取的注释的 PDF 文档。您可以通过添加以下代码来执行此操作：

```csharp
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");
```

这行代码初始化 Document 类的新实例并加载 PDF 文档“GetAllAnnotationsFromPage.pdf”。将此文件名替换为您的 PDF 文件的名称。

## 第 4 步：遍历所有注释

打开 PDF 文档后，您可以循环浏览特定页面上的所有注释。例如，要循环遍历 PDF 文档第一页上的所有注释，添加以下代码：

```csharp
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
    //代码在这里
}
```

此代码循环遍历 PDF 文档第一页上的所有注释，并将每个注释分配给“annotation”变量。

## 第 5 步：获取注释属性

要提取每个注释的属性，您可以在 foreach 循环中添加以下代码：

```csharp
Console.WriteLine("Title : {0} ", annotation.Title);
Console.WriteLine("Subject : {0} ", annotation.Subject);
Console.WriteLine("Contents : {0} ", annotation.Contents);
```

此代码将每个注释的标题、主题和内容写入控制台。

### 使用 Aspose.PDF for .NET 从页面获取所有注释的示例源代码

以下是使用 Aspose.PDF for .NET 从 PDF 页面获取所有注释的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//打开文档
	Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");

	//遍历所有注释
	foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
	{
		//获取注释属性
		Console.WriteLine("Title : {0} ", annotation.Title);
		Console.WriteLine("Subject : {0} ", annotation.Subject);
		Console.WriteLine("Contents : {0} ", annotation.Contents);                
	}

```
