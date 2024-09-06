---
title: 添加 PDF 注释
linktitle: 添加注释
second_title: Aspose.PDF for .NET API 参考
description: 按照本分步指南使用 Aspose.PDF for .NET 轻松向您的 PDF 添加自定义注释。使用特定细节和图标自定义您的注释。
type: docs
weight: 10
url: /zh/net/annotations/addannotation/
---
## 介绍

注释是丰富 PDF 文档的好方法，使其具有交互性和信息性。无论您是为合作者留下注释还是为读者添加额外信息，注释都是必不可少的。在本教程中，我们将深入探讨使用 Aspose.PDF for .NET 添加 PDF 注释的过程。我们将分解每个步骤，以便在本指南结束时，您将成为在 PDF 文件中嵌入注释的专家。让我们开始吧！

## 先决条件

在深入研究代码之前，让我们确保您拥有所需的一切：

-  Aspose.PDF for .NET：确保已安装 Aspose.PDF 库。您可以从[Aspose.PDF for .NET 下载页面](https://releases.aspose.com/pdf/net/).
- 开发环境：Visual Studio 或您选择的任何其他 C# IDE。
- C# 基础知识：本指南假设您熟悉 C# 编程。
- PDF 文档：您将添加注释的示例 PDF 文件。

如果你还没有 Aspose.PDF 库，你可以从上面的链接获取它并开始[免费试用](https://releases.aspose.com/)或者买一个[执照](https://purchase.aspose.com/buy). 

## 导入包

在开始编码之前，请确保已导入必要的命名空间：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

这些命名空间提供对 PDF 操作和注释所需的类和方法的访问。

## 步骤 1：加载 PDF 文档

首先，您需要加载要添加注释的 PDF 文档。

```csharp
//文档目录的路径。
string dataDir = "YOUR DATA DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

事情是这样的：你指定 PDF 文件的存储目录，然后使用`Document`Aspose.PDF 提供的类。此步骤至关重要，因为如果不加载文档，您就无法对其进行任何更改。

## 步骤 2：创建注释

### 定义注释属性
现在，让我们创建注释本身。我们将使用`TextAnnotation`，非常适合在您的 PDF 中添加评论或注释。

```csharp
//创建注记
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

在此代码片段中：
- 位置和大小：`Rectangle`类别定义注释在页面上出现的位置及其尺寸。
- 标题、主题和内容：这些属性允许您指定注释的内容和内容。
- 图标：`TextIcon.Key`为注释设置图标，使其更具视觉吸引力。

## 步骤 3：自定义注释的外观

接下来，让我们通过添加边框和调整其外观来使该注释脱颖而出。

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

以下是具体情况：
- 边界：我们创造一个`Border`对象并将其宽度设置为 5，为我们的注释提供突出的轮廓。
- 虚线图案：`Dash`属性可让您创建虚线边框，为注释添加一些样式。

## 步骤 4：将注释添加到 PDF 页面

创建和自定义注释后，就可以将其添加到您的 PDF 页面了。

```csharp
//将注释添加到页面的注释集合中
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

此代码将注释添加到 PDF 的第一页。`Annotations`集合包含特定页面的所有注释，此步骤可确保您的新注释是该集合的一部分。

## 步骤 5：保存更新的 PDF 文档

最后，让我们保存文档，以便永久添加您的注释。

```csharp
//保存输出文件
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nAnnotation added successfully.\nFile saved at " + dataDir);
```

通过使用新名称保存文档（`AddAnnotation_out.pdf`)，您保留原始文件并生成一个添加了注释的新文件。控制台消息确认一切成功，您现在可以在指定的目录中找到带注释的 PDF。

## 结论

向 PDF 添加注释不仅是一项强大的功能；使用 Aspose.PDF for .NET 也非常简单。无论您是标记文档以供审阅还是添加注释以供将来参考，本指南都涵盖了您需要了解的所有内容。通过遵循这些步骤，您可以创建自定义注释来丰富您的 PDF，使其更加实用和具有交互性。

## 常见问题解答

### 我可以使用 Aspose.PDF for .NET 添加哪些类型的注释？
您可以添加各种类型的注释，包括文本、链接、突出显示和图章注释等。

### 我可以自定义注释的外观吗？
当然可以！您可以自定义注释的大小、颜色、边框，甚至图标。

### 是否可以在单个页面添加多个注释？
是的，您可以在 PDF 的任何页面上添加任意数量的注释。

### 添加注释后可以删除吗？
是的，可以使用`Annotations.Delete`Aspose.PDF 提供的方法。

### 我需要许可证才能使用 Aspose.PDF for .NET 吗？
是的，要解锁所有功能并避免任何限制，你需要[执照](https://purchase.aspose.com/buy)。您还可以获得[临时执照](https://purchase.aspose.com/temporary-license/)进行评估。