---
title: 将图像流转换为 PDF
linktitle: 将图像流转换为 PDF
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松将图像流转换为 PDF 文件。
type: docs
weight: 70
url: /zh/net/programming-with-images/convert-image-stream-to-pdf/
---

本指南将逐步指导您如何使用 Aspose.PDF for .NET 将图像流转换为 PDF 文件。确保您已经设置了环境并按照以下步骤操作：

## 第一步：定义文档目录

在开始之前，请确保为文档设置了正确的目录。代替`"YOUR DOCUMENT DIRECTORY"`在代码中包含图像所在目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：实例化一个 Document 对象

在这一步中，我们将实例化一个`Document`使用的空构造函数的对象`Aspose.Pdf.Document`班级。

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## 第 3 步：向 PDF 文档添加页面

使用 将页面添加到 PDF 文档`Add`的方法`Pages`的对象`pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## 第四步：读取图像流

在这一步中，我们将创建一个`FileStream`对象从流中读取图像文件。

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## 第 5 步：将图像读入字节数组

从流中读取图像并使用`Read`的方法`fs`目的。

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## 第 6 步：从字节数组创建 MemoryStream 对象

创建一个`MemoryStream`包含图像的字节数组中的对象。

```csharp
MemoryStream ms = new MemoryStream(data);
```

## 第 7 步：创建图像对象

在这一步中，我们将创建一个`Image`对象使用`Aspose.Pdf.Image`班级。使用指定图像流`ImageStream`财产并通过`ms`我们之前创建的对象。

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## 步骤 8：将 Image 对象添加到 Paragraphs 集合

添加`imageht`反对`Paragraphs`的集合`sec`部分。

```csharp
sec.Paragraphs.Add(imageht);
```

## 第 9 步：保存 PDF 文档

使用保存 PDF 文档`Save`的方法`pdf1`目的。指定 PDF 文件的输出路径。

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## 第 10 步：关闭 MemoryStream 对象

关上`ms`对象使用`Close`释放资源的方法。

```csharp
ms. Close();
```

### 使用 Aspose.PDF for .NET 将图像流转换为 PDF 的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//通过调用其空构造函数来实例化 Document 实例
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
//在pdf文档中添加一个页面
Aspose.Pdf.Page sec = pdf1.Pages.Add();
//创建一个FileStream对象来读取imag文件
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
//将图像读入字节数组
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
//从图像字节数组创建 MemoryStream 对象
MemoryStream ms = new MemoryStream(data);
//创建图像对象
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
//指定图像源为 MemoryStream
imageht.ImageStream = ms;
//将图像对象添加到该部分的段落集合中
sec.Paragraphs.Add(imageht);
//保存 PDF
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
//关闭内存流对象
ms.Close();
```

## 结论

恭喜！您已经使用 Aspose.PDF for .NET 成功地将图像流转换为 PDF 文件。生成的PDF文件保存在指定目录下。您现在可以在您的项目或应用程序中使用此 PDF 文件。