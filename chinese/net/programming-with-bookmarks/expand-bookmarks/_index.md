---
title: 展开书签
linktitle: 展开书签
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松扩展 PDF 文件的书签以改进导航。
type: docs
weight: 50
url: /zh/net/programming-with-bookmarks/expand-bookmarks/
---

在 PDF 文档中展开书签将默认显示所有打开的书签。使用 Aspose.PDF for .NET，您可以按照以下源代码轻松扩展书签：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要展开其书签的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 3 步：打开 PDF 文档

现在我们将使用以下代码打开我们想要扩展其书签的 PDF 文档：

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 第四步：设置页面显示模式

在这一步中，我们将页面显示方式设置为默认显示书签。我们使用`PageMode`的财产`doc`对象来设置所需的页面模式。下面是相应的代码：

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## 第 5 步：浏览书签并展开它们

现在我们将遍历文档书签集合中的每个书签项，并将每个项的打开状态设置为`true`默认展开它们。下面是相应的代码：

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## 第 6 步：保存更新后的文件

最后，我们使用`Save`的方法`doc`目的。下面是相应的代码：

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 展开书签的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document doc = new Document(dataDir + "input.pdf");
//设置页面查看模式即显示缩略图、全屏、显示附件面板
doc.PageMode = PageMode.UseOutlines;
//遍历PDF文件大纲集合中的每一个Ouline项
foreach (OutlineItemCollection item in doc.Outlines)
{
	//设置大纲项的打开状态
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
//保存输出
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## 结论

恭喜！您现在有了使用 Aspose.PDF for .NET 开发书签的分步指南。您可以使用此代码显示 PDF 文档中的所有默认书签。

请务必查看官方 Aspose.PDF 文档以获取有关高级书签操作功能的更多信息。