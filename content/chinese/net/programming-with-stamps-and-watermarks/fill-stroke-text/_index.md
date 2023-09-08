---
title: 在 PDF 文件中填充描边文本
linktitle: 在 PDF 文件中填充描边文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 轻松填充 PDF 文件中的文本并为其添加轮廓。
type: docs
weight: 90
url: /zh/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 在 PDF 文件中填充和轮廓文本。我们将向您展示如何使用提供的 C# 源代码将填充和轮廓颜色应用于 PDF 文件中的文本。

## 第一步：搭建环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 下载用于 .NET 的 Aspose.PDF 库并在您的项目中引用。

## 第 2 步：创建 TextState 对象

第一步是创建一个 TextState 对象来传递高级属性。就是这样：

```csharp
//创建 TextState 对象以传递高级属性
TextState ts = new TextState();

//设置轮廓颜色
ts.StrokingColor = Color.Gray;

//定义文本渲染模式
ts.RenderingMode = TextRenderingMode.StrokeText;
```

上面的代码创建一个新的 TextState 对象并设置轮廓颜色以及文本的呈现方式。

## 第 3 步：加载 PDF 文档

现在 TextState 对象已准备就绪，我们可以在要应用文本填充和轮廓的位置加载 PDF 文档。就是这样：

```csharp
//加载 PDF 文档作为输入
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

上面的代码使用 Aspose.PDF.Facades 库中的 PdfFileStamp 类加载现有 PDF 文档。

## 第 4 步：为文本添加填充和描边

现在 PDF 文档已加载，我们可以向文本添加填充和轮廓。就是这样：

```csharp
//使用定义的文本和属性创建图章（Stamp）
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

//绑定 TextState 对象
stamp.BindTextState(ts);

//设置原点X、Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

//将图章添加到文档中
fileStamp.AddStamp(stamp);
```

上面的代码创建一个具有指定文本和定义的填充和描边属性的图章。

## 步骤5：保存输出文档

添加文本图章后，我们就可以保存修改后的PDF文档。就是这样：

```csharp
//保存修改后的文档
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

上述代码将编辑后的PDF文档保存到指定目录。

### 使用 Aspose.PDF for .NET 填充描边文本的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//创建 TextState 对象以传递高级属性
TextState ts = new TextState();

//设置描边颜色
ts.StrokingColor = Color.Gray;

//设置文本渲染模式
ts.RenderingMode = TextRenderingMode.StrokeText;

//加载输入 PDF 文档
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

//绑定文本状态
stamp.BindTextState(ts);

//设置X、Y原点
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

//添加图章
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## 结论

恭喜！您已经学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中填充和轮廓文本。现在，您可以应用这些知识来自定义 PDF 文档中的填充和轮廓颜色。

### PDF 文件中填充描边文本的常见问题解答

#### 问：在 PDF 文档中填充和概述文本意味着什么？何时需要这样做？

答：在 PDF 文档中填充和轮廓文本涉及将颜色应用于文本字符的内部（填充）和文本周围的边框（轮廓）。这可用于增强文本的视觉外观、强调或突出显示 PDF 中的特定内容。

#### 问：提供的C#源代码如何完成PDF文件中的文本填充和轮廓显示？

答：提供的源代码演示了如何创建`TextState`对象来定义高级文本属性，例如轮廓颜色和渲染模式。然后，它使用 Aspose.PDF.Facades 加载现有 PDF 文档，创建包含具有指定填充和描边属性的文本的图章，并将图章添加到文档中。

#### 问：这样做的目的是什么`TextState` object in the code?

答： 的`TextState`对象用于定义高级文本属性，包括文本轮廓（描边）的颜色和渲染模式。它允许您自定义文本在描边和填充方面的显示方式。

#### 问：我可以对同一文本的不同部分应用不同的填充和轮廓颜色吗？

 A：是的，您可以修改代码来创建不同的`TextState`具有不同填充和轮廓颜色的对象，并使用单独的方法将它们应用到文本的特定部分`Stamp`对象。

#### 问：我可以将填充颜色和轮廓颜色应用到 PDF 文档中已有的文本吗？

答：是的，您可以使用类似的原理将填充和轮廓颜色应用到 PDF 文档中的现有文本，方法是选择适当的文本对象并将其添加为具有所需颜色的图章。`TextState`特性。

#### 问：如何调整填充文本和轮廓文本的不透明度和混合？

答：提供的代码允许您使用以下命令设置图章的不透明度和混合属性`Opacity`和`BlendingSpace`属性，分别。您可以调整这些值以达到所需的视觉效果。

#### 问：如何对同一 PDF 文档中的多个图章应用不同的填充和轮廓颜色？

答：可以创建多个`TextState`具有不同填充和轮廓颜色的对象，然后创建单独的`Stamp`每组文本的对象具有不同的颜色。使用以下命令将这些图章添加到同一 PDF 文档中`PdfFileStamp`班级。

#### 问：我可以使用 Arial 以外的字体来显示轮廓文本和填充文本吗？

 A：是的，您可以通过修改字体名称参数来更改字体`FormattedText`创建图章时的构造函数。您可以使用系统上可用的任何字体。

#### 问：如何修改轮廓文本和填充文本的旋转角度？

答：提供的代码允许您使用设置图章的旋转角度`Rotation`财产。您可以调整此属性来指定文本所需的旋转角度。

#### 问：如何控制页面上轮廓文本和填充文本的位置和大小？

答：您可以使用`SetOrigin`的方法`Stamp`对象设置页面上图章位置的 X 和 Y 坐标。另外，您还可以调整字体大小`FormattedText`构造函数来控制文本的大小。