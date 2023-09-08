---
title: MHT 转 PDF
linktitle: MHT 转 PDF
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 MHT 转换为 PDF 的分步指南。
type: docs
weight: 70
url: /zh/net/document-conversion/mht-to-pdf/
---
在本教程中，我们将指导您完成使用 Aspose.PDF for .NET 将 MHT 文件转换为 PDF 的过程。 MHT（MIME HTML）是一种用于保存完整网页的格式，包括图像和相关内容。按照以下步骤，您将能够将 MHT 文件转换为 PDF 格式。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- 您的系统上安装了适用于 .NET 的 Aspose.PDF 库。
- 开发环境，例如 Visual Studio。

## 第1步：加载MHT文件
在此步骤中，我们将使用 Aspose.PDF for .NET 加载 MHT 文件。请按照以下代码操作：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

//加载文档
Document document = new Document(dataDir + "test.mht", options);
```

一定要更换`"YOUR DOCUMENTS DIRECTORY"`与 MHT 文件所在的实际目录。

## 步骤 2: MHT 到 PDF 转换
加载MHT文件后，我们可以继续转换为PDF。使用以下代码：

```csharp
//将输出另存为 PDF 文档
document.Save(dataDir + "MHTToPDF_out.pdf");
```

上面的代码将MHT文件转换为PDF格式并将其另存为文件名`"MHTToPDF_out.pdf"`.

### 使用 Aspose.PDF for .NET 将 MHT 转换为 PDF 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
//加载文档
Document document = new Document(dataDir  + "test.mht", options);
//将输出另存为 PDF 文档
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 将 MHT 文件转换为 PDF 的分步过程。按照上述说明操作，您现在应该能够将 MHT 文件转换为 PDF 格式。当您需要将整个网页转换为 PDF 文档时，此功能非常有用。

### 常见问题解答

#### 问：Aspose.PDF for .NET 支持将嵌入图像的 MHT 文件转换为 PDF 吗？

答：是的，Aspose.PDF for .NET 支持将嵌入图像的 MHT 文件转换为 PDF。该库可以处理完整的网页内容，包括图像和相关资源，并将其转换为 PDF 文档。

#### 问：我可以在 MHT 到 PDF 转换过程中自定义 PDF 输出吗？

答：是的，Aspose.PDF for .NET 提供了各种选项来在 MHT 到 PDF 转换过程中自定义 PDF 输出。您可以设置页面大小、方向、边距等属性来控制生成的 PDF 文档的外观。

#### 问：Aspose.PDF for .NET 是否会在 PDF 输出中保留原始 MHT 文件的超链接和格式？

答：是的，Aspose.PDF for .NET 会在 PDF 输出中保留原始 MHT 文件的超链接和格式。该库确保转换后的 PDF 保留与源 MHT 文件相同的布局和内容。

#### 问：我可以使用 Aspose.PDF for .NET 将多个 MHT 文件转换为单独的 PDF 文档吗？

答：是的，您可以使用 Aspose.PDF for .NET 将多个 MHT 文件转换为单独的 PDF 文档。只需加载每个 MHT 文件并将其保存为具有唯一文件名的单独 PDF 文档即可。