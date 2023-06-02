---
title: 设置自由文本注释格式
linktitle: 设置自由文本注释格式
second_title: Aspose.PDF for .NET API 参考
description: 本文提供了有关如何使用 Aspose.PDF for .NET 创建自由文本注释并指定其内容的分步指南
type: docs
weight: 140
url: /zh/net/annotations/setfreetextannotationformatting/
---

Aspose.PDF for .NET 是一个功能强大且易于使用的 PDF 文档操作 API，它允许您在 .NET 应用程序中以编程方式处理 PDF 文件。 Aspose.PDF for .NET 提供的功能之一是能够在 PDF 文档中设置自由文本注释格式。在本文中，我们将引导您逐步完成使用 Aspose.PDF for .NET 设置自由文本注释格式的过程。

## 先决条件

在我们开始之前，请确保您具备以下先决条件：

- Microsoft Visual Studio 2010 或更高版本
- 用于 .NET 的 Aspose.PDF
- C#基础知识



## 1.新建一个C#控制台应用

首先，在 Microsoft Visual Studio 中创建一个新的 C# 控制台应用程序。要创建新的控制台应用程序，请从主菜单中选择“文件”>“新建”>“项目”>“Visual C#”>“控制台应用程序”。

## 2. 添加对 Aspose.PDF for .NET 的引用

接下来，在您的项目中添加对 Aspose.PDF for .NET 的引用。为此，请在“解决方案资源管理器”窗格中右键单击您的项目，选择“添加”>“引用”，然后浏览到您保存 Aspose.PDF for .NET DLL 文件的位置。选择 DLL 文件并单击“确定”以将引用添加到您的项目。

## 3.搭建环境

添加对Aspose.PDF for .NET 的引用后，您需要设置环境。为此，创建一个名为“dataDir”的新字符串变量并将其设置为 PDF 文档所在目录的路径。将下面代码中的“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的实际路径：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 4.打开PDF文档

设置环境后，您可以使用以下代码打开 PDF 文档：

```csharp
//打开文档
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

将“SetFreeTextAnnotationFormatting.pdf”替换为您的 PDF 文档的实际名称。

## 5.设置默认外观

要设置自由文本注释的默认外观，您需要使用所需的字体、字体大小和颜色实例化 DefaultAppearance 对象。在本教程中，我们将字体设置为“Arial”，字体大小设置为 28，颜色设置为红色。

```csharp
//实例化 DefaultAppearance 对象
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## 6.创建一个自由文本注释

现在您已经设置了默认外观，您可以使用以下代码创建自由文本注释：

```csharp
//创建注释
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

上面的代码在 PDF 文档的第二页上创建了一个新的自由文本注释。注释将位于 (200, 400)，宽度为 400，高度为 600。

## 7.指定注解的内容

创建自由文本注释后，您可以使用以下代码指定注释的内容：

```csharp
//指定注释的内容
freetext.Contents = "Free Text
```

### 使用 Aspose.PDF for .NET 设置自由文本注释格式的示例源代码
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

//实例化 DefaultAppearance 对象
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
//创建注释
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
//指定注释的内容
freetext.Contents = "Free Text";
//添加anoot到页面的注释集合
pdfDocument.Pages[1].Annotations.Add(freetext);
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
//保存更新的文档
pdfDocument.Save(dataDir);            
```
