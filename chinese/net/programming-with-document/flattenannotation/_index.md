---
title: 展平注释
linktitle: 展平注释
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 平展 PDF 文档中的注释。保留注释并防止意外更改。
type: docs
weight: 150
url: /zh/net/programming-with-document/flattenannotation/
---

Aspose.PDF for .NET 是一个功能强大的库，它使开发人员能够以编程方式处理 PDF 文档。它提供的功能之一是能够平整 PDF 文档中的注释。拼合 PDF 文档中的注释意味着注释成为文档内容的一部分，无法再编辑或删除。当您想要确保注释被保留并且不会被意外更改时，这很有用。

在本教程中，我们将讨论如何使用 Aspose.PDF for .NET 来展平 PDF 文档中的注释。我们将提供有关如何执行此操作的分步指南以及示例源代码。

## 第 1 步：创建一个新的 C# 控制台应用程序
首先，在 Visual Studio 中创建一个新的 C# 控制台应用程序。您可以随意命名。创建项目后，您需要添加对 Aspose.PDF for .NET 库的引用。

## 第 2 步：导入 Aspose.PDF 命名空间
在 C# 文件的顶部添加以下代码行以导入 Aspose.PDF 命名空间：

```csharp
using Aspose.Pdf;
```

## 第 3 步：打开 PDF 文档
打开要拼合的 PDF 文档：

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 第 4 步：展平注释
展平PDF文档中的注释：

```csharp
foreach (var page in pdfDocument.Pages)
{
    foreach (var annotation in page.Annotations)
    {
        annotation.Flatten();
    }
}
```

## 第 5 步：保存更新的文档
保存更新的文档：

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("\nFlattened annotation successfully.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 的 Flatten Annotation 示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
//展平注释
foreach (var page in pdfDocument.Pages)
{
	foreach (var annotation in page.Annotations)
	{
		annotation.Flatten();
	}

}
//保存更新的文档
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("\nFlattened annotation successfully.\nFile saved at " + dataDir);
```

## 结论
在本教程中，我们讨论了如何使用 Aspose.PDF for .NET 来展平 PDF 文档中的注释。拼合 PDF 文档中的注释是一项有用的功能，可确保注释得以保留且不会被意外更改。 Aspose.PDF for .NET 提供了一个简单易用的 API 来处理 PDF 文档，包括扁平化注释。 

