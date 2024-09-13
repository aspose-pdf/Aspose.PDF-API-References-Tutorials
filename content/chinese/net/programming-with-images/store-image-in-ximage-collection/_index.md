---
title: 将图像存储在 XImage 集合中
linktitle: 将图像存储在 XImage 集合中
second_title: Aspose.PDF for .NET API 参考
description: 通过本完整的分步指南了解如何使用 Aspose.PDF for .NET 将图像存储在 XImage 集合中。
type: docs
weight: 290
url: /zh/net/programming-with-images/store-image-in-ximage-collection/
---
## 介绍

在当今的数字时代，以编程方式处理和操作文档对于许多应用程序来说都是必不可少的。Aspose.PDF for .NET 使开发人员能够轻松处理 PDF 文件，增强工作流程并实现动态内容的创建。在本指南中，我们将深入研究将图像存储在 XImage 集合中的过程，这是一项重要功能，可让您将视觉效果直接嵌入 PDF。准备好踏上创建精彩内容的旅程吧。

## 先决条件

在深入研究代码和流程之前，您需要确保已准备好以下几件事：

- .NET 环境：您的机器上应该安装有 .NET Framework。根据项目要求选择合适的版本。
- Aspose.PDF for .NET：确保您拥有 Aspose.PDF 库。您可以从以下网址下载[这里](https://releases.aspose.com/pdf/net/)或开始免费试用[这里](https://releases.aspose.com/).
- 图像文件：您还需要一个要存储在 PDF 中的图像文件（如 JPG 或 PNG）。在本例中，我们将使用名为“aspose-logo.jpg”的文件。
- 对 C# 的基本了解：熟悉 C# 编程将帮助您顺利跟上。

## 导入包

要开始使用 Aspose.PDF for .NET，您需要导入所需的命名空间。此步骤为利用库提供的所有功能奠定了基础。

```csharp
using System;
using System.IO;
using Aspose.Pdf.Operators;
```

通过导入这些命名空间，您可以启用 Aspose.PDF 中的各种功能，包括文档创建、图像处理等。

让我们将其分解为易于管理的步骤，以便您更轻松地遵循。

## 步骤 1：设置文档目录

您需要做的第一件事是什么？定义文档的存放位置。您需要设置一个变量来保存文档目录的路径。这是您的 PDF 的保存位置。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; //替换为您的实际文档目录。
```

## 第 2 步：初始化文档

现在，是时候创建一个新的 PDF 文档了。这一步是您的 PDF 开始发挥作用的地方。 

```csharp
Aspose.Pdf.Document document = new Document();
```

在这里，我们实例化一个新的 Document 对象，将其作为画布。

## 步骤 3：添加新页面

每件杰作都需要一块画布，对吧？在我们的例子中，我们需要一个在文档中工作的页面。

```csharp
document.Pages.Add();
Page page = document.Pages[1]; //获取第一页。
```

我们正在向文档添加一个新页面。现在，我们将对该页面进行操作。

## 步骤 4：加载图像文件

接下来，您需要将图像加载到程序中。此步骤与打开一本书阅读非常相似；您需要先访问内容，然后才能使用它。

```csharp
using (FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open))
{
```

此行将图像文件作为流打开，使我们能够操作并将其嵌入到 PDF 中。

## 步骤 5：将图像添加到页面资源

现在您已经准备好了图像，是时候将其添加到页面资源中了，本质上就是告诉 PDF，“嘿，我有一张很酷的图像想让你记住！”

```csharp
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

此代码完成了将图像添加到 PDF 并将其分配给`XImage`我们稍后可以引用的变量。

## 步骤 6：准备绘制图像

接下来是有趣的部分——在页面上定位图像。您需要设置坐标，以便将图像准确地放置在您想要的位置。

```csharp
page.Contents.Add(new GSave());
```

此行保存图形状态以供以后恢复。这就像在我们更改任何内容之前拍摄事物设置情况的快照。

## 步骤 7：定义图像位置和大小

现在，定义您想要放置图像的大小和位置：

```csharp
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
```

此代码块设置了图像所适合的矩形的尺寸，本质上就是为图像在页面上提供一个位置。

## 步骤 8：创建变换矩阵 

为了控制图像的放置方式，我们将定义一个变换矩阵。这将控制图像在目标坐标上的显示方式。

```csharp
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

想象一下，在您踏上旅程之前绘制一张地图。它有助于确定图像在页面上的显示方式。

## 步骤 9：将图像放置在页面上

现在，是时候真正告诉 PDF 将图像放在哪里了。

```csharp
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
```

在这里，我们向 PDF 的内容流添加命令，这些命令将根据我们刚刚建立的矩阵实际绘制图像。

## 步骤 10：保存文档

最后，我们可以保存我们的杰作了！这是您所有的辛勤工作汇集成有形成果的时刻。

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

您已告知 Aspose.PDF 使用提供的文件名保存文档。运行此代码时，您会在指定目录中找到新创建的 PDF 文件，其中包含嵌入的图像。

## 结论

就这样！您已经学会了如何使用 Aspose.PDF for .NET 将图像逐点存储在 XImage 集合中。看到您的代码成形并生成有用的东西，难道不令人欣慰吗？无论您是构建应用程序还是只想自动化报告，本指南都是很好的基础。请记住，Aspose.PDF 的强大功能可以帮助您完成除此以外的众多任务，因此请继续探索！

## 常见问题解答

### Aspose.PDF 支持哪些图像文件格式？
Aspose.PDF 支持各种图像格式，包括 JPG、PNG、BMP 和 GIF。

### 将图像添加到 PDF 时我可以更改其大小吗？
是的，通过调整矩形中定义的坐标，您可以改变PDF中显示的图像的大小。

### 我需要许可证才能使用 Aspose.PDF 吗？
 Aspose 提供免费试用和各种购买选项。您可以找到它们[这里](https://purchase.aspose.com/buy).

### 如果我遇到问题，如何获得支持？
您可以向 Aspose 社区寻求帮助[这里](https://forum.aspose.com/c/pdf/10).

### 有没有办法对添加到 PDF 的图像应用压缩？
是的，在向 PDF 添加图像时，您可以指定图像过滤器类型以使用 Flate 等压缩方法。