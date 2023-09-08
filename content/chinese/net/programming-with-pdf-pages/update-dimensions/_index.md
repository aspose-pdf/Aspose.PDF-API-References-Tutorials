---
title: 更新 PDF 页面尺寸
linktitle: 更新 PDF 页面尺寸
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 更新 PDF 页面尺寸的分步指南。根据您的需要检查尺寸。
type: docs
weight: 150
url: /zh/net/programming-with-pdf-pages/update-dimensions/
---
在本教程中，我们将引导您逐步完成使用 Aspose.PDF for .NET 更新 PDF 文档中的页面尺寸的过程。我们将解释捆绑的 C# 源代码，并为您提供全面的指南，帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.PDF for .NET 更改 PDF 文档中的页面尺寸。

## 先决条件
在开始之前，请确保您具备以下条件：

- C# 编程语言的基础知识
- 在您的开发环境中安装 Aspose.PDF for .NET

## 第1步：定义文档目录
首先，您需要设置文档目录的路径。这是您要保存编辑的 PDF 文档的位置。将“您的文档目录”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤 2：打开 PDF 文档
然后您可以使用以下命令打开现有的 PDF 文档`Document`Aspose.PDF 类。请务必指定正确的文档路径。

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 第三步：获取页面集合
现在您可以使用以下命令访问 PDF 文档的页面集合`Pages`的财产`Document`班级。

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 第四步：获取特定页面
然后，您可以使用集合中页面的索引来选择文档的特定页面。在此示例中，我们使用第二页（索引 1）。

```csharp
Page pdfPage = pageCollection[1];
```

## 步骤 5：定义新页面尺寸
现在您可以使用以下命令设置新的页面大小`SetPageSize()`的方法`Page`目的。在此示例中，我们将页面尺寸设置为 A4（11.7 x 8.3 英寸），并转换为磅（1 英寸 = 72 磅）。

```csharp
pdfPage.SetPageSize(597.6, 842.4);
```

## 步骤 6：保存更新后的文档
最后，您可以使用以下命令将更新的 PDF 文档保存到文件中：`Save()`的方法`Document`班级。请务必指定正确的路径和文件名。

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
//将页面大小设置为 A4（11.7 x 8.3 英寸），在 Aspose.Pdf 中，1 英寸 = 72 点
//因此 A4 尺寸（以点为单位）将为 (842.4, 597.6)
pdfPage.SetPageSize(597.6, 842.4);
dataDir = dataDir + "UpdateDimensions_out.pdf";
//保存更新后的文档
pdfDocument.Save(dataDir);
System.Console.WriteLine("\nPage dimensions updated successfully.\nFile saved at " + dataDir);

```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 更新 PDF 文档中页面的尺寸。通过遵循此分步指南，您可以根据需要轻松更改 PDF 文档中页面的尺寸。 Aspose.PDF 提供了强大而灵活的 API，用于处理 PDF 文件并执行各种操作，包括更改页面尺寸。有了这些知识，您就可以控制和自定义 PDF 页面的尺寸，以满足您的特定需求。

### 更新 PDF 页面尺寸的常见问题解答

#### 问：如何使用 Aspose.PDF for .NET 更新 PDF 文档中特定页面的尺寸？

答：要使用 Aspose.PDF for .NET 更新 PDF 文档中特定页面的尺寸，您可以按照以下步骤操作：

1. 通过指定原始 PDF 文件所在的路径以及要保存更新的 PDF 文件的路径来设置文档目录。将“您的文档目录”替换为适当的路径。
2. 使用以下命令打开要更新的现有 PDF 文档`Document`Aspose.PDF 类。请务必指定原始 PDF 文档的正确路径。
3. 使用以下命令访问 PDF 文档的页面集合`Pages`的财产`Document`班级。
4. 使用页面索引从页面集合中选择要更新的特定页面。在提供的 C# 源代码中，我们使用第二页（索引 1）。
5. 使用以下命令定义新的页面大小`SetPageSize()`的方法`Page`目的。在示例中，我们将页面尺寸设置为 A4 尺寸（11.7 x 8.3 英寸），并转换为磅（1 英寸 = 72 磅）。
6. 使用以下命令将更新的 PDF 文档保存到文件中`Save()`的方法`Document`班级。请务必指定正确的路径和文件名。

#### 问：我可以同时更新PDF文档中多个页面的尺寸吗？

答：是的，您可以修改提供的源代码以同时更新 PDF 文档中多个页面的尺寸。您可以循环浏览页面集合中的所有页面并为每个页面设置所需的页面大小，而不是选择特定页面（如步骤 4 中所示）。

#### 问：使用 Aspose.PDF for .NET 时如何将页面尺寸从英寸转换为磅？

答：在 Aspose.PDF for .NET 中，页面尺寸的测量单位是点，其中 1 英寸相当于 72 点。要将英寸转换为磅，您可以使用以下公式：`points = inches * 72`。例如，要将页面尺寸设置为 11.7 x 8.3 英寸，您可以将相应的尺寸（以磅为单位）计算为 (11.7 * 72) 和 (8.3 * 72)。

#### 问：更新页面尺寸会影响PDF文档的内容布局吗？

答：是的，更新页面尺寸将影响该特定页面上 PDF 文档的内容布局。当您更改页面尺寸时，页面上的内容将相应调整以适应新尺寸。

#### 问：更新后是否可以恢复更改并恢复原始页面尺寸？

答：是的，如果您想恢复更改并恢复原始页面尺寸，您可以在进行更改之前保留原始 PDF 文档的副本，或者在不保存更改的情况下再次重新打开原始 PDF 文档。这样，原始尺寸将被保留。