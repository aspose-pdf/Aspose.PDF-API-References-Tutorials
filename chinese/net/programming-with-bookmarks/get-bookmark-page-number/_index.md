---
title: 获取书签页码
linktitle: 获取书签页码
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松从您的 PDF 文件中获取书签页码。
type: docs
weight: 60
url: /zh/net/programming-with-bookmarks/get-bookmark-page-number/
---

检索与 PDF 文档中的书签关联的页码对于导航很有用。使用Aspose.PDF for .NET，您可以通过以下源代码轻松获取书签的页码：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf.Facades;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要从中提取书签页码的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 3 步：创建书签编辑器

现在我们将创建一个`PdfBookmarkEditor`对象来操作文档的书签。使用以下代码：

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## 第 4 步：打开 PDF 文件

在此步骤中，我们使用`BindPdf`书签编辑器的方法。下面是相应的代码：

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## 第五步：提取书签

现在我们将使用`ExtractBookmarks`书签编辑器的方法。下面是相应的代码：

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## 第 6 步：浏览书签并获取页码

最后，我们遍历提取的书签并使用`foreach`环形。下面是相应的代码：

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### 使用 Aspose.PDF for .NET 获取书签页码的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建 PdfBookmarkEditor
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
//打开PDF文件
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
//提取书签
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## 结论

恭喜！现在，您有了使用 Aspose.PDF for .NET 获取书签页码的分步指南。您可以使用此代码检索与 PDF 文档中每个书签关联的导航信息。

请务必查看官方 Aspose.PDF 文档以获取有关高级书签操作功能的更多信息。