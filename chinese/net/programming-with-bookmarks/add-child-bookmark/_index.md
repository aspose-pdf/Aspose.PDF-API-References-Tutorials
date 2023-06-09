---
title: 添加子书签
linktitle: 添加子书签
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松将子书签添加到您的 PDF 文件，以便更有条理地浏览。
type: docs
weight: 20
url: /zh/net/programming-with-bookmarks/add-child-bookmark/
---

将子书签添加到 PDF 文档可以实现更有条理的组织和导航。使用 Aspose.PDF for .NET，您可以通过以下源代码轻松添加子书签：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要添加子书签的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 3 步：打开 PDF 文档

现在我们将使用以下代码打开要添加子书签的 PDF 文档：

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## 第 4 步：创建父书签对象

在此步骤中，我们将使用`OutlineItemCollection`类并设置其属性，如标题、斜体属性和粗体属性。下面是相应的代码：

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## 步骤 5：创建子书签对象

在这一步中，我们将使用`OutlineItemCollection`类并设置其属性。下面是相应的代码：

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## 第 6 步：将子书签添加到父书签

最后，我们使用将创建的子书签添加到父书签的子书签集合中`Add`父对象的方法。下面是相应的代码：

```csharp
pdfOutline.Add(pdfChildOutline);
```

## 第 7 步：将父书签添加到文档的书签集合中

最后，我们使用`Add`的方法`Outlines`财产。下面是相应的代码：

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### 使用 Aspose.PDF for .NET 添加子书签的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
//创建父书签对象
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
//创建子书签对象
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
//在父书签的集合中添加子书签
pdfOutline.Add(pdfChildOutline);
//在文档的大纲集合中添加父书签。
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
//保存输出
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## 结论

恭喜！现在您有了一个使用 Aspose.PDF for .NET 添加子书签的分步指南。您可以使用此代码来组织和构建 PDF 文档中的书签。

请务必查看官方 Aspose.PDF 文档以获取有关高级书签操作功能的更多信息。