---
title: 页码邮票
linktitle: 页码邮票
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 将页码标记添加到 PDF 文档。
type: docs
weight: 160
url: /zh/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 向 PDF 文档添加页码标记。我们将使用提供的 C# 源代码打开现有的 PDF 文档，创建页码戳记，设置其属性，并将其添加到 PDF 文档中的特定页面。

## 第 1 步：设置环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 在您的项目中下载并引用了用于 .NET 的 Aspose.PDF 库。

## 第 2 步：加载现有的 PDF 文档

第一步是将现有的 PDF 文档加载到您的项目中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//打开现有的 PDF 文档
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

请务必将“您的文档目录”替换为您的 PDF 文档所在目录的实际路径。

## 第 3 步：创建和配置页码标记

现在 PDF 文档已加载，我们可以创建页码缓冲区并根据需要进行配置。就是这样：

```csharp
//创建页码缓冲区
PageNumberStamp pageNumberStamp = new PageNumberStamp();

//定义缓冲区是否在后台
pageNumberStamp.Background = false;

//页码缓冲区的格式
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

//页码缓冲区的底部边距
pageNumberStamp.BottomMargin = 10;

//页码缓冲区的水平对齐
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

//页码的起始编号
pageNumberStamp.StartingNumber = 1;

//设置页码缓冲区文本属性
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

上面的代码创建了一个页码标记，具有页码格式、下边距、水平对齐、起始编号和文本属性等属性。

## 第 4 步：将页码标记添加到特定页面

配置页码戳后，我们可以将其添加到 PDF 文档的特定页面。就是这样：

```csharp
//将页码缓冲区添加到特定页面
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

上面的代码将页码标记添加到 PDF 文档的第一页。您可以根据需要更改页码。

## 步骤 5：保存修改后的 PDF 文档

一旦为PDF文档添加了页码戳，我们就可以保存修改后的PDF文档了。就是这样：

```csharp
//保存修改后的 PDF 文档
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

请务必将“您的文档目录”替换为您要保存已编辑 PDF 文档的目录的实际路径。

### 使用 Aspose.PDF for .NET 的页码戳示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

//创建页码图章
PageNumberStamp pageNumberStamp = new PageNumberStamp();

//邮票是否背景
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

//设置文本属性
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

//在特定页面上添加图章
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

//保存输出文件
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## 结论

恭喜！您已经学习了如何使用 Aspose.PDF for .NET 将页码标记添加到 PDF 文档。您现在可以通过添加清晰且信息丰富的页码来个性化您的 PDF 文档。
