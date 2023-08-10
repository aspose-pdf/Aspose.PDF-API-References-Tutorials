---
title: 浮动框内容的文本对齐
linktitle: 浮动框内容的文本对齐
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 对齐 PDF 文档中浮动框中的文本。
type: docs
weight: 520
url: /zh/net/programming-with-text/text-alignment-for-floating-box-contents/
---

本教程介绍如何使用 Aspose.PDF for .NET 对齐 PDF 文档中浮动框中的文本。提供的 C# 源代码逐步演示了该过程。

## 先决条件

在继续学习本教程之前，请确保您具备以下条件：

- C# 编程语言的基础知识。
- 安装了 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它或使用 NuGet 将其安装到您的项目中。

## 第 1 步：设置项目

首先在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目，并添加对 Aspose.PDF for .NET 库的引用。

## 第2步：导入必要的命名空间

在 C# 文件的开头添加以下 using 指令以导入所需的命名空间：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第三步：设置文档目录路径

使用以下命令设置文档目录的路径`dataDir`多变的：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

## 第四步：创建一个新文档

创建一个新的`Document`目的：

```csharp
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

## 第 5 步：使用文本片段创建浮动框

创建多个`FloatingBox`具有不同垂直对齐和水平对齐的对象：

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);

Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);

Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

修改文本和样式`TextFragment`所需的对象。

## 步骤 6：保存 PDF 文档

保存修改后的PDF文档：

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

确保更换`"FloatingBox_alignment_review_out.pdf"`与所需的输出文件名。

### 使用 Aspose.PDF for .NET 实现浮动框内容文本对齐的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

## 结论

恭喜！您已成功学习如何使用 Aspose.PDF for .NET 在 PDF 文档中的浮动框中对齐文本。本教程提供了从设置项目到保存修改后的文档的分步指南。现在，您可以将此代码合并到您自己的 C# 项目中，以自定义 PDF 文件中浮动框中文本的对齐方式。