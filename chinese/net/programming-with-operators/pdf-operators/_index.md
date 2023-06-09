---
title: PDF 运算符
linktitle: PDF 运算符
second_title: Aspose.PDF for .NET API 参考
description: 在 Aspose.PDF for .NET 中使用 PDF 运算符的分步指南。将图像添加到 PDF 页面并指定其位置。
type: docs
weight: 20
url: /zh/net/programming-with-operators/pdf-operators/
---
在本教程中，我们将为您提供有关如何使用 Aspose.PDF for .NET 使用 PDF 运算符的分步指南。 PDF 操作员允许您以精确和可控的方式操作和添加内容到 PDF 文档。使用 Aspose.PDF 提供的运算符，您可以将图像添加到 PDF 页面并精确指定其位置。

## 先决条件

在开始之前，请确保您具备以下先决条件：

1. Visual Studio 安装了 .NET 框架。
2. .NET 的 Aspose.PDF 库。

## 第 1 步：项目设置

首先，在 Visual Studio 中创建一个新项目并添加对 Aspose.PDF for .NET 库的引用。您可以从 Aspose 官方网站下载该库并将其安装在您的机器上。

## 第 2 步：导入必要的命名空间

在您的 C# 代码文件中，导入访问 Aspose.PDF 提供的类和方法所需的命名空间：

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## 第 3 步：加载 PDF 文档

使用以下代码加载 PDF 文档：

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document pdfDocument = new Document(dataDir + "PDFOperators.pdf");
```

请务必在您的机器上指定 PDF 文件的实际路径。

## 第 4 步：加载图像并将其添加到页面

使用以下代码从文件加载图像并将其添加到 PDF 页面：

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;

Page page = pdfDocument.Pages[1];

FileStream imageStream = new FileStream(dataDir + "PDFOperators.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream);

page. Contents. Add(new GSave());

Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });

page.Contents.Add(new ConcatenateMatrix(matrix));

XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Do(ximage.Name));

page. Contents. Add(new GRestore());
```

请务必在您的计算机上指定 PDF 和图像文件的实际路径。您还可以调整`lowerLeftX`, `lowerLeftY`, `upperRightX`和`upperRightY`根据需要定位图像的坐标。

### 使用 Aspose.PDF for .NET 的 PDF Operators 示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir+ "PDFOperators.pdf");
//设定坐标
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
//获取需要添加图片的页面
Page page = pdfDocument.Pages[1];
//将图像加载到流中
FileStream imageStream = new FileStream(dataDir + "PDFOperators.jpg", FileMode.Open);
//将图像添加到页面资源的图像集合
page.Resources.Images.Add(imageStream);
//使用 GSave 运算符：此运算符保存当前图形状态
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
//创建矩形和矩阵对象
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
//使用 ConcatenateMatrix（连接矩阵）运算符：定义必须如何放置图像
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
//使用 Do 运算符：此运算符绘制图像
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
//使用 GRestore 运算符：此运算符恢复图形状态
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "PDFOperators_out.pdf";
//保存更新的文档
pdfDocument.Save(dataDir);
```

## 结论

在本教程中，您学习了如何使用 Aspose.PDF for .NET 使用 PDF 运算符。按照描述的步骤操作，您将能够将图像添加到 PDF 页面并精确指定其位置。 PDF Operators 提供对 PDF 文档操作的精细控制，允许您自定义您的内容。
