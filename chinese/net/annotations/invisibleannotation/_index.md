---
title: 隐形注解
linktitle: 隐形注解
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 C# 源代码和 Aspose.PDF for .NET 对 PDF 进行不可见的注释。分步指南。
type: docs
weight: 100
url: /zh/net/annotations/invisibleannotation/
---
## 了解 PDF 文档中的注释

PDF 文档中的注释是一项强大的功能，允许您在不更改实际内容的情况下向文档添加额外的信息或注释。它们可用于突出显示文本、引起对文档特定区域的注意或添加评论或反馈。

您可以在 PDF 文档中使用许多不同类型的注释，包括：

- 文本注释
- 链接注解
- 邮票注解
- 声音注释
- 文件附件注释
- 还有很多

## 使用 Aspose.PDF for .NET 在 PDF 文档中创建不可见注释

要使用 Aspose.PDF for .NET 在 PDF 文档中创建不可见的注释，我们首先需要创建一个`FreeTextAnnotation`对象并指定注释的位置和大小。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

在上面的代码中，我们创建了一个`FreeTextAnnotation`对象并指定注释在 PDF 文档第 2 页上的位置。我们还指定将在注释中显示的文本的字体类型、大小和颜色。

## 向不可见注释添加特征

接下来，我们可以为注释添加一些特征，例如边框颜色、背景颜色或不透明度。

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

在上面的代码中，我们将注释的边框颜色设置为红色。

## 设置注释标志

在创建注解并设置其特征后，我们可以指定注解标志。在本教程中，我们希望注释可打印，但不可查看。

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
```

## 保存修改后的 PDF 文档

最后，我们可以使用新的不可见注释保存修改后的 PDF 文档。

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## 如何使用 Aspose.PDF for .NET 进行不可见注释的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1