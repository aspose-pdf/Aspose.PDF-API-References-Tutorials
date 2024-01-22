---
title: 添加 PDF 注释
linktitle: 添加注释
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用此 C# 源代码通过 Aspose.PDF for .NET 添加文本 PDF 注释。使用特定的细节和图标自定义您的注释。
type: docs
weight: 10
url: /zh/net/annotations/addannotation/
---
向 PDF 文档添加注释是一项强大的功能，可以增强协作和审阅流程。 Aspose.PDF for .NET 可以轻松地使用 C# 以编程方式向 PDF 文档添加注释。在本指南中，我们将逐步解释如何使用 Aspose.PDF for .NET 向 PDF 文档添加注释。

## 步骤 1：创建一个新项目并安装 Aspose.PDF for .NET

在开始编写添加注释的代码之前，我们需要创建一个新项目并安装 Aspose.PDF for .NET。要安装 Aspose.PDF for .NET，请按照下列步骤操作：

1. 打开 Visual Studio 并创建一个新的 C# 项目。
2. 在解决方案资源管理器中右键单击该项目，然后选择“管理 NuGet 包”。
3. 搜索“Aspose.PDF”并选择“安装”。

安装完成后，我们就可以开始编写代码了。

## 第 2 步：打开 PDF 文档

添加注释的第一步是打开 PDF 文档。我们可以使用下面的代码来打开该文档：

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

在此代码中，我们指定要打开的 PDF 文档的路径。确保将“您的数据目录”替换为数据目录的实际路径。

## 第 3 步：创建注释

要添加注释，我们需要创建一个新的实例`TextAnnotation`班级。我们可以使用以下代码来创建新的文本注释：

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

在此代码中，我们在 PDF 文档的第二页上创建一个新的文本注释。我们还设置注释的标题、主题、状态、内容、打开和图标属性。

## 第 4 步：自定义注释

我们可以使用以下命令自定义注释的外观`Border`班级。我们可以使用下面的代码来自定义注释的边框：

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

在此代码中，我们创建一个新的`Border`对象并设置其宽度和虚线属性。然后我们设置`Border`新注释的属性`Border`目的。最后，我们设置`Rect`注释的属性来指定其位置和大小。

## 第 5 步：将注释添加到 PDF 文档

创建并自定义注释后，我们需要将其添加到 PDF 文档中。我们可以使用以下代码为PDF文档添加注释：

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

在此代码中，我们将注释添加到 PDF 文档第二页的注释集合中。

## 第 6 步：保存输出文件

最后，我们需要保存添加了注释的 PDF 文档。我们可以使用以下代码来保存输出文件：

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### 使用 Aspose.PDF for .NET 添加注释的示例源代码


```csharp   
 //文档目录的路径。
string dataDir = "YOUR DATA DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

//创建注释
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

//在页面的注释集合中添加注释
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
//保存输出文件
pdfDocument.Save(dataDir);
```
此代码演示如何使用 Aspose.PDF for .NET 将具有特定标题、主题、状态、内容和图标的文本注释添加到 PDF 页面。您可以根据您的要求修改此代码，以便向 PDF 文档添加注释。只需记住将 YOUR DATA DIRECTORY 替换为 PDF 文件所在的实际目录路径以及要保存输出文件的位置。

## 结论

使用 Aspose.PDF for .NET 向 PDF 文档添加注释为增强文档协作和审阅流程提供了宝贵的工具。通过遵循本文提供的分步指南，开发人员可以将注释功能无缝集成到他们的 C# 应用程序中。

### 常见问题解答

#### 问：使用 Aspose.PDF for .NET 可以添加哪些类型的注释？

答：Aspose.PDF for .NET 支持各种类型的注释，包括文本注释、图章、链接、形状等。开发人员可以自定义这些注释的外观和属性以满足他们的特定需求。

#### 问：我可以为多页 PDF 文档中的特定页面添加注释吗？

答：是的，Aspose.PDF for .NET 允许您指定要添加注释的页面。您可以根据需要选择特定页面或为多个页面添加注释。

#### 问：如何自定义注释的外观？

答：可以使用边框宽度、颜色、破折号样式、文本样式等属性来自定义注释。 Aspose.PDF for .NET 提供了一组丰富的选项来定制注释的外观。

#### 问：是否可以使用 Aspose.PDF for .NET 添加超链接作为注释？

答：是的，您可以使用 Aspose.PDF for .NET 将超链接作为注释添加到 PDF 文档中。超链接注释可用于链接到外部 URL 或同一文档中的特定位置。

#### 问：可以在不改变原始内容的情况下向现有 PDF 文档添加注释吗？

答：是的，Aspose.PDF for .NET 添加注释作为附加元素，而不改变 PDF 文档的原始内容。原始 PDF 内容保持不变。