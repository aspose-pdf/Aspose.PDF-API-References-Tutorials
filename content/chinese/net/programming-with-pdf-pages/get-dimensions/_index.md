---
title: 获取 PDF 页面尺寸
linktitle: 获取 PDF 页面尺寸
second_title: Aspose.PDF for .NET API 参考
description: 在本教程中，我们将解释如何使用 Aspose.PDF for .NET 获取 PDF 页面尺寸并执行操作。提供了详细的步骤来指导您完成整个过程。
type: docs
weight: 60
url: /zh/net/programming-with-pdf-pages/get-dimensions/
---
在本教程中，我们将引导您逐步完成使用 Aspose.PDF for .NET 获取 PDF 文件中的页面尺寸的过程。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.PDF for .NET 获取 PDF 文件中页面的尺寸。

## 先决条件
在开始之前，请确保您具备以下条件：

- C# 编程语言的基础知识
- 在您的开发环境中安装 Aspose.PDF for .NET

## 第1步：定义文档目录
首先，您需要设置文档目录的路径。这是您的 PDF 文件所在的位置。将“您的文档目录”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤 2：打开 PDF 文档
然后您可以使用以下命令打开 PDF 文件`Document`Aspose.PDF 类。请务必指定 PDF 文件的正确路径。

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 步骤 3：添加空白页（如果需要）
如果PDF文档已经包含页面，您可以使用索引跳转到现有页面`1`（第一页的索引为 1）。否则，您可以向文档添加新页面。

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## 第 4 步：获取页面尺寸
您现在可以使用以下方法获取页面尺寸`GetPageRect()`的方法`Page`目的。该方法返回一个`Rectangle`包含页面尺寸的对象。您可以使用以下命令访问宽度和高度`Width`和`Height`特性。

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## 第 5 步：旋转页面
如果你想旋转页面，你可以使用`Rotate`的财产`Page`目的。在此示例中，页面旋转 90 度。

```csharp
page. Rotate = Rotate. on90;
```

## 第6步：再次获取页面尺寸
页面旋转后，您可以使用以下命令再次获取页面尺寸`GetPageRect()`方法。

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### 使用 Aspose.PDF for .NET 获取尺寸的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
//向 pdf 文档添加空白页
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
//获取页面高度和宽度信息
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
//将页面旋转 90 度角
page.Rotate = Rotation.on90;
//获取页面高度和宽度信息
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 获取 PDF 文件中页面的尺寸。通过按照提供的步骤操作，您可以轻松提取页面尺寸并执行其他 PDF 操作操作。 Aspose.PDF for .NET 为处理 PDF 文件提供了极大的灵活性，并允许您开发强大的定制解决方案。

请随意进一步探索 Aspose.PDF 的文档，以发现该库提供的所有功能。

### 获取 PDF 页面尺寸的常见问题解答

#### 问：如何获取 PDF 文件中特定页面的尺寸？

答：要获取 PDF 文件中特定页面的尺寸，您可以使用`GetPageRect()`的方法`Page`Aspose.PDF for .NET 中的对象。该方法返回一个`Rectangle`包含页面尺寸（宽度和高度）的对象。

#### 问：什么是`GetPageRect(true)` method do in the provided C# source code?

答： 的`GetPageRect(true)`提供的 C# 源代码中的方法返回应用任何旋转后页面的尺寸。如果页面旋转，该方法将返回旋转页面的尺寸，该尺寸可能与原始尺寸不同。

#### 问：我可以使用 Aspose.PDF for .NET 获取 PDF 文档中所有页面的尺寸吗？

 A：是的，您可以通过迭代来获取PDF文档中所有页面的尺寸`Pages`的集合`Document`对象并使用`GetPageRect(true)`每个页面的方法。

#### 问：如何根据页面的尺寸确定页面的方向（纵向或横向）？

答：要根据页面的尺寸确定页面的方向，您可以比较页面的宽度和高度。如果宽度大于高度，则页面为横向，如果高度大于宽度，则页面为纵向。

#### 问：我可以使用 Aspose.PDF for .NET 修改页面尺寸吗？

答：是的，您可以在 Aspose.PDF for .NET 中修改页面的尺寸。得到后`Rectangle`代表页面尺寸的对象，您可以根据您的要求调整宽度和高度，然后将更改应用到页面。