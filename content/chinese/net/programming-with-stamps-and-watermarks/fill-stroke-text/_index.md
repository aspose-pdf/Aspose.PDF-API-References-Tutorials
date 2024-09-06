---
title: 在 PDF 文件中填充描边文本
linktitle: 在 PDF 文件中填充描边文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 轻松填充和勾勒 PDF 文件中的文本。
type: docs
weight: 90
url: /zh/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 在 PDF 文件中填充和勾勒文本轮廓。我们将向您展示如何使用提供的 C# 源代码将填充和勾勒颜色应用于 PDF 文件中的文本。

## 步骤 1：设置环境

开始之前，请确保您已准备好以下物品：

- 已安装的 .NET 开发环境。
- 已下载并引用适用于 .NET 的 Aspose.PDF 库到您的项目中。

## 步骤 2：创建 TextState 对象

第一步是创建一个 TextState 对象来传递高级属性。操作方法如下：

```csharp
//创建 TextState 对象来传输高级属性
TextState ts = new TextState();

//设置轮廓颜色
ts.StrokingColor = Color.Gray;

//定义文本渲染模式
ts.RenderingMode = TextRenderingMode.StrokeText;
```

上述代码创建了一个新的 TextState 对象并设置了轮廓颜色以及文本的呈现方式。

## 步骤 3：加载 PDF 文档

现在 TextState 对象已准备就绪，我们可以将 PDF 文档加载到我们想要应用文本填充和轮廓的位置。操作方法如下：

```csharp
//加载 PDF 文档作为输入
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

上述代码使用 Aspose.PDF.Facades 库中的 PdfFileStamp 类加载现有的 PDF 文档。

## 步骤 4：为文本添加填充和描边

现在 PDF 文档已加载，我们可以为文本添加填充和轮廓。操作方法如下：

```csharp
//创建具有定义文本和属性的印章（Stamp）
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

//绑定 TextState 对象
stamp.BindTextState(ts);

//设置原点 X, Y
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

//在文件上加盖印章
fileStamp.AddStamp(stamp);
```

上述代码使用指定的文本以及定义的填充和描边属性创建了一个印章。

## 步骤 5：保存输出文档

添加文本标记后，我们可以保存修改后的 PDF 文档。操作方法如下：

```csharp
//保存修改后的文档
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

上述代码将编辑后的PDF文档保存到指定目录。

### 使用 Aspose.Pdf for .NET 填充描边文本的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//创建 TextState 对象来传输高级属性
TextState ts = new TextState();

//设置描边颜色
ts.StrokingColor = Color.Gray;

//设置文本渲染模式
ts.RenderingMode = TextRenderingMode.StrokeText;

//加载输入 PDF 文档
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

//绑定 TextState
stamp.BindTextState(ts);

//设置 X,Y 原点
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

恭喜！您已经学会了如何使用 Aspose.PDF for .NET 在 PDF 文档中填充和勾勒文本轮廓。现在您可以运用这些知识自定义 PDF 文档中的填充和轮廓颜色。

### PDF 文件中填充描边文本的常见问题解答

#### 问：在 PDF 文档中填充和勾勒文本是什么意思？什么时候需要这样做？

答：在 PDF 文档中填充和勾勒文本轮廓涉及将颜色应用于文本字符内部（填充）和文本周围的边框（勾勒）。这可用于增强文本的视觉效果、强调或突出显示 PDF 中的特定内容。

#### 问：提供的 C# 源代码如何实现 PDF 文件中文本的填充和描边？

答：提供的源代码演示了如何创建`TextState`对象定义高级文本属性，例如轮廓颜色和渲染模式。然后使用 Aspose.PDF.Facades 加载现有 PDF 文档，创建包含具有指定填充和描边属性的文本的印章，并将印章添加到文档中。

#### 问：`TextState` object in the code?

答：`TextState`对象用于定义高级文本属性，包括文本轮廓（描边）的颜色和渲染模式。它允许您自定义文本在描边和填充方面的显示方式。

#### 问：我可以对同一文本的不同部分应用不同的填充和轮廓颜色吗？

答：是的，你可以修改代码来创建不同的`TextState`具有不同填充和轮廓颜色的对象，并使用单独的`Stamp`对象。

#### 问：我可以将填充和轮廓颜色应用于 PDF 文档中已有的文本吗？

答：是的，您可以使用类似的原理将填充和轮廓颜色应用于 PDF 文档中的现有文本，方法是选择适当的文本对象并将其添加为具有所需颜色的图章`TextState`特性。

#### 问：如何调整填充和轮廓文本的不透明度和混合？

答：提供的代码允许您使用以下代码设置印章的不透明度和混合属性：`Opacity`和`BlendingSpace`属性。您可以调整这些值以实现所需的视觉效果。

#### 问：如何对同一 PDF 文档中的多个印章应用不同的填充和轮廓颜色？

答：您可以创建多个`TextState`具有不同填充和轮廓颜色的对象，然后创建单独的`Stamp`为每组文本添加不同的颜色对象。使用`PdfFileStamp`班级。

#### 问：我可以使用 Arial 以外的字体来表示轮廓和填充的文本吗？

答：是的，您可以通过修改字体名称参数来更改字体。`FormattedText`创建图章时，可以使用构造函数。您可以使用系统上可用的任何字体。

#### 问：如何修改轮廓文字和填充文字的旋转角度？

答：提供的代码允许您使用`Rotation`属性。您可以调整此属性来指定文本所需的旋转角度。

#### 问：如何控制页面上轮廓文字和填充文字的位置和大小？

答：您可以使用`SetOrigin`方法`Stamp`对象来设置印章在页面上的位置的 X 和 Y 坐标。此外，您还可以在`FormattedText`构造函数来控制文本的大小。