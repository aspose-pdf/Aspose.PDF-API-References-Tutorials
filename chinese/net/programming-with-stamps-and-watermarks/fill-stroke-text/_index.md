---
title: 填充描边文字
linktitle: 填充描边文字
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 轻松地在 PDF 文档中填充和勾勒文本。
type: docs
weight: 90
url: /zh/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
在本教程中，我们将逐步向您介绍如何使用 Aspose.PDF for .NET 在 PDF 文档中填充和勾勒文本。我们将向您展示如何使用提供的 C# 源代码将填充和轮廓颜色应用于 PDF 文档中的文本。

## 第 1 步：设置环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 在您的项目中下载并引用了用于 .NET 的 Aspose.PDF 库。

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

上面的代码创建了一个新的 TextState 对象并设置了轮廓颜色以及文本的呈现方式。

## 第 3 步：加载 PDF 文档

现在 TextState 对象已准备就绪，我们可以在要应用文本填充和轮廓的位置加载 PDF 文档。就是这样：

```csharp
//加载 PDF 文档作为输入
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

上面的代码使用 Aspose.PDF.Facades 库中的 PdfFileStamp 类加载现有的 PDF 文档。

## 第 4 步：为文本添加填充和描边

现在 PDF 文档已加载，我们可以为文本添加填充和轮廓。就是这样：

```csharp
//使用定义的文本和属性创建图章 (Stamp)
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

//将图章添加到文档
fileStamp.AddStamp(stamp);
```

上面的代码创建了一个具有指定文本和定义的 Fill 和 Stroke 属性的 Stamp。

## 第 5 步：保存输出文档

添加文本戳记后，我们可以保存修改后的 PDF 文档。就是这样：

```csharp
//保存修改后的文件
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

上述代码将编辑好的PDF文档保存到指定目录。

### 使用 Aspose.PDF for .NET 填充笔划文本的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//创建 TextState 对象以传递高级属性
TextState ts = new TextState();

//设置描边颜色
ts.StrokingColor = Color.Gray;

//设置文本渲染模式
ts.RenderingMode = TextRenderingMode.StrokeText;

//加载输入的 PDF 文档
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

//绑定文本状态
stamp.BindTextState(ts);

//设置 X,Y 原点
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

//添加邮票
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## 结论

恭喜！您已经学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中填充和勾勒文本。现在您可以应用这些知识来自定义 PDF 文档中的填充和轮廓颜色。
