---
title: 添加不同的标题
linktitle: 添加不同的标题
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 轻松地将不同的标题添加到 PDF 文档的每一页。
type: docs
weight: 30
url: /zh/net/programming-with-stamps-and-watermarks/adding-different-headers/
---
在本教程中，我们将逐步向您介绍如何使用 Aspose.PDF for .NET 向 PDF 文档添加不同的标题。我们将向您展示如何使用提供的 C# 源代码将自定义标题添加到 PDF 文档的每一页。

## 第 1 步：设置环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 在您的项目中下载并引用了用于 .NET 的 Aspose.PDF 库。

## 第 2 步：加载 PDF 文档

第一步是将现有的 PDF 文档加载到您的项目中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//打开源文档
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "AddingDifferentHeaders.pdf");
```

请务必将“您的文档目录”替换为您的 PDF 文档所在目录的实际路径。

## 第 3 步：创建标头缓冲区

现在您已经上传了 PDF 文档，您可以创建要添加的标题图章。就是这样：

```csharp
//创建三个头缓冲区
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");
```

上面的代码创建了三个包含指定文本的新头缓冲区。

## 第 4 步：配置标头缓冲区属性

在将页眉图章添加到 PDF 文档之前，您可以为每个图章配置不同的属性，例如对齐方式、大小、颜色等。方法如下：

```csharp
//配置第一个头缓冲区
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp1.TextState.FontStyle = FontStyles.Bold;
stamp1.TextState.ForegroundColor = Color.Red;
stamp1.TextState.FontSize = 14;

//第二个头缓冲区的配置
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp2.Zoom = 10;

//配置第三个头缓冲区
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
stamp3.RotateAngle = 35;
stamp3.TextState.BackgroundColor = Color.Pink;
stamp3.TextState.Font = FontRepository.FindFont("Verdana");
```

您可以根据需要为每个标头缓冲区调整这些属性。

## 第 5 步：将页眉标记添加到 PDF

现在标题戳已准备就绪，您可以将它们添加到 PDF 文档的每个特定页面。就是这样：

```csharp
//将标题缓冲区添加到特定页面
doc.Pages[1].AddStamp(stamp1);
doc.Pages[2].AddStamp(stamp2);
doc.Pages[3].AddStamp(stamp3);
```

上面的代码将每个标题标记添加到 PDF 文档的相应页面。

## 第 6 步：保存输出文档

添加页眉戳记后，您可以保存编辑后的 PDF 文档。就是这样：

```csharp
//保存更新的文档
doc.Save(dataDir);
```

上述代码将编辑好的PDF文档保存到指定目录。

### 使用 Aspose.PDF for .NET 添加不同标头的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//开源文档
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddingDifferentHeaders.pdf");

//创建三个邮票
Aspose.Pdf.TextStamp stamp1 = new Aspose.Pdf.TextStamp("Header 1");
Aspose.Pdf.TextStamp stamp2 = new Aspose.Pdf.TextStamp("Header 2");
Aspose.Pdf.TextStamp stamp3 = new Aspose.Pdf.TextStamp("Header 3");

//设置图章对齐方式（将图章放在页面顶部，水平居中）
stamp1.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
stamp1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

//指定字体样式为粗体
stamp1.TextState.FontStyle = FontStyles.Bold;

//设置文本前景色信息为红色
stamp1.TextState.ForegroundColor = Color.Red;

//指定字体大小为 14
stamp1.TextState.FontSize = 14;

//现在我们需要将第二个图章对象的垂直对齐方式设置为顶部
stamp2.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

//将图章的水平对齐信息设置为居中对齐
stamp2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

//设置图章对象的缩放系数
stamp2.Zoom = 10;

//设置第三个图章对象的格式
//将图章对象的垂直对齐信息指定为 TOP
stamp3.VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

//将图章对象的水平对齐信息设置为居中对齐
stamp3.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;

//设置图章对象的旋转角度
stamp3.RotateAngle = 35;

//将粉红色设置为图章的背景颜色
stamp3.TextState.BackgroundColor = Color.Pink;

//将 stamp 的字体信息更改为 Verdana
stamp3.TextState.Font = FontRepository.FindFont("Verdana");

//在第一页上添加第一枚邮票；
doc.Pages[1].AddStamp(stamp1);

//在第二页添加第二个邮票；
doc.Pages[2].AddStamp(stamp2);

//在第三页上添加了第三个邮票。
doc.Pages[3].AddStamp(stamp3);
dataDir = dataDir + "multiheader_out.pdf";

//保存更新的文档
doc.Save(dataDir);
Console.WriteLine("\nDifferent headers added successfully.\nFile saved at " + dataDir);

```

## 结论

恭喜！您已经学习了如何使用 Aspose.PDF for .NET 向 PDF 文档的每一页添加不同的页眉。您现在可以将这些知识应用到您自己的项目中，为您的 PDF 文档自定义标题。
