---
title: 设置 XMP 元数据
linktitle: 设置 XMP 元数据
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中设置 XMPMetadata。请遵循此分步指南。
type: docs
weight: 330
url: /zh/net/programming-with-document/setxmpmetadata/
---
在本文中，我们将提供有关如何使用 Aspose.PDF for .NET 在 PDF 文件中设置 XMP 元数据的分步指南。我们将在文章末尾提供完整的示例源代码。

## 第一步：设置文档目录路径

在我们开始之前，我们需要将路径设置为我们的 PDF 文档所在的目录。我们将把这个路径存储在一个名为“dataDir”的变量中。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

确保更换`YOUR DOCUMENT DIRECTORY`与您的 PDF 文件的实际路径。

## 第 2 步：打开 PDF 文件

第一步是打开要为其设置 XMP 元数据的 PDF 文件。为此，您需要创建一个新的`Document`对象并传入 PDF 文件的路径。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## 第 3 步：设置 XMP 元数据属性

现在您已打开 PDF 文件，您可以开始设置 XMP 元数据属性。您设置的属性将取决于您的特定需求，但以下是您可能想要设置的一些常见属性：

- `xmp:CreateDate`：PDF 文件的创建日期。
- `xmp:Nickname`：PDF 文件的昵称或别名。
- `xmp:CustomProperty`：具有您指定的值的自定义属性。

要设置这些属性，您可以使用`Metadata`的财产`Document`目的。这是一个例子：

```csharp
//设置属性
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

在本教程中，我们将创建日期设置为当前日期和时间，昵称设置为“昵称”，自定义属性设置为“自定义值”。您可以用自己的值替换这些值。

## 第 4 步：保存 PDF 文件

设置 XMP 元数据属性后，您需要保存 PDF 文件。为此，您可以使用`Save`的方法`Document`对象并传入要保存更新的 PDF 文件的路径。

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
//保存文档
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 设置 XMPMetadata 的示例源代码

下面是使用 Aspose.PDF for .NET 设置 XMPMetadata 的完整示例源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//打开文档
	Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

	//设置属性
	pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
	pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
	pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

	dataDir = dataDir + "SetXMPMetadata_out.pdf";
	//保存文档
	pdfDocument.Save(dataDir);
	
	Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);

```
