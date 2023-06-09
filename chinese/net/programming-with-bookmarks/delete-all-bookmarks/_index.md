---
title: 删除所有书签
linktitle: 删除所有书签
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松删除 PDF 文件中的所有书签。
type: docs
weight: 30
url: /zh/net/programming-with-bookmarks/delete-all-bookmarks/
---

# 使用 Aspose.PDF for .NET 删除所有书签

在某些情况下，可能需要从 PDF 文档中删除书签。使用 Aspose.PDF for .NET，您可以按照以下源代码轻松删除所有书签：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要从中删除书签的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 3 步：打开 PDF 文档

现在我们将使用以下代码打开要从中删除书签的 PDF 文档：

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
```

## 第 4 步：删除所有书签

在此步骤中，我们使用`Delete`的方法`Outlines`财产。下面是相应的代码：

```csharp
pdfDocument.Outlines.Delete();
```

## 第 5 步：保存更新后的文件

最后，我们使用`Save`的方法`pdfDocument`目的。下面是相应的代码：

```csharp
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 删除所有书签的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
//删除所有书签
pdfDocument.Outlines.Delete();
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
//保存更新的文件
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll bookmarks deleted successfully.\nFile saved at " + dataDir);
```

## 结论

恭喜！现在您有了一个逐步指南，可以使用 Aspose.PDF for .NET 删除所有书签。您可以使用此代码通过删除所有现有书签来清理 PDF 文档。

请务必查看官方 Aspose.PDF 文档以获取有关高级书签操作功能的更多信息。