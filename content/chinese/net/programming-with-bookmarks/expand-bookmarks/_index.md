---
title: 展开 PDF 文件中的书签
linktitle: 展开 PDF 文件中的书签
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松扩展 PDF 文件中的书签以改进导航。
type: docs
weight: 50
url: /zh/net/programming-with-bookmarks/expand-bookmarks/
---
默认情况下，展开 PDF 文件中的书签将显示所有打开的书签。使用Aspose.PDF for .NET，您可以通过以下源代码轻松扩展书签：

## 第1步：导入所需的库

在开始之前，您需要为 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf;
```

## 步骤 2：设置文档文件夹路径

在此步骤中，您需要指定包含要展开其书签的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 3：打开 PDF 文档

现在我们将使用以下代码打开要扩展其书签的PDF文档：

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 第四步：设置页面显示模式

在这一步中，我们将页面显示模式设置为默认显示书签。我们使用`PageMode`的财产`doc`对象设置所需的页面模式。这是相应的代码：

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## 第 5 步：浏览书签并展开它们

现在我们将循环遍历文档书签集合中的每个书签项，并将每个项的打开状态设置为`true`默认情况下展开它们。这是相应的代码：

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## 第 6 步：保存更新的文件

最后，我们使用以下命令保存更新后的 PDF 文件`Save`的方法`doc`目的。这是相应的代码：

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
//设置页面查看模式，即显示缩略图、全屏、显示附件面板
doc.PageMode = PageMode.UseOutlines;
//遍历 PDF 文件轮廓集合中的每个 Ouline 项目
foreach (OutlineItemCollection item in doc.Outlines)
{
	//设置大纲项目的打开状态
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
//保存输出
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## 结论

恭喜！您现在已经有了使用 Aspose.PDF for .NET 开发书签的分步指南。您可以使用此代码显示 PDF 文档中的所有默认书签。

请务必查看官方 Aspose.PDF 文档，以获取有关高级书签操作功能的更多信息。

### PDF 文件中展开书签的常见问题解答

#### 问：PDF 文件中的书签是什么？

答：PDF 文件中的书签是导航辅助工具，允许用户快速跳转到文档中的特定部分或页面。它们提供了访问文档不同部分的便捷方法。

#### 问：为什么我要在 PDF 文件中展开书签？

答：展开书签可以提高用户体验，所有书签默认以展开状态显示。这使用户可以清楚地了解文档的结构，并允许他们轻松导航到不同的部分。

#### 问：如何导入 C# 项目所需的库？

答：要导入 C# 项目所需的库，请使用以下导入指令：

```csharp
using Aspose.Pdf;
```

该指令允许您利用 Aspose.PDF for .NET 提供的类和方法。

#### 问：如何指定文档文件夹的路径？

 A：在提供的源代码中，替换`"YOUR DOCUMENT DIRECTORY"`包含您要使用的 PDF 文件的文件夹的实际路径。这可确保代码可以找到目标 PDF 文件。

#### 问：如何打开 PDF 文档以展开其书签？

答：要打开 PDF 文档以展开书签，请使用以下代码：

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

代替`"input.pdf"`与实际的文件名。

#### 问：如何设置页面显示方式默认显示书签？

A：要将页面显示模式设置为默认显示书签，请使用`PageMode`的财产`doc`目的：

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### 问：如何展开PDF文档中的所有书签？

答：要展开所有书签，请循环浏览文档大纲集合中的每个书签项并设置`Open`财产给`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### 问：如果书签有嵌套子书签会怎样？

答：如果书签有嵌套的子书签，则展开父书签也会展开其子书签，从而提供文档结构的全面视图。

#### 问：展开书签后如何保存更新的PDF文件？

答：要在展开书签后保存更新的 PDF 文件，请使用以下代码：

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### 问：我可以自定义展开书签的外观吗？

答：虽然本教程默认重点介绍扩展书签，但您可以使用 Aspose.PDF 的其他功能和属性自定义书签的外观。