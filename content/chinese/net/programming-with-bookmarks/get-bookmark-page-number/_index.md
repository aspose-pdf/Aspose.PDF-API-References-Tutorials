---
title: 获取 PDF 文件中的书签页码
linktitle: 获取 PDF 文件中的书签页码
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松获取 PDF 文件中的书签页码。
type: docs
weight: 60
url: /zh/net/programming-with-bookmarks/get-bookmark-page-number/
---
检索与 PDF 文件中的书签关联的页码对于导航非常有用。使用Aspose.PDF for .NET，您可以通过以下源代码轻松获取书签的页码：

## 第1步：导入所需的库

在开始之前，您需要为 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf.Facades;
```

## 步骤 2：设置文档文件夹路径

在此步骤中，您需要指定包含要从中提取书签页码的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第三步：创建书签编辑器

现在我们将创建一个`PdfBookmarkEditor`对象来操作文档的书签。使用以下代码：

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## 第 4 步：打开 PDF 文件

在此步骤中，我们使用以下命令打开 PDF 文件`BindPdf`书签编辑器的方法。这是相应的代码：

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## 第5步：提取书签

现在我们将使用以下命令从文档中提取书签`ExtractBookmarks`书签编辑器的方法。这是相应的代码：

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## 第 6 步：浏览书签并获取页码

最后，我们循环遍历提取的书签，并使用以下方法获取与每个书签关联的页码：`foreach`环形。这是相应的代码：

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
//创建Pdf书签编辑器
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
//打开 PDF 文件
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

恭喜！现在您有了使用 Aspose.PDF for .NET 获取书签页码的分步指南。您可以使用此代码检索与 PDF 文档中每个书签关联的导航信息。

请务必查看官方 Aspose.PDF 文档，以获取有关高级书签操作功能的更多信息。

### 获取 PDF 文件中书签页码的常见问题解答

#### 问：PDF 文件中的书签是什么？

答：PDF 文件中的书签是导航辅助工具，允许用户快速跳转到文档中的特定部分或页面。它们通过提供相关内容的快捷方式来增强用户体验。

#### 问：为什么我要从 PDF 文件中检索书签页码？

答：检索书签页码可以帮助用户更有效地浏览文档，并清楚地指示每个书签的位置。这对于具有多个部分的较长文档特别有用。

#### 问：如何导入 C# 项目所需的库？

答：要导入 C# 项目所需的库，请使用以下导入指令：

```csharp
using Aspose.Pdf.Facades;
```

该指令允许您利用 Aspose.PDF for .NET 提供的类和方法。

#### 问：如何指定文档文件夹的路径？

 A：在提供的源代码中，替换`"YOUR DOCUMENT DIRECTORY"`包含要从中提取书签页码的 PDF 文件的文件夹的实际路径。这可确保代码可以找到目标 PDF 文件。

#### 问：如何创建书签编辑器？

答：要创建书签编辑器，请使用以下代码：

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### 问：如何打开 PDF 文件进行书签操作？

A：要打开PDF文件以提取书签信息，请使用以下代码：

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

代替`"GetBookmarks.pdf"`与实际的文件名。

#### 问：如何从 PDF 文件中提取书签？

答：要从 PDF 文件中提取书签，请使用`ExtractBookmarks`书签编辑器方法：

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### 问：如何检索和显示书签页码？

 A：使用循环遍历提取的书签`foreach`循环并访问`PageNumber`每个书签的属性来检索并显示其关联的页码：

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### 问：我可以使用这种方法修改书签属性吗？

答：虽然本教程重点介绍检索书签页码，但您可以使用相同的方法修改其他书签属性`Bookmark`对象和相关属性。

#### 问：提取书签信息后如何保存更新的PDF文件？

答：书签提取不会修改原始 PDF 文件。如果您想保存任何更改，可以使用 Aspose.PDF for .NET 提供的其他方法来完成。