---
title: 更新 PDF 页面尺寸
linktitle: 更新 PDF 页面尺寸
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 更新 PDF 页面尺寸的分步指南。根据您的需要检查尺寸。
type: docs
weight: 150
url: /zh/net/programming-with-pdf-pages/update-dimensions/
---
在本教程中，我们将引导您逐步使用 Aspose.PDF for .NET 更新 PDF 文档中的页面尺寸。我们将解释捆绑的 C# 源代码并为您提供全面的指南，以帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.PDF for .NET 更改 PDF 文档中的页面尺寸。

## 先决条件
开始之前，请确保您已准备好以下物品：

- C# 编程语言的基础知识
- 在您的开发环境中安装 Aspose.PDF for .NET

## 步骤1：定义文档目录
首先，您需要设置文档目录的路径。这是您要保存编辑的 PDF 文档的位置。将“您的文档目录”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：打开 PDF 文档
然后您可以使用`Document`Aspose.PDF 类。请确保指定正确的文档路径。

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 步骤 3：获取页面集合
现在，您可以使用`Pages`的财产`Document`班级。

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 步骤 4：获取特定页面
然后，您可以使用集合中页面的索引选择文档的特定页面。在此示例中，我们使用第二页（索引 1）。

```csharp
Page pdfPage = pageCollection[1];
```

## 步骤 5：定义新的页面尺寸
现在，您可以使用`SetPageSize()`方法`Page`对象。在此示例中，我们将页面尺寸设置为 A4（11.7 x 8.3 英寸），转换为点（1 英寸 = 72 点）。

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## 步骤 6：保存更新后的文档
最后，您可以使用`Save()`方法`Document`类。请确保指定正确的路径和文件名。

```csharp
dataDir = dataDir + "UpdateDimensions_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 更新尺寸的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
//获取页面集合
PageCollection pageCollection = pdfDocument.Pages;
//获取特定页面
Page pdfPage = pageCollection[1];
//将页面尺寸设置为 A4（11.7 x 8.3 英寸），在 Aspose.Pdf 中，1 英寸 = 72 点
//因此 A4 尺寸（以点为单位）为 (842.4, 597.6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
//保存更新的文档
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 更新 PDF 文档中页面的尺寸。按照本分步指南，您可以根据需要轻松更改 PDF 文档中页面的尺寸。Aspose.PDF 提供了强大而灵活的 API，用于处理 PDF 文件并执行各种操作，包括更改页面尺寸。有了这些知识，您可以控制和自定义 PDF 页面的尺寸以满足您的特定需求。

### 更新 PDF 页面尺寸的常见问题解答

#### 问：如何使用 Aspose.PDF for .NET 更新 PDF 文档中特定页面的尺寸？

答：要使用 Aspose.PDF for .NET 更新 PDF 文档中特定页面的尺寸，您可以按照以下步骤操作：

1. 通过指定原始 PDF 文件所在的路径以及要保存更新的 PDF 文件的路径来设置文档目录。将“您的文档目录”替换为适当的路径。
2. 打开现有 PDF 文档进行更新，使用`Document`Aspose.PDF 类。请确保指定原始 PDF 文档的正确路径。
3. 使用`Pages`的财产`Document`班级。
4. 使用页面索引从页面集合中选择要更新的特定页面。在提供的 C# 源代码中，我们使用第二个页面（索引 1）。
5. 使用定义新的页面大小`SetPageSize()`方法`Page`对象。在示例中，我们将页面尺寸设置为 A4 尺寸（11.7 x 8.3 英寸），转换为点（1 英寸 = 72 点）。
6. 使用`Save()`方法`Document`类。请确保指定正确的路径和文件名。

#### 问：我可以同时更新 PDF 文档中多个页面的尺寸吗？

答：是的，您可以修改提供的源代码，以同时更新 PDF 文档中多个页面的尺寸。您可以循环遍历页面集合中的所有页面，并为每个页面设置所需的页面大小，而不是选择特定页面（如步骤 4 所示）。

#### 问：使用 Aspose.PDF for .NET 时，如何将页面尺寸从英寸转换为点？

答：在 Aspose.PDF for .NET 中，页面尺寸使用的测量单位是点，其中 1 英寸相当于 72 点。要将英寸转换为点，可以使用以下公式：`points = inches * 72`。例如，要设置页面大小为 11.7 x 8.3 英寸，则可以计算相应的尺寸（以点为单位）为 (11.7 * 72) 和 (8.3 * 72)。

#### 问：更新页面尺寸会影响 PDF 文档的内容布局吗？

答：是的，更新页面尺寸会影响该特定页面上 PDF 文档的内容布局。当您更改页面尺寸时，页面上的内容将相应调整以适应新的尺寸。

#### 问：更新后，可以撤消更改并恢复原始页面尺寸吗？

答：是的，如果您想恢复更改并恢复原始页面尺寸，您可以保留更改前的原始 PDF 文档副本，也可以重新打开原始 PDF 文档而不保存更改。这样，原始尺寸将被保留。