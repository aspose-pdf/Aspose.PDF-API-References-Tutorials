---
title: 添加文字戳记
linktitle: 添加文字戳记
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 轻松地为您的 PDF 文档添加文本标记。
type: docs
weight: 50
url: /zh/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
在本教程中，我们将逐步向您介绍如何使用 Aspose.PDF for .NET 向 PDF 文档添加文本戳记。我们将向您展示如何使用提供的 C# 源代码将自定义文本标记添加到 PDF 文档的特定页面。

## 第 1 步：设置环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 在您的项目中下载并引用了用于 .NET 的 Aspose.PDF 库。

## 第 2 步：加载 PDF 文档

第一步是将现有的 PDF 文档加载到您的项目中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

请务必将“您的文档目录”替换为您的 PDF 文档所在目录的实际路径。

## 第 3 步：创建文本缓冲区

现在您已经上传了 PDF 文档，您可以创建要添加的文本图章。方法如下：

```csharp
//创建文本缓冲区
TextStamp textStamp = new TextStamp("Example Stamp");
```

上面的代码创建了一个包含指定文本的新文本缓冲区。

## 第 4 步：配置文本标记属性

在将文本图章添加到 PDF 文档之前，您可以配置图章的各种属性，例如背景、位置、旋转、字体、大小等。方法如下：

```csharp
//配置文本缓冲区属性
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

您可以根据需要调整这些属性。

## 第 5 步：将文本图章添加到 PDF

现在文本戳已准备就绪，您可以将其添加到 PDF 文档的特定页面。就是这样：

```csharp
//将文本缓冲区添加到特定页面
pdfDocument.Pages[1].AddStamp(textStamp);
```

上面的代码将文本标记添加到 PDF 文档的第一页。如果需要，您可以指定另一个页面。

## 第 6 步：保存输出文档

添加文本图章后，您可以保存编辑的 PDF 文档。就是这样：

```csharp
//保存输出文件
pdfDocument.Save(dataDir);
```

上面的代码将修改后的 PDF 文档保存在指定的目录中。

### 使用 Aspose.PDF for .NET 添加文本标记的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

//创建文本图章
TextStamp textStamp = new TextStamp("Sample Stamp");

//设置图章是否为背景
textStamp.Background = true;

//设置原点
textStamp.XIndent = 100;
textStamp.YIndent = 100;

//旋转图章
textStamp.Rotate = Rotation.on90;

//设置文本属性
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

//在特定页面上添加图章
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

//保存输出文件
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## 结论

恭喜！您已经学习了如何使用 Aspose.PDF for .NET 添加文本标记。现在您可以将这些知识应用到您自己的项目中，为 PDF 文档添加自定义文本图章。
