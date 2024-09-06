---
title: 在 PDF 文件中添加日期时间戳
linktitle: 在 PDF 文件中添加日期时间戳
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 轻松在 PDF 文件中添加日期和时间戳。
type: docs
weight: 10
url: /zh/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
在本文中，我们将逐步指导您如何使用 Aspose.PDF for .NET 在 PDF 文件中添加日期和时间戳。我们将向您展示如何使用提供的 C# 源代码将日期和时间戳添加到现有 PDF 文件。

## 要求

开始之前，请确保您已准备好以下物品：

- 已安装的 .NET 开发环境。
- 已下载并引用适用于 .NET 的 Aspose.PDF 库到您的项目中。

## 步骤 1：设置环境

在向 PDF 文档添加日期和时间戳之前，您需要设置开发环境。请按照以下步骤操作：

1. 打开您最喜欢的 IDE（集成开发环境）。
2. 创建一个新的 C# 项目。
3. 确保您已添加对 .NET 的 Aspose.PDF 库的引用。

## 第 2 步：添加 Aspose.PDF 库

需要 .NET 的 Aspose.PDF 库来处理项目中的 PDF 文档。

## 步骤 3：加载 PDF 文档

添加日期和时间戳的第一步是将现有 PDF 文档加载到项目中。操作方法如下：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

请务必将“您的文档目录”替换为 PDF 文档所在目录的实际路径。

## 步骤 4：创建日期和时间戳

现在您已上传了文档

  PDF，您可以创建要添加的日期和时间戳。操作方法如下：

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

//创建文本缓冲区
TextStamp textStamp = new TextStamp(annotationText);
```

上面的代码创建了一个包含当前日期和时间的新文本缓冲区。

## 步骤 5：配置图章属性

在将图章添加到 PDF 文档之前，您可以配置图章的各种属性，例如边距、水平和垂直对齐方式等。操作方法如下：

```csharp
//设置缓冲区属性
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

您可以根据需要调整这些属性。

## 步骤 6：将图章添加到 PDF

现在日期和时间戳已准备好，您可以将其添加到 PDF 文档的特定页面。操作方法如下：

```csharp
//将邮票添加到页面的邮票收藏中
pdfDocument.Pages[1].AddStamp(textStamp);
```

上述代码将图章添加到 PDF 文档的第一页。如有必要，您可以指定其他页面。

## 步骤 7：保存输出文档

添加日期和时间戳后，您可以保存修改后的 PDF 文档。操作方法如下：

```csharp
//保存输出文档
pdfDocument.Save(dataDir);
```

上述代码将编辑后的PDF文档保存到指定目录。

### 使用 Aspose.PDF for .NET 添加日期时间戳的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

//创建文本印章
TextStamp textStamp = new TextStamp(annotationText);

//设置图章的属性
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

//在集邮册上添加邮票
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

//保存输出文档
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## 结论

恭喜！您已经学会了如何使用 Aspose.PDF for .NET 添加日期和时间戳。现在您可以将这些知识应用到自己的项目中，为 PDF 文档添加日期和时间戳。

### 在 PDF 文件中添加日期时间戳的常见问题解答

#### 问：使用 Aspose.PDF for .NET 向 PDF 文档添加日期和时间戳有什么目的？

答：在 PDF 文档中添加日期和时间戳可显示文档的修改或创建时间，从而增强其信息价值。此功能可用于跟踪文档更改，并为文档历史记录提供参考点。

#### 问：我可以自定义日期和时间戳的格式以满足特定要求吗？

答：是的，您可以根据自己的喜好自定义日期和时间戳的格式。提供的 C# 源代码使用`DateTime.Now.ToString()`方法以特定格式生成时间戳。您可以修改此代码以根据需要格式化时间戳。

#### 问：是否可以将日期和时间戳添加到 PDF 页面上的特定位置？

答：当然可以，您可以通过修改`TextStamp`对象。本教程中提供的代码演示了如何设置边距、对齐方式和垂直定位等属性。

#### 问：我可以在同一 PDF 文档的不同页面上添加多个日期和时间戳吗？

答：是的，您可以向同一 PDF 文档的不同页面添加多个日期和时间戳。只需重复创建`TextStamp`对象并为每个所需页面配置其属性。

#### 问：如何更改日期和时间戳文本的字体、大小或颜色？

答：要修改日期和时间戳文本的字体、大小或颜色，您可以自定义`DefaultAppearance`用于创建的对象`TextStamp`调整字体名称、大小和颜色值以实现所需的外观。

#### 问：是否可以使用 Aspose.PDF for .NET 向 PDF 文档添加其他类型的注释或印章？

答：是的，Aspose.PDF for .NET 提供了多种可添加到 PDF 文档的注释类型，包括文本注释、图章、线条、形状等。您可以浏览 Aspose.PDF 文档以获取有关使用注释的更多详细信息。

#### 问：在 PDF 文档中添加日期和时间戳有什么限制或注意事项吗？

答：虽然添加日期和时间戳很简单，但请考虑文档的布局和现有内容等因素。确保时间戳的位置不会遮挡重要信息或影响文档的可读性。

#### 问：如何将此方法集成到我自己的项目中，以便向 PDF 文档添加日期和时间戳？

答：要集成此方法，请按照提供的步骤操作并调整代码以适合您的项目结构。您可以向现有 PDF 文档添加日期和时间戳，以增强其实用性并提供清晰的更改时间表。

#### 问：我可以自动向多个 PDF 文档添加日期和时间戳吗？

答：是的，您可以通过创建一个脚本或程序来自动化向多个 PDF 文档添加日期和时间戳的过程，该脚本或程序会遍历文档列表并对每个文档应用相同的标记过程。