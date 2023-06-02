---
title: MHT转PDF
linktitle: MHT转PDF
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
- .NET 的 Aspose.PDF 库安装在您的系统上。
- 开发环境，例如 Visual Studio。

## 第 1 步：加载 MHT 文件
在此步骤中，我们将使用 Aspose.PDF for .NET 加载 MHT 文件。请遵循以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

MhtLoadOptions options = new MhtLoadOptions();

//装入文档
Document document = new Document(dataDir + "test.mht", options);
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用 MHT 文件所在的实际目录。

## 第 2 步：MHT 到 PDF 的转换
加载 MHT 文件后，我们可以继续转换为 PDF。使用以下代码：

```csharp
//将输出另存为 PDF 文档
document.Save(dataDir + "MHTToPDF_out.pdf");
```

上面的代码将 MHT 文件转换为 PDF 格式并将其保存为文件名`"MHTToPDF_out.pdf"`.

### 使用 Aspose.Words for .NET 的 MHT 到 PDF 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
MhtLoadOptions options = new MhtLoadOptions();
//载入文件
Document document = new Document(dataDir  + "test.mht", options);
//将输出另存为 PDF 文档
document.Save(dataDir + "MHTToPDF_out.pdf");
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 将 MHT 文件转换为 PDF 的分步过程。按照上述说明，您现在应该能够将 MHT 文件转换为 PDF 格式。当您需要将整个网页转换为 PDF 文档时，此功能非常有用。