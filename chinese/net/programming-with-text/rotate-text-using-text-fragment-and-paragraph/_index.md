---
title: 使用文本片段和段落旋转文本
linktitle: 使用文本片段和段落旋转文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中使用文本片段和段落来旋转文本。
type: docs
weight: 400
url: /zh/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---

本教程解释了如何使用 Aspose.PDF for .NET 来使用文本片段和段落来旋转文本。提供的 C# 源代码逐步演示了该过程。

## 先决条件

在继续本教程之前，请确保您具有以下内容：

- C# 编程语言的基础知识。
- 安装了 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它或使用 NuGet 将其安装到您的项目中。

## 第 1 步：设置项目

首先在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目，并添加对 Aspose.PDF for .NET 库的引用。

## 第 2 步：导入必要的命名空间

在 C# 文件的开头添加以下 using 指令以导入所需的命名空间：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第 3 步：创建 PDF 文档

初始化`Document`对象来创建一个新的 PDF 文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

确保更换`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

## 第 4 步：添加页面

使用`Pages.Add()`方法：

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## 第 5 步：创建文本片段

创建多个`TextFragment`对象，设置其文本和属性，并指定旋转角度：

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

根据需要调整文本、旋转角度和其他属性。

## 第 6 步：向页面添加文本片段

将创建的文本片段添加到页面，方法是将它们附加到`Paragraphs`收藏：

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## 步骤 7：保存 PDF 文档

将修改后的 PDF 文档保存到一个文件中，使用`Save`方法：

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

确保更换`"TextFragmentTests_Rotated3_out.pdf"`使用所需的输出文件名。

### 使用 Aspose.PDF for .NET 使用文本片段和段落旋转文本的示例源代码 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
//初始化文档对象
Document pdfDocument = new Document();
//获取特定页面
Page pdfPage = (Page)pdfDocument.Pages.Add();
//创建文本片段
TextFragment textFragment1 = new TextFragment("main text");
//设置文本属性
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//创建文本片段
TextFragment textFragment2 = new TextFragment("rotated text");
//设置文本属性
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//设置旋转
textFragment2.TextState.Rotation = 315;
//创建文本片段
TextFragment textFragment3 = new TextFragment("rotated text");
//设置文本属性
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
//设置旋转
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
//保存文档
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## 结论

恭喜！您已经成功学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中使用文本片段和段落来旋转文本。本教程提供了从创建文档到保存修改后版本的分步指南。您现在可以将此代码合并到您自己的 C# 项目中，以操作 PDF 文件中的文本旋转。