---
title: 更新维度
linktitle: 更新维度
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 更新 PDF 页面尺寸的分步指南。根据您的需要检查尺寸。
type: docs
weight: 150
url: /zh/net/programming-with-pdf-pages/update-dimensions/
---
在本教程中，我们将逐步引导您使用 Aspose.PDF for .NET 更新 PDF 文档中的页面尺寸。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，以帮助您了解并在您自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.PDF for .NET 更改 PDF 文档中的页面尺寸。

## 先决条件
在开始之前，请确保您具备以下条件：

- C#编程语言的基本知识
- 安装在您的开发环境中的 Aspose.PDF for .NET

## 第一步：定义文档目录
首先，您需要设置文档目录的路径。这是您要保存已编辑 PDF 文档的位置。用适当的路径替换“您的文档目录”。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：打开 PDF 文档
然后您可以使用打开现有的 PDF 文档`Document`Aspose.PDF 类。请务必指定正确的文档路径。

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 第 3 步：获取页面集合
现在您可以使用访问 PDF 文档的页面集合`Pages`的财产`Document`班级。

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 第 4 步：获取特定页面
然后，您可以使用集合中页面的索引来选择文档的特定页面。在此示例中，我们使用第二页（索引 1）。

```csharp
Page pdfPage = pageCollection[1];
```

## 第 5 步：定义新的页面尺寸
现在您可以使用`SetPageSize()`的方法`Page`目的。在此示例中，我们将页面尺寸设置为 A4（11.7 x 8.3 英寸），并转换为磅（1 英寸 = 72 磅）。

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## 第 6 步：保存更新后的文档
最后，您可以使用`Save()`的方法`Document`班级。请务必指定正确的路径和文件名。

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 更新维度的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
//获取页面集合
PageCollection pageCollection = pdfDocument.Pages;
//获取特定页面
Page pdfPage = pageCollection[1];
//将页面大小设置为 A4（11.7 x 8.3 英寸），在 Aspose.Pdf 中，1 英寸 = 72 磅
//所以以点为单位的 A4 尺寸将是 (842.4, 597.6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
//保存更新的文档
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 更新 PDF 文档中页面的尺寸。按照此分步指南，您可以根据需要轻松更改 PDF 文档中页面的尺寸。 Aspose.PDF 提供了强大而灵活的 API，用于处理 PDF 文件和执行各种操作，包括更改页面尺寸。有了这些知识，您就可以控制和自定义 PDF 页面的尺寸以满足您的特定需求。
