---
title: 文本和图像作为段落
linktitle: 文本和图像作为段落
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中添加文本和图像作为内联段落。
type: docs
weight: 530
url: /zh/net/programming-with-text/text-and-image-as-paragraph/
---

本教程介绍如何使用 Aspose.PDF for .NET 在 PDF 文档中添加文本和图像作为内联段落。提供的 C# 源代码逐步演示了该过程。

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
using Aspose.Pdf.Drawing;
```

## 第三步：设置文档目录路径

使用以下命令设置文档目录的路径`dataDir`多变的：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

## 第 4 步：创建新文档和页面

创建一个新的`Document`对象并将页面添加到其页面集合中：

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 第 5 步：创建 TextFragment 并将其添加为段落

创建一个`TextFragment`对象并将其添加到页面的段落集合中：

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## 步骤 6：添加图像作为内嵌段落

创建一个`Aspose.Pdf.Image`对象并将其设置为内联段落，以便它出现在上一个段落之后：

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; //可选：设置图像高度
image.FixWidth = 100; //可选：设置图像宽度
page.Paragraphs.Add(image);
```

代替`"aspose-logo.jpg"`与实际的图像文件名，并根据需要调整可选的图像高度和宽度。

## 第 7 步：添加另一个 TextFragment 作为内嵌段落

重新初始化`TextFragment`具有不同内容的对象并将其添加为内联段落：

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## 步骤8：保存PDF文档

保存修改后的PDF文档：

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

确保更换`"TextAndImageAsParagraph_out.pdf"`与所需的输出文件名。

### 使用 Aspose.PDF for .NET 的文本和图像作为段落的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//实例化文档实例
Document doc = new Document();
//将页面添加到 Document 实例的页面集合中
Page page = doc.Pages.Add();
//创建文本片段网
TextFragment text = new TextFragment("Hello World.. ");
//将文本片段添加到 Page 对象的段落集合中
page.Paragraphs.Add(text);
//创建图像实例
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
//将图像设置为内联段落，以便它出现在
//上一段对象（TextFragment）
image.IsInLineParagraph = true;
//指定图像文件路径
image.File = dataDir + "aspose-logo.jpg";
//设置图像高度（可选）
image.FixHeight = 30;
//设置图像宽度（可选）
image.FixWidth = 100;
//将图像添加到页面对象的段落集合中
page.Paragraphs.Add(image);
//使用不同的内容重新初始化 TextFragment 对象
text = new TextFragment(" Hello Again..");
//将 TextFragment 设置为内联段落
text.IsInLineParagraph = true;
//将新创建的 TextFragment 添加到页面的段落集合中
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## 结论

恭喜！您已成功学习如何使用 Aspose.PDF for .NET 在 PDF 文档中添加文本和图像作为内联段落。本教程提供了从设置项目到保存修改后的文档的分步指南。现在，您可以将此代码合并到您自己的 C# 项目中，以自定义 PDF 文件中文本和图像的布局。