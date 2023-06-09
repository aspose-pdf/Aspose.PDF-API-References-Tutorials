---
title: 图片转PDF
linktitle: 图片转PDF
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松将图像转换为 PDF。
type: docs
weight: 180
url: /zh/net/programming-with-images/image-to-pdf/
---

Aspose.PDF for .NET 是一个功能强大的库，允许开发人员使用 C# 或任何 .NET 语言创建、操作和转换 PDF 文档。在本教程中，我们将指导您完成使用 Aspose.PDF for .NET 将图像转换为 PDF 的过程。

## 第 1 步：设置环境

在我们开始之前，请确保您的系统上安装了 Aspose.PDF for .NET。您可以从 Aspose 官方网站下载并安装它。安装后，在您首选的开发环境中创建一个新的 C# 项目。

## 第 2 步：导入所需的库

要在您的项目中使用 Aspose.PDF for .NET，您需要导入必要的库。在 C# 文件的开头添加以下 using 语句：

```csharp
using Aspose.Pdf;
using System.IO;
using System.Drawing;
```

## 第三步：初始化文档对象

在 C# 代码中，第一步是初始化`Document`目的。该对象表示我们将创建的 PDF 文档。将以下代码添加到您的项目中：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

代替`"YOUR DOCUMENT DIRECTORY"`使用您要保存 PDF 文件的实际路径。

## 第 4 步：向文档添加页面

接下来，我们需要向文档添加一个页面。一个页面由`Page`班级。使用以下代码向文档添加页面：

```csharp
Page page = doc.Pages.Add();
```

此代码创建一个新页面并将其添加到`Pages`文档的集合。

## 第 5 步：加载图像文件

要将图像转换为 PDF，我们首先需要加载源图像文件。在此示例中，我们假设图像文件名为`aspose-logo.jpg`并且与 C# 文件位于同一目录中。使用以下代码加载图像文件：

```csharp
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
```

确保更换`"YOUR DOCUMENT DIRECTORY"`与图像文件的实际路径。

## 第 6 步：设置边距和裁剪框

在将图像添加到 PDF 页面之前，我们可以自定义页面布局。例如，我们可以设置边距和裁剪框以适合图像尺寸。使用以下代码调整页面设置：

```csharp
Bitmap b = new Bitmap(mystream);
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page

.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
```

这些设置确保图像适合页面而没有任何额外的边距。

## 第 7 步：创建图像对象

现在，让我们创建一个`Aspose.Pdf.Image`对象来保存图像数据。将以下代码添加到您的项目中：

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
```

该对象将代表我们要添加到 PDF 页面的图像。

## 第 8 步：将图像添加到页面

要将图像添加到 PDF 页面，我们需要将图像数据分配给`ImageStream`的财产`Aspose.Pdf.Image`目的。使用以下代码添加图像：

```csharp
image1.ImageStream = mystream;
page.Paragraphs.Add(image1);
```

在这里，我们将图像流分配给`ImageStream`属性，然后将图像对象添加到`Paragraphs`页面的集合。

## 第 9 步：保存 PDF 文件

一旦我们将图像添加到 PDF 页面，我们就可以保存生成的 PDF 文件。使用以下代码保存文件：

```csharp
dataDir = dataDir + "ImageToPDF_out.pdf";
doc.Save(dataDir);
```

代替`"YOUR DOCUMENT DIRECTORY"`使用所需的输出目录和文件名。

## 第十步：关闭内存流

保存 PDF 文件后，关闭内存流以释放系统资源很重要。添加以下代码以关闭内存流：

```csharp
mystream. Close();
```

## 运行代码并验证输出

您现在已经完成了代码实现。运行代码并验证图像是否已成功转换为 PDF。输出文件应保存在指定目录中。


### 使用 Aspose.PDF for .NET 的图像到 PDF 的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//实例化文档对象
Document doc = new Document();
//将页面添加到文档的页面集合
Page page = doc.Pages.Add();
//将源图像文件加载到 Stream 对象
FileStream fs = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open, FileAccess.Read);
byte[] tmpBytes = new byte[fs.Length];
fs.Read(tmpBytes, 0, int.Parse(fs.Length.ToString()));
MemoryStream mystream = new MemoryStream(tmpBytes);
//使用加载的图像流实例化 BitMap 对象
Bitmap b = new Bitmap(mystream);
//设置边距使图像适合等。
page.PageInfo.Margin.Bottom = 0;
page.PageInfo.Margin.Top = 0;
page.PageInfo.Margin.Left = 0;
page.PageInfo.Margin.Right = 0;
page.CropBox = new Aspose.Pdf.Rectangle(0, 0, b.Width, b.Height);
//创建图像对象
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
//将图像添加到该部分的段落集合中
page.Paragraphs.Add(image1);
//设置图像文件流
image1.ImageStream = mystream;
dataDir = dataDir + "ImageToPDF_out.pdf";
//保存生成的 PDF 文件
doc.Save(dataDir);
//关闭内存流对象
mystream.Close();
Console.WriteLine("\nImage converted to pdf successfully.\nFile saved at " + dataDir); 
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 将图像转换为 PDF。我们介绍了分步过程，包括设置环境、导入库、初始化文档对象、加载图像文件、设置边距和裁剪框、将图像添加到页面、保存 PDF 文件以及关闭内存流。通过执行这些步骤，您可以在 .NET 应用程序中轻松地将图像转换为 PDF。