---
title: 在 PDF 文件中设置文件信息
linktitle: 在 PDF 文件中设置文件信息
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南，了解如何使用 Aspose.PDF for .NET 在 PDF 文件中设置文件信息。
type: docs
weight: 310
url: /zh/net/programming-with-document/setfileinfo/
---
如果您正在开发的项目需要使用 Aspose.PDF for .NET 管理 PDF 文件，您可能想要利用的功能之一是为 PDF 文档设置文件信息的功能。文件信息包括各种详细信息，例如作者、创建日期、关键字、修改日期、主题和标题。本指南将引导您完成使用 C# 源代码和 Aspose.PDF for .NET 设置 PDF 文档的文件信息的过程。

## 使用 Aspose.PDF for .NET 设置文件信息的分步指南

1. 在 Visual Studio IDE 中创建一个新的 C# 项目。
2. 在项目中添加对 Aspose.PDF for .NET 库的引用。
3. 通过提供要修改其文件信息的 PDF 文件的路径来创建新的 PDF 文档对象。

## 步骤1：设置文档目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：打开 PDF 文档

```csharp
//打开文档
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## 步骤3：使用DocumentInfo对象访问PDF文档的文件信息。

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## 步骤 4：使用 DocumentInfo 对象的属性设置所需的文件信息值。

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## 步骤5：将更新后的PDF文档保存到指定位置。

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## 步骤6：验证文件信息是否已成功更新。

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

您已使用 Aspose.PDF for .NET 成功设置 PDF 文档的文件信息。

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

总之，Aspose.PDF for .NET 提供了一种简单有效的方法来设置 PDF 文档的文件信息。通过执行上述步骤，您可以使用 C# 源代码轻松地为 PDF 文档设置所需的文件信息值。

### PDF 文件中设置文件信息的常见问题解答

#### 问：我可以设置示例中未提及的其他文件信息属性吗？

答：是的，您可以使用以下命令设置其他文件信息属性`DocumentInfo`Aspose.PDF for .NET 中的对象。这`DocumentInfo`类提供了各种属性，允许您设置附加信息，例如生产者、版本和自定义属性。

#### 问：是否可以从现有 PDF 文档中检索文件信息？

答：是的，您可以使用 Aspose.PDF for .NET 从现有 PDF 文档中检索文件信息。为此，您可以使用`DocumentInfo`对象访问文件信息属性并读取 PDF 文档中存储的信息。

#### 问：设置文件信息会修改原始PDF文档吗？

答：不会，使用 Aspose.PDF for .NET 设置文件信息不会修改原始 PDF 文档。相反，它会使用更新的文件信息创建一个新的 PDF 文档。原始 PDF 文档保持不变。