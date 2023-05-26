---
title: 设置缩放系数
linktitle: 设置缩放系数
second_title: Aspose.PDF for .NET API 参考
description: 通过我们的分步指南，了解如何使用 Aspose.PDF for .NET 为 PDF 文件设置缩放系数。
type: docs
weight: 340
url: /zh/net/programming-with-document/setzoomfactor/
---
Aspose.PDF for .NET 是一个强大的 API，允许开发人员在他们的 .NET 应用程序中处理 PDF 文档。它提供的功能之一是能够设置 PDF 文档的缩放系数。在本分步指南中，我们将解释如何使用 Aspose.PDF for .NET 使用提供的 C# 源代码设置 PDF 文档的缩放系数。

## 第一步：设置文档目录路径

第一步是设置PDF文档所在目录的路径。这可以通过设置`dataDir`目录路径的变量。 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

将“您的文档目录”替换为您的 PDF 文档所在的实际目录路径。

## 第 2 步：实例化一个新的 Document 对象

要使用 Aspose.PDF for .NET 处理 PDF 文档，我们需要创建一个新的`Document`对象并将 PDF 文件加载到其中。 

```csharp
Document doc = new Document(dataDir + "SetZoomFactor.pdf");
```

此代码将创建一个新的`Document`对象并从中加载名为“SetZoomFactor.pdf”的 PDF 文件`dataDir`目录放入其中。

## 第 3 步：设置缩放系数

一旦`Document`对象创建完成后，我们就可以设置PDF文档的缩放比例了。在下面的代码中，我们将缩放系数设置为 50%。

```csharp
GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
```

此代码通过创建一个新的将缩放因子设置为 50%`GoToAction`对象并传递一个`XYZExplicitDestination`缩放系数为 50% 的对象。这`OpenAction`的财产`Document`然后将对象设置为此`GoToAction`目的。

## 第 4 步：保存 PDF 文档

最后，我们可以将修改后的PDF文档保存到一个新文件中。在下面的代码中，我们将 PDF 文档保存到名为“Zoomed_pdf_out.pdf”的新文件中`dataDir`目录。

```csharp
dataDir = dataDir + "Zoomed_pdf_out.pdf";
doc.Save(dataDir);
```

## 结论

Aspose.PDF for .NET 提供了一种简单有效的方法来使用 C# 代码设置 PDF 文档的缩放系数。通过执行上述步骤，您可以轻松地在 .NET 应用程序中修改任何 PDF 文档的缩放比例。

### 使用 Aspose.PDF for .NET 设置缩放因子的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//实例化新的文档对象
	Document doc = new Document(dataDir + "SetZoomFactor.pdf");

	GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
	doc.OpenAction = action;
	dataDir = dataDir + "Zoomed_pdf_out.pdf";
	//保存文件
	doc.Save(dataDir);

```
