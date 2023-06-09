---
title: 删除图像
linktitle: 删除图像
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松删除 PDF 文件中的图像。
type: docs
weight: 110
url: /zh/net/programming-with-images/delete-images/
---

本指南将逐步指导您如何使用 Aspose.PDF for .NET 从 PDF 文件中删除图像。确保您已经设置了环境并按照以下步骤操作：

## 第一步：定义文档目录

在开始之前，请确保为文档设置了正确的目录。代替`"YOUR DOCUMENT DIRECTORY"`在代码中包含 PDF 文档所在目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：打开 PDF 文档

在此步骤中，我们将使用`Document` Aspose.PDF 类。使用`Document`构造函数并将路径传递给 PDF 文档。

```csharp
Document pdfDocument = new Document(dataDir + "DeleteImages.pdf");

```

## 第 3 步：删除特定图像

在此步骤中，我们将从特定页面中删除特定图像。使用`Delete`页面资源的方法`Images`删除图像的对象。在下面的示例中，我们从第一页删除索引为 1 的图像。

```csharp
pdfDocument.Pages[1].Resources.Images.Delete(1);
```

## 第 4 步：保存更新后的 PDF 文件

使用保存更新的 PDF 文件`Save`的方法`pdfDocument`目的。指定 PDF 文件的输出路径。

```csharp
dataDir = dataDir + "DeleteImages_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 删除图像的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir+ "DeleteImages.pdf");
//删除特定图像
pdfDocument.Pages[1].Resources.Images.Delete(1);
dataDir = dataDir + "DeleteImages_out.pdf";
//保存更新的 PDF 文件
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages deleted successfully.\nFile saved at " + dataDir); 
```

## 结论

恭喜！您已经使用 Aspose.PDF for .NET 成功地从 PDF 文件中删除了图像。更新后的 PDF 文件保存在指定目录中。您现在可以在没有已删除图像的情况下使用此 PDF 文件。