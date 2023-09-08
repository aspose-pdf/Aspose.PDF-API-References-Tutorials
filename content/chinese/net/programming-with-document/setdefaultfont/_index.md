---
title: 在 PDF 文件中设置默认字体
linktitle: 在 PDF 文件中设置默认字体
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南，了解如何使用 Aspose.PDF for .NET 在 PDF 文件中设置默认字体。
type: docs
weight: 280
url: /zh/net/programming-with-document/setdefaultfont/
---
如果您在 .NET 中处理 PDF 文档，则可能会遇到以下问题：PDF 中使用的字体在查看或打印 PDF 的系统上不可用。这可能会导致文本显示不正确或根本不显示。 Aspose.PDF for .NET 允许您为文档设置默认字体，从而提供了此问题的解决方案。在此示例中，如何使用 Aspose.PDF for .NET 设置默认字体。

## 第一步：设置文档目录路径

我们需要设置PDF文档所在目录的路径。我们将该路径存储在名为“dataDir”的变量中。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载 PDF 文档

我们首先加载缺少字体的现有 PDF 文档。在此示例中，我们假设 PDF 文档位于由`dataDir`多变的。

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    //代码放在这里
}
```

## 第三步：设置默认字体

接下来，我们将使用以下命令设置 PDF 文档的默认字体`PdfSaveOptions`班级。在此示例中，我们将默认字体设置为“Arial”。

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## 步骤 4：保存更新后的文档

最后，我们将更新的文档保存到新文件中。在此示例中，我们将更新的文档保存到与输入文件位于同一目录中的名为“output_out.pdf”的文件中。

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### 使用 Aspose.PDF for .NET 设置默认字体的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加载缺少字体的现有 PDF 文档
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	//指定默认字体名称
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## 结论

使用 Aspose.PDF for .NET 在 PDF 文档中设置默认字体是一种简单而有效的方法，可以确保文本正确显示，即使原始字体不可用。通过遵循分步指南并使用提供的 C# 源代码，开发人员可以轻松设置默认字体并创建 PDF，从而在不同环境中提供一致且可靠的查看体验。当在可能安装了不同字体集的各种系统上查看或打印 PDF 时，此功能特别有用。

### PDF 文件中设置默认字体的常见问题解答

#### 问：为什么在 PDF 文档中设置默认字体很重要？

答：在 PDF 文档中设置默认字体非常重要，因为即使在查看或打印 PDF 的系统上没有原始字体，它也能确保文本正确显示。它有助于防止文本丢失或乱码等问题，确保一致且可靠的观看体验。

#### 问：我可以使用 Aspose.PDF for .NET 选择任何字体作为默认字体吗？

答：是的，您可以使用 Aspose.PDF for .NET 选择系统上可用的任何字体作为默认字体。只需在中指定字体名称即可`DefaultFontName`的财产`PdfSaveOptions`班级。

#### 问：如果系统上没有指定的默认字体，会发生什么情况？

答：如果系统上没有指定的默认字体，PDF 查看器将使用后备字体来显示文本。建议选择常用字体，如 Arial 或 Times New Roman，以确保不同系统之间的兼容性。