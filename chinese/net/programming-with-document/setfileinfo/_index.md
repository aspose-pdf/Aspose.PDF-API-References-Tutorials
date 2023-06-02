---
title: 设置文件信息
linktitle: 设置文件信息
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南了解如何使用 Aspose.PDF for .NET 在您的 PDF 文档中设置文件信息。
type: docs
weight: 310
url: /zh/net/programming-with-document/setfileinfo/
---
如果您正在处理需要使用 Aspose.PDF for .NET 管理 PDF 文件的项目，您可能想要使用的功能之一是能够为 PDF 文档设置文件信息。文件信息包括作者、创建日期、关键字、修改日期、主题和标题等各种详细信息。本指南将引导您完成使用 C# 源代码和 Aspose.PDF for .NET 为 PDF 文档设置文件信息的过程。

## 使用 Aspose.PDF for .NET 设置文件信息的分步指南

1. 在 Visual Studio IDE 中创建一个新的 C# 项目。
2. 在您的项目中添加对 Aspose.PDF for .NET 库的引用。
3. 通过提供您要修改其文件信息的 PDF 文件的路径来创建新的 PDF 文档对象。

## 第 1 步：设置文档目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：打开 PDF 文档

```csharp
//打开文档
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## 第三步：使用DocumentInfo对象访问PDF文档的文件信息。

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## 第 4 步：使用 DocumentInfo 对象的属性设置所需的文件信息值。

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## 第五步：将更新后的PDF文档保存到指定位置。

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## 第六步：验证文件信息是否更新成功。

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

您已经成功地使用 Aspose.PDF for .NET 为 PDF 文档设置了文件信息。

### 使用 Aspose.PDF for .NET 设置文件信息的示例源代码


```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

//指定文档信息
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
//保存输出文档
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## 结论

总之，Aspose.PDF for .NET 提供了一种简单有效的方式来设置PDF 文档的文件信息。按照上述步骤，您可以使用 C# 源代码轻松地为您的 PDF 文档设置所需的文件信息值。