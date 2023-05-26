---
title: 获取特定注释
linktitle: 获取特定注释
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南了解如何使用 Aspose.PDF for .NET 在 PDF 文档中获取特定注释。
type: docs
weight: 80
url: /zh/net/annotations/getparticularannotation/
---
如果您在 .NET 中处理 PDF，您可能会遇到从 PDF 文档中获取特定注释的需要。在本指南中，我们将向您展示如何使用 C# 使用 Aspose.PDF for .NET 从 PDF 文档中获取特定注释。

按照以下简单步骤从 PDF 文档中获取特定注释：

## 第 1 步：从 PDF 文档中获取特定注释

首先，确保您的项目中安装并引用了 Aspose.PDF for .NET 库。

接下来，创建 Document 类的新实例并使用文档目录的路径加载 PDF 文档。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");
```

## 第 2 步：您可以使用以下代码获取特定注释：

```csharp
TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];
```

此代码检索 PDF 文档第二页上的第二个注释。

## 第三步：最后，你可以使用下面的代码获取注解的属性：

```csharp
Console.WriteLine("Title : {0} ", textAnnotation.Title);
Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
Console.WriteLine("Contents : {0} ", textAnnotation.Contents);
```

此代码在控制台中显示注释的标题、主题和内容。


### 使用 Aspose.PDF for .NET 获取特定注释的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//打开文档
	Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");

	//获取特定注释
	TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];

	//获取注释属性
	Console.WriteLine("Title : {0} ", textAnnotation.Title);
	Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
	Console.WriteLine("Contents : {0} ", textAnnotation.Contents);

```

