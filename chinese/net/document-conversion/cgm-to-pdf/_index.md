---
title: CGM转PDF
linktitle: CGM转PDF
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松将 CGM 文件转换为 PDF。
type: docs
weight: 20
url: /zh/net/document-conversion/cgm-to-pdf/
---

在本教程中，我们将逐步指导您使用 Aspose.PDF for .NET 将 CGM 转换为 PDF。我们将解释所提供的 C# 源代码并提供分步说明，以帮助您轻松地进行操作。

## 介绍

将 CGM 文件转换为 PDF 后，您可以普遍共享和查看您的技术图纸。使用 Aspose.PDF for .NET，您可以轻松执行此转换并获得高质量的 PDF 文件。

## 环境设置

在您开始之前，请确保您已经配置了您的开发环境以使用 Aspose.PDF for .NET。请按照以下步骤操作：

1. 安装 Visual Studio 或其他与 C# 开发兼容的 IDE。
2. 创建一个新的 C# 项目。
3. 通过 NuGet 安装 Aspose.PDF for .NET 包以添加必要的依赖项。

## 将 CGM 文件转换为 PDF

要将 CGM 文件转换为 PDF，请按照下列步骤操作：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//使用 CGMLoadOption 实例化 LoadOption 对象
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
//实例化一个文档对象
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
//保存生成的 PDF 文档
doc.Save(dataDir + "TECHDRAW_out.pdf");
```

在上面的代码中，一定要替换`"YOUR DOCUMENTS DIRECTORY"`使用要转换的 CGM 文件所在目录的实际路径。此代码使用`CgmLoadOptions`类，然后使用`Document`目的。最后，保存生成的 PDF 文档。

### 使用 Aspose.PDF for .NET 的 CGM 到 PDF 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//使用 CGMLoadOption 实例化 LoadOption 对象
Aspose.Pdf.CgmLoadOptions cgmload = new Aspose.Pdf.CgmLoadOptions();
//实例化文档对象
Document doc = new Document(dataDir + "CGMToPDF.CGM", cgmload);
//保存生成的 PDF 文档
doc.Save(dataDir+ "TECHDRAW_out.pdf");
```

## 结论

恭喜！现在您知道了如何使用 Aspose.PDF for .NET 将 CGM 文件转换为 PDF。我们已经完成了该过程的每一步，从初始化 CGM 加载选项到保存生成的 PDF 文档。使用提供的代码示例将此功能集成到您自己的项目中。试用 Aspose.PDF for .NET 并发现它为操作 PDF 文件提供的扩展可能性。
