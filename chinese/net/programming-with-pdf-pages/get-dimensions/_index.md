---
title: 获取维度
linktitle: 获取维度
second_title: Aspose.PDF for .NET API 参考
description: 在本教程中，我们将解释如何获取 PDF 页面尺寸并使用 Aspose.PDF for .NET 执行操作。提供了详细的步骤来指导您完成整个过程。
type: docs
weight: 60
url: /zh/net/programming-with-pdf-pages/get-dimensions/
---
在本教程中，我们将逐步引导您使用 Aspose.PDF for .NET 获取 PDF 文件中的页面尺寸。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，以帮助您了解并在您自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.PDF for .NET 获取 PDF 文件中页面的尺寸。

## 先决条件
在开始之前，请确保您具备以下条件：

- C#编程语言的基本知识
- 安装在您的开发环境中的 Aspose.PDF for .NET

## 第一步：定义文档目录
首先，您需要设置文档目录的路径。这是您的 PDF 文件所在的位置。用适当的路径替换“您的文档目录”。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：打开 PDF 文档
然后你可以使用打开PDF文件`Document`Aspose.PDF 类。请务必指定 PDF 文件的正确路径。

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 第 3 步：添加空白页（如果需要）
如果 PDF 文档已经包含页面，您可以使用索引跳转到现有页面`1`（第一页的索引为 1）。否则，您可以向文档添加新页面。

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## 第 4 步：获取页面尺寸
您现在可以使用`GetPageRect()`的方法`Page`目的。这个方法返回一个`Rectangle`包含页面尺寸的对象。您可以使用访问宽度和高度`Width`和`Height`特性。

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## 第五步：旋转页面
如果你想旋转页面，你可以使用`Rotate`的财产`Page`目的。在此示例中，页面旋转了 90 度。

```csharp
page. Rotate = Rotate. on90;
```

## 第 6 步：再次获取页面尺寸
页面旋转后，您可以使用`GetPageRect()`方法。

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### 使用 Aspose.PDF for .NET 获取维度的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
//向 pdf 文档添加空白页
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
//获取页面高宽信息
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
//将页面旋转 90 度角
page.Rotate = Rotation.on90;
//获取页面高宽信息
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 获取 PDF 文件中页面的尺寸。按照提供的步骤，您可以轻松提取页面尺寸并执行其他 PDF 操作。 Aspose.PDF for .NET 为处理 PDF 文件提供了极大的灵活性，并允许您开发强大的定制解决方案。

随意进一步探索 Aspose.PDF 的文档以发现该库提供的所有功能。
