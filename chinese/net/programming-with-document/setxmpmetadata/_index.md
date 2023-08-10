---
title: 在 PDF 文件中设置 XMPMetadata
linktitle: 在 PDF 文件中设置 XMPMetadata
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中设置 XMPMetadata。请遵循此分步指南。
type: docs
weight: 330
url: /zh/net/programming-with-document/setxmpmetadata/
---
在本文中，我们将提供有关如何使用 Aspose.PDF for .NET 在 PDF 文件中设置 XMP 元数据的分步指南。我们将在文章末尾提供完整的示例源代码。

## 第一步：设置文档目录路径

在开始之前，我们需要设置 PDF 文档所在目录的路径。我们将该路径存储在名为“dataDir”的变量中。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

确保更换`YOUR DOCUMENT DIRECTORY`与 PDF 文件的实际路径。

## 第 2 步：打开 PDF 文件

第一步是打开要为其设置 XMP 元数据的 PDF 文件。为此，您需要创建一个新的`Document`对象并传入 PDF 文件的路径。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## 步骤 3：设置 XMP 元数据属性

现在您已打开 PDF 文件，您可以开始设置 XMP 元数据属性。您设置的属性将取决于您的具体需求，但以下是您可能想要设置的一些常见属性：

- `xmp:CreateDate`：PDF 文件的创建日期。
- `xmp:Nickname`：PDF 文件的昵称或别名。
- `xmp:CustomProperty`：具有您指定值的自定义属性。

要设置这些属性，您可以使用`Metadata`的财产`Document`目的。这是一个例子：

```csharp
//设置属性
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

在本教程中，我们将创建日期设置为当前日期和时间，将昵称设置为“昵称”，将自定义属性设置为“自定义值”。您可以将这些值替换为您自己的值。

## 步骤 4：保存 PDF 文件

设置 XMP 元数据属性后，您需要保存 PDF 文件。为此，您可以使用`Save`的方法`Document`对象并传入要保存更新的 PDF 文件的路径。

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
//保存文档
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 设置 XMPMetadata 的示例源代码

以下是使用 Aspose.PDF for .NET 设置 XMPMetadata 的完整示例源代码：

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

## 结论

Aspose.PDF for .NET 提供了一种在 PDF 文件中设置 XMP 元数据的简单方法，使您能够向文档添加描述性信息和属性。上面提供的分步指南向您展示了如何使用 C# 源代码设置各种 XMP 元数据属性。此外，您可以自定义 XMP 元数据以满足您的特定需求和业务要求。借助 Aspose.PDF for .NET，管理 PDF 元数据变得高效，并可以更好地组织和搜索 PDF 文档。

### 在 PDF 文件中设置 XMP 元数据的常见问题解答

#### 问：PDF 文件中的 XMP 元数据是什么？为什么它很重要？

答：XMP（可扩展元数据平台）是一种在各种文件格式（包括 PDF）中嵌入元数据的标准。 PDF 文件中的 XMP 元数据允许您向文档添加描述性信息和属性，例如创建日期、作者、标题、关键字和自定义属性。它对于更好地组织、搜索和归档 PDF 文档至关重要。

#### 问：除了示例中提到的属性之外，我还可以设置其他 XMP 元数据属性吗？

答：是的，您可以根据您的具体要求设置各种 XMP 元数据属性。一些常见的属性包括`dc:title`（文件名），`dc:creator` （文档创建者），`dc:description` （文档说明），`pdf:Keywords` （文档关键字）等等。 XMP 规范提供了各种标准命名空间和自定义命名空间，用于设置不同类型的元数据。

#### 问：是否可以从现有 PDF 文件中检索和读取 XMP 元数据？

答：是的，Aspose.PDF for .NET 提供了从现有 PDF 文件读取和检索 XMP 元数据的功能。您可以使用`Metadata`的财产`Document`类来访问 XMP 元数据并检索特定属性的值。