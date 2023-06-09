---
title: 页眉中的文本
linktitle: 页眉中的文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉中添加文本。
type: docs
weight: 190
url: /zh/net/programming-with-stamps-and-watermarks/text-in-header/
---
在本教程中，我们将学习如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉中添加文本。请按照以下步骤操作：

## 第一步：项目准备

确保您已经安装了 Aspose.PDF for .NET 并创建了一个 C# 项目。

## 第 2 步：导入命名空间

将以下命名空间添加到 C# 源文件中：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第 3 步：打开文档

使用提供的路径打开现有的 PDF 文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinHeader.pdf");
```

请务必将“您的文档目录”替换为您的文档目录的实际路径。

## 第 4 步：创建标题文本

使用要在标题中添加的文本创建一个新的文本标记：

```csharp
TextStamp textStamp = new TextStamp("Header text");
```

您可以通过更改上边距、水平对齐方式和垂直对齐方式等属性来自定义文本。

## 第 5 步：向所有页面添加标题文本

浏览 PDF 文档的所有页面并在页眉中添加文本戳记：

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## 步骤 6：保存 PDF 文档

在所有页面上添加标题文本后，保存更新的 PDF 文档：

```csharp
pdfDocument.Save(dataDir + "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at: " + dataDir);
```

请务必将“您的文档目录”替换为您要保存 PDF 文档的目录的实际路径。

### 使用 Aspose.PDF for .NET 的 Textin Header 示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir+ "TextinHeader.pdf");

//创建标题
TextStamp textStamp = new TextStamp("Header Text");

//设置图章的属性
textStamp.TopMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Top;

//在所有页面上添加标题
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}

//保存更新的文档
pdfDocument.Save(dataDir+ "TextinHeader_out.pdf");
Console.WriteLine("\nText in header added successfully.\nFile saved at " + dataDir);

```

## 结论

恭喜！您已经学习了如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉中添加文本。您现在可以通过向 PDF 文档添加额外的文本来自定义标题。
