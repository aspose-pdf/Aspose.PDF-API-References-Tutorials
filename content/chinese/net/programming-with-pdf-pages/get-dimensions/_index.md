---
title: 获取 PDF 页面尺寸
linktitle: 获取 PDF 页面尺寸
second_title: Aspose.PDF for .NET API 参考
description: 在本教程中，我们将解释如何使用 Aspose.PDF for .NET 获取 PDF 页面尺寸并执行操作。提供了详细的步骤来指导您完成整个过程。
type: docs
weight: 60
url: /zh/net/programming-with-pdf-pages/get-dimensions/
---
在本教程中，我们将引导您逐步使用 Aspose.PDF for .NET 获取 PDF 文件中的页面尺寸。我们将解释捆绑的 C# 源代码并为您提供全面的指南，以帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.PDF for .NET 获取 PDF 文件中页面的尺寸。

## 先决条件
开始之前，请确保您已准备好以下物品：

- C# 编程语言的基础知识
- 在您的开发环境中安装 Aspose.PDF for .NET

## 步骤1：定义文档目录
首先，您需要设置文档目录的路径。这是您的 PDF 文件所在的位置。将“您的文档目录”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：打开 PDF 文档
然后您可以使用`Document`Aspose.PDF 类。请确保指定 PDF 文件的正确路径。

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 步骤 3：添加空白页（如果需要）
如果 PDF 文档已包含页面，则可以使用索引跳转到现有页面`1`（第一页的索引为 1）。否则，您可以向文档添加新页面。

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## 步骤 4：获取页面尺寸
您现在可以使用`GetPageRect()`方法`Page`对象。此方法返回一个`Rectangle`包含页面尺寸的对象。您可以使用`Width`和`Height`特性。

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## 步骤 5：旋转页面
如果你想旋转页面，你可以使用`Rotate`的财产`Page`对象。在此示例中，页面旋转了 90 度。

```csharp
page. Rotate = Rotate. on90;
```

## 步骤 6：再次获取页面尺寸
页面旋转后，您可以使用`GetPageRect()`方法。

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### 使用 Aspose.PDF for .NET 获取尺寸的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
//向 PDF 文档添加空白页
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
//获取页面高度和宽度信息
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
//将页面旋转 90 度
page.Rotate = Rotation.on90;
//获取页面高度和宽度信息
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 获取 PDF 文件中页面的尺寸。按照提供的步骤，您可以轻松提取页面尺寸并执行其他 PDF 操作。Aspose.PDF for .NET 为处理 PDF 文件提供了极大的灵活性，并允许您开发强大且定制的解决方案。

请随意进一步探索 Aspose.PDF 的文档来发现该库提供的所有功能。

### 获取 PDF 页面尺寸的常见问题解答

#### 问：如何获取 PDF 文件中特定页面的尺寸？

答：要获取 PDF 文件中特定页面的尺寸，您可以使用`GetPageRect()`方法`Page`Aspose.Pdf for .NET 中的对象。此方法返回一个`Rectangle`包含页面尺寸（宽度和高度）的对象。

#### 问：`GetPageRect(true)` method do in the provided C# source code?

答：`GetPageRect(true)`提供的 C# 源代码中的方法返回应用任何旋转后的页面尺寸。如果页面被旋转，该方法将返回旋转后的页面尺寸，该尺寸可能与原始尺寸不同。

#### 问：我可以使用 Aspose.PDF for .NET 获取 PDF 文档中所有页面的尺寸吗？

答：是的，您可以通过迭代获取 PDF 文档中所有页面的尺寸`Pages`收集`Document`对象并使用`GetPageRect(true)`方法。

#### 问：如何根据页面尺寸确定页面的方向（纵向或横向）？

答：要根据页面尺寸确定页面方向，您可以比较页面的宽度和高度。如果宽度大于高度，则页面为横向，如果高度大于宽度，则页面为纵向。

#### 问：我可以使用 Aspose.PDF for .NET 修改页面尺寸吗？

答：是的，您可以在 Aspose.PDF for .NET 中修改页面的尺寸。获取`Rectangle`代表页面尺寸的对象，您可以根据需要调整宽度和高度，然后将更改应用到页面。