---
title: 扁平化 PDF 文件中的注释
linktitle: 扁平化 PDF 文件中的注释
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 展平 PDF 文件中的注释。保留注释并防止意外更改。
type: docs
weight: 150
url: /zh/net/programming-with-document/flattenannotation/
---
Aspose.Pdf for .NET 是一个功能强大的库，使开发人员能够以编程方式处理 PDF 文件。它提供的功能之一是能够平铺 PDF 文件中的注释。平铺 PDF 文档中的注释意味着注释将成为文档内容的一部分，并且无法再编辑或删除。当您想确保注释得到保留并且不会被意外更改时，这很有用。

在本教程中，我们将讨论如何使用 Aspose.PDF for .NET 来平整 PDF 文档中的注释。我们将提供有关如何执行此操作的分步指南以及示例源代码。

## 步骤 1：创建一个新的 C# 控制台应用程序
首先，在 Visual Studio 中创建一个新的 C# 控制台应用程序。您可以随意命名。创建项目后，您需要添加对 Aspose.PDF for .NET 库的引用。

## 第 2 步：导入 Aspose.PDF 命名空间
在 C# 文件顶部添加以下代码行以导入 Aspose.PDF 命名空间：

```csharp
using Aspose.Pdf;
```

## 步骤 3：打开 PDF 文档
打开要扁平化的 PDF 文档：

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 步骤 4：展平注释
扁平化PDF文档中的注释：

```csharp
foreach (var page in pdfDocument.Pages)
{
    foreach (var annotation in page.Annotations)
    {
        annotation.Flatten();
    }
}
```

## 步骤 5：保存更新后的文档
保存更新后的文档：

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("\nFlattened annotation successfully.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 进行 Flatten Annotation 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
//扁平化注释
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
在本教程中，我们讨论了如何使用 Aspose.Pdf for .NET 平铺 PDF 文档中的注释。平铺 PDF 文档中的注释是一项有用的功能，可确保注释得到保留并且不会被意外更改。Aspose.Pdf for .NET 提供了一个简单易用的 API 来处理 PDF 文档，包括平铺注释。 

### PDF 文件中扁平化注释的常见问题解答

#### 问：PDF 文档中的注释是什么？

答：PDF 文档中的注释是可以添加到文档中的附加元素或注释，用于提供额外的信息或交互性。注释可以包括文本、图像、链接、评论等。

#### 问：为什么我要展平 PDF 文档中的注释？

答：当您想要确保注释成为文档内容的一部分并且无法编辑或删除时，扁平化 PDF 文档中的注释非常有用。它有助于将注释保留为文档的一部分。

#### 问：我可以选择性地扁平化 PDF 文档中的注释吗？

答：是的，您可以使用 Aspose.PDF for .NET 选择性地扁平化 PDF 文档中的注释。您可以选择扁平化特定页面上或整个文档中的特定注释或所有注释。