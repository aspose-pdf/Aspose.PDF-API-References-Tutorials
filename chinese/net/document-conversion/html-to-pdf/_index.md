---
title: HTML 到 PDF
linktitle: HTML 到 PDF
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 HTML 转换为 PDF 的分步指南。
type: docs
weight: 50
url: /zh/net/document-conversion/html-to-pdf/
---

在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 将 HTML 文件转换为 PDF 的过程。 HTML（超文本标记语言）是一种用于构建和呈现 Web 内容的标记语言。按照以下步骤，您将能够将 HTML 文件转换为 PDF 格式。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- .NET 的 Aspose.PDF 库安装在您的系统上。
- 开发环境，例如 Visual Studio。

## 第 1 步：加载 HTML 文件
在此步骤中，我们将使用 Aspose.PDF for .NET 加载 HTML 文件。请遵循以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

HtmlLoadOptions options = new HtmlLoadOptions();
options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用您的 HTML 文件所在的实际目录。

## 第 2 步：HTML 加载选项
现在我们已经加载了 HTML 文件，我们可以指定特定的加载选项。使用以下代码：

```csharp
options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);
```

上面的代码告诉 Aspose.PDF 对外部资源（例如图像）使用自定义加载策略。您可以自定义此策略以满足您的需要。

## 第 3 步：HTML 到 PDF 的转换
加载 HTML 文件并指定加载选项后，我们可以继续转换为 PDF。使用以下代码：

```csharp
pdfDocument.Save("HTMLToPDF_out.pdf");
```

### 使用 Aspose.Words for .NET 将 HTML 转换为 PDF 的示例源代码

```csharp
try
{
	
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	HtmlLoadOptions options = new HtmlLoadOptions();
	options.CustomLoaderOfExternalResources = new LoadOptions.ResourceLoadingStrategy(SamePictureLoader);

	Document pdfDocument = new Document(dataDir + "HTMLToPDF.html", options);
	pdfDocument.Save("HTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论
在本教程中，我们逐步介绍了该过程。使用 Aspose.PDF for .NET 将 HTML 文件转换为 PDF 的步骤。按照上述说明，您现在应该能够将 HTML 文件转换为 PDF 格式。当您需要从 HTML 内容生成 PDF 文档时，此功能非常有用。

