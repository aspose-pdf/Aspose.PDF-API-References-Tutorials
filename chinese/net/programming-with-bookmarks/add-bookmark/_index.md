---
title: 添加书签
linktitle: 添加书签
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松将书签添加到您的 PDF 文件以改进导航。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/add-bookmark/
---

在 PDF 文档中添加书签可以轻松快速地进行导航。使用 Aspose.PDF for .NET，您可以通过以下源代码轻松添加书签：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要添加书签的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 3 步：打开 PDF 文档

现在我们将使用以下代码打开要添加书签的 PDF 文档：

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## 第 4 步：创建书签对象

在此步骤中，我们将使用创建一个书签对象`OutlineItemCollection`类并设置其属性，例如标题、斜体属性、粗体属性和单击时要执行的操作。下面是相应的代码：

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## 第 5 步：为文档添加书签

最后，我们使用将创建的书签添加到文档的书签集合中`Add`的方法`Outlines`财产。下面是相应的代码：

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### 使用 Aspose.PDF for .NET 添加书签的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
//创建书签对象
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
//设置目标页码
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
//在文档的大纲集合中添加书签。
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
//保存输出
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## 结论

恭喜！现在您有了使用 Aspose.PDF for .NET 添加书签的分步指南。您可以使用此代码通过添加自定义书签来改进 PDF 文档中的导航。

请务必查看官方 Aspose.PDF 文档以获取有关高级书签操作功能的更多信息。