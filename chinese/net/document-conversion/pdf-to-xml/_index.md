---
title: PDF 到 XML
linktitle: PDF 到 XML
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 PDF 转换为 XML 的分步指南。
type: docs
weight: 210
url: /zh/net/document-conversion/pdf-to-xml/
---

在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 将 PDF 文件转换为 XML 格式的过程。 XML（可扩展标记语言）是一种用于存储和交换结构化信息的数据格式。按照以下步骤，您将能够将 PDF 文件转换为 XML 格式。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- .NET 的 Aspose.PDF 库安装在您的系统上。
- 开发环境，例如 Visual Studio。

## 第 1 步：加载 PDF 文档
在此步骤中，我们将使用 Aspose.PDF for .NET 加载源 PDF 文件。请遵循以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载 PDF 文档
Document doc = new Document(dataDir + "input.pdf");
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用您的 PDF 文件所在的实际目录。

## 第 2 步：保存生成的 XML 文件
现在我们将以 XML 格式保存转换后的 PDF 文件。使用以下代码：

```csharp
//将输出保存为 XML
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

上面的代码将转换后的 PDF 文件保存为 XML 格式，文件名`"PDFToXML_out.xml"`.

### 使用 Aspose.Words for .NET 的 PDF 到 XML 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";            
//加载源 PDF 文件
Document doc = new Document(dataDir + "input.pdf");
//以 XML 格式保存输出
doc.Save(dataDir + "PDFToXML_out.xml", SaveFormat.MobiXml);
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 将 PDF 文件转换为 XML 的分步过程。按照上述说明，您现在应该能够将 PDF 文件转换为 XML 格式。当您想要从 PDF 文件中提取结构化内容并将其处理成 XML 格式以供以后使用时，此功能非常有用。