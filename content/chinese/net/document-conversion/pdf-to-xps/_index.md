---
title: PDF 到 XPS
linktitle: PDF 到 XPS
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 PDF 转换为 XPS 的分步指南。
type: docs
weight: 220
url: /zh/net/document-conversion/pdf-to-xps/
---
在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 将 PDF 文件转换为 XPS（XML 纸张规范）格式的过程。 XPS 格式是一种基于 XML 的文件格式，用于以电子方式表示文档。通过执行以下步骤，您将能够将 PDF 文件转换为 XPS 格式。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- 您的系统上安装了适用于 .NET 的 Aspose.PDF 库。
- 开发环境，例如 Visual Studio。

## 第 1 步：加载 PDF 文档
在此步骤中，我们将使用 Aspose.PDF for .NET 加载源 PDF 文件。请按照以下代码操作：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载 PDF 文档
Document pdfDocument = new Document(dataDir + "input.pdf");
```

一定要更换`"YOUR DOCUMENTS DIRECTORY"`与您的 PDF 文件所在的实际目录。

## 步骤 2：实例化 XPS 保存选项
加载 PDF 文件后，我们将实例化 XPS 保存选项。使用以下代码：

```csharp
//实例化 XPS 保存选项
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## 步骤 3：保存生成的 XPS 文件
现在我们将转换后的 PDF 文件保存为 XPS 格式。使用以下代码：

```csharp
//保存 XPS 文档
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

上面的代码将转换后的PDF文件保存为XPS格式，文件名为`"PDFToXPS_out.xps"`.


### 使用 Aspose.PDF for .NET 将 PDF 转换为 XPS 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载 PDF 文档
Document pdfDocument = new Document(dataDir + "input.pdf");

//实例化 XPS 保存选项
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

//保存 XPS 文档
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 将 PDF 文件转换为 XPS 格式的分步过程。按照上述说明操作，您现在应该能够将 PDF 文件转换为 XPS 格式。当您想要查看或打印 XPS 格式的 PDF 文档时，此功能非常有用。

### 常见问题解答

#### 问：XPS格式是否适合跨平台兼容？

答：XPS 格式是一种基于 XML 的文件格式，与平台无关，可以在各种操作系统和设备上查看。默认情况下，Windows 平台支持 XPS 文件，某些第三方应用程序和查看器可能适用于其他平台。

#### 问：Aspose.PDF for .NET 在 XPS 转换过程中可以处理具有多个页面和图像的复杂 PDF 文件吗？

答：是的，Aspose.PDF for .NET 可以在 XPS 转换过程中处理具有多个页面和图像的复杂 PDF 文件。它在将 PDF 转换为 XPS 格式时准确保留 PDF 的布局、图像和文本内容。

#### 问：是否可以在 XPS 转换过程中指定其他设置或选项？

答：是的，Aspose.PDF for .NET 提供了可以在 XPS 转换过程中自定义的各种选项和设置。您可以使用以下命令控制图像压缩、字体嵌入和其他设置`XpsSaveOptions`班级。

#### 问：能否使用 Aspose.PDF for .NET 将受密码保护的 PDF 转换为 XPS 格式？

答：是的，Aspose.PDF for .NET 支持将受密码保护的 PDF 转换为 XPS 格式。加载受密码保护的 PDF 时，您可以使用`Document`类构造函数或通过设置`Password`加载 PDF 之前的属性。