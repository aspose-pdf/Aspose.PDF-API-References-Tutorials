---
title: 在 PDF 文件中添加文本印记
linktitle: 在 PDF 文件中添加文本印记
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中轻松添加文本图章。
type: docs
weight: 50
url: /zh/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 在 PDF 文件中添加文本图章。我们将向您展示如何使用提供的 C# 源代码将自定义文本图章添加到 PDF 文件的特定页面。

## 第一步：搭建环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 下载用于 .NET 的 Aspose.PDF 库并在您的项目中引用。

## 第 2 步：加载 PDF 文档

第一步是将现有的 PDF 文档加载到您的项目中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

请务必将“您的文档目录”替换为 PDF 文档所在目录的实际路径。

## 第 3 步：创建文本缓冲区

现在您已经上传了 PDF 文档，您可以创建要添加的文本图章。操作方法如下：

```csharp
//创建文本缓冲区
TextStamp textStamp = new TextStamp("Example Stamp");
```

上面的代码创建一个包含指定文本的新文本缓冲区。

## 步骤 4：配置文本图章属性

在将文本图章添加到 PDF 文档之前，您可以配置图章的各种属性，例如背景、位置、旋转、字体、大小等。操作方法如下：

```csharp
//配置文本缓冲区属性
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

您可以根据需要调整这些属性。

## 第 5 步：将文本图章添加到 PDF

现在文本图章已准备就绪，您可以将其添加到 PDF 文档的特定页面。就是这样：

```csharp
//将文本缓冲区添加到特定页面
pdfDocument.Pages[1].AddStamp(textStamp);
```

上面的代码将文本图章添加到 PDF 文档的第一页。如果需要，您可以指定另一个页面。

## 步骤 6：保存输出文档

添加文本图章后，您可以保存编辑后的 PDF 文档。就是这样：

```csharp
//保存输出文档
pdfDocument.Save(dataDir);
```

上面的代码将修改后的PDF文档保存在指定目录中。

### 使用 Aspose.PDF for .NET 添加文本图章的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

//创建文本印章
TextStamp textStamp = new TextStamp("Sample Stamp");

//设置图章是否为背景
textStamp.Background = true;

//设置原点
textStamp.XIndent = 100;
textStamp.YIndent = 100;

//旋转图章
textStamp.Rotate = Rotation.on90;

//设置文本属性
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

//添加图章到特定页面
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

//保存输出文档
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## 结论

恭喜！您已经了解了如何使用 Aspose.PDF for .NET 添加文本图章。现在您可以将这些知识应用到您自己的项目中，以将自定义文本图章添加到 PDF 文档中。

### 在 PDF 文件中添加文本印记的常见问题解答

#### 问：使用 Aspose.PDF for .NET 在 PDF 文件中添加文本图章的目的是什么？

答：添加文本图章允许您将自定义文本放置在 PDF 文档的特定页面上。此功能对于添加标签、注释、水印或任何其他文本信息以增强文档内容并提供附加上下文非常有用。

#### 问：我可以自定义文本图章的外观，例如字体、大小、颜色和旋转吗？

答：是的，您可以完全自定义文本图章的外观。提供的C#源代码演示了如何设置各种属性`TextStamp`对象，包括字体、字体大小、字体样式、文本颜色、背景颜色和旋转。

#### 问：是否可以在同一 PDF 文档的不同页面上添加多个文本印记？

答：当然，您可以将多个文本图章添加到同一 PDF 文档的不同页面。本教程提供的代码允许您指定添加文本图章的目标页面，使其适用于文档中的不同页面。

#### 问：如何指定 PDF 文档中文本印记的位置？

 A：您可以通过修改`XIndent`和`YIndent`的属性`TextStamp`目的。这些属性定义图章左上角相对于页面原点的坐标。

#### 问：我可以将此方法应用于现有 PDF 文档来添加文本图章吗？

答：是的，您可以将此方法应用于现有的 PDF 文档来添加文本图章。本教程提供的代码演示了如何加载现有 PDF 文档并将文本图章添加到特定页面。

#### 问：我可以为文本图章添加背景色和前景色吗？

答：是的，您可以为文本图章添加背景色和前景色。通过设置`Background`财产给`true`，您可以为文本图章提供彩色背景。此外，您还可以设置`TextState.ForegroundColor`属性来指定文本本身的颜色。

#### 问：如何确保文本印记不会遮盖 PDF 文档的底层内容？

答：添加文本印记时，请注意其位置，以确保它不会遮挡关键信息或对文档的可读性产生负面影响。您可以调整`XIndent`和`YIndent`属性来适当定位文本图章。

#### 问：我可以使用此方法添加文本以外的图章，例如图像或徽标吗？

答：本教程重点介绍添加文本图章，但您也可以使用 Aspose.PDF for .NET 以类似方式添加其他类型的图章，例如图像或徽标。该过程涉及创建适当的图章对象并配置其属性。

#### 问：如何自动执行向多个 PDF 文档添加文本图章的过程？

答：您可以通过创建一个脚本或程序来自动执行向多个 PDF 文档添加文本印记的过程，该脚本或程序会迭代文档列表并对每个文档应用相同的文本印记过程。