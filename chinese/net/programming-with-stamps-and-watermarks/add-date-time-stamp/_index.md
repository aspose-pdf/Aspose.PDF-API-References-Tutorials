---
title: 添加日期时间戳
linktitle: 添加日期时间戳
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 轻松地将日期和时间戳添加到您的 PDF 文档。
type: docs
weight: 10
url: /zh/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
在本文中，我们将带您一步步了解如何使用 Aspose.PDF for .NET 添加日期和时间戳。我们将向您展示如何使用提供的 C# 源代码向现有 PDF 文档添加日期和时间戳。

## 要求

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 在您的项目中下载并引用了用于 .NET 的 Aspose.PDF 库。

## 第 1 步：设置环境

在向 PDF 文档添加日期和时间戳之前，您需要设置开发环境。以下是要遵循的步骤：

1. 打开您最喜欢的 IDE（集成开发环境）。
2. 创建一个新的 C# 项目。
3. 确保您已添加对 .NET 的 Aspose.PDF 库的引用。

## 第 2 步：添加 Aspose.PDF 库

.NET 的 Aspose.PDF 库需要在您的项目中处理 PDF 文档。

## 第 3 步：加载 PDF 文档

添加日期和时间戳的第一步是将现有的 PDF 文档加载到您的项目中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

请务必将“您的文档目录”替换为您的 PDF 文档所在目录的实际路径。

## 第 4 步：创建日期和时间戳

现在您已经上传了文档

  PDF，您可以创建要添加的日期和时间戳。方法如下：

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

//创建文本缓冲区
TextStamp textStamp = new TextStamp(annotationText);
```

上面的代码创建了一个包含当前日期和时间的新文本缓冲区。

## 第 5 步：配置图章属性

在将图章添加到 PDF 文档之前，您可以配置图章的各种属性，例如边距、水平和垂直对齐方式等。方法如下：

```csharp
//设置缓冲区属性
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

您可以根据需要调整这些属性。

## 第 6 步：将图章添加到 PDF

现在日期和时间戳已准备就绪，您可以将其添加到 PDF 文档的特定页面。就是这样：

```csharp
//将图章添加到页面的图章集
pdfDocument.Pages[1].AddStamp(textStamp);
```

上面的代码将图章添加到 PDF 文档的第一页。如果需要，您可以指定另一个页面。

## 第 7 步：保存输出文档

添加日期和时间戳后，您可以保存修改后的 PDF 文档。就是这样：

```csharp
//保存输出文件
pdfDocument.Save(dataDir);
```

上述代码将编辑好的PDF文档保存到指定目录。

### 使用 Aspose.PDF for .NET 添加日期时间戳的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

//创建文本图章
TextStamp textStamp = new TextStamp(annotationText);

//设置图章的属性
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

//在集邮上加盖邮票
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

//保存输出文件
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## 结论

恭喜！您已经学习了如何使用 Aspose.PDF for .NET 添加日期和时间戳。现在您可以将这些知识应用到您自己的项目中，为 PDF 文档添加日期和时间戳。
