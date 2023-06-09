---
title: 在页面上绘制 XForm
linktitle: 在页面上绘制 XForm
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 页面上绘制 XForm 表单的分步指南。在页面上添加和定位表单。
type: docs
weight: 10
url: /zh/net/programming-with-operators/draw-xform-on-page/
---
在本教程中，我们将为您提供有关如何使用 Aspose.PDF for .NET 在页面上绘制 XForm 的分步指南。 Aspose.PDF 是一个功能强大的库，允许您以编程方式创建、操作和转换 PDF 文档。使用 Aspose.PDF 提供的运算符，您可以在现有 PDF 页面上添加和定位 XForm 表单。

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

## 第三步：设置文件路径

定义背景图像、输入 PDF 文件和输出 PDF 文件的文件路径：

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

请务必指定您计算机上的实际文件路径。

## 第 4 步：加载输入的 PDF 文件

使用以下代码加载输入 PDF 文件：

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
//以下代码使用 GSave/GRestore 运算符
//该代码使用 ContatenateMatrix 运算符来定位 XForm
//该代码使用 Do 运算符在页面上绘制 XForm
// GSave/GRestore 运算符包装现有内容
//这样做是为了获得现有内容末尾的初始图形状态
//否则，现有运算符链的末尾可能会留下不需要的转换
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
//添加 GSave 运算符以在新命令后正确重置图形状态
pageContents. Add(new GSave());

//创建变形
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
//设置图片的宽高
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
//将图像加载到流中
Stream imageStream = new FileStream(imageFile, FileMode.Open);
//将图像添加到 XForm 资源图像集合
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
//使用 Do 运算符：此运算符绘制图像
form.Contents.Add(new Do(ximage.Name));
form.Contents.Add(new GRestore());

pageContents. Add(new GSave());
//将 XForm 定位在坐标 x=100 和 y=500 处
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
//使用 Do 运算符绘制 XForm
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
//将 XForm 定位在坐标 x=100 和 y=300 处
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
//使用 Do 运算符绘制 XForm
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

//在 GSave 之后使用 GRestore 恢复图形状态
pageContents. Add(new GRestore());
doc.Save(outFile);
}
```

请务必指定实际文件路径并根据需要调整页码和 XForm 位置。

### 使用 Aspose.PDF for .NET 在页面上绘制 XForm 的示例源代码
 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imageFile = dataDir+ "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
using (Document doc = new Document(inFile))
{
	OperatorCollection pageContents = doc.Pages[1].Contents;
	//示例演示
	//GSave/GRestore 运算符的使用
	//ContatenateMatrix 运算符用于定位 xForm
	//使用操作符在页面上绘制 xForm
	//使用 GSave/GRestore 运算符对包装现有内容
	//这是为了获取现有内容的初始图形状态
	//否则，现有运营商链的末端可能会有一些不需要的转换
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	//添加保存图形状态运算符以在新命令后正确清除图形状态
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	//创建 xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	//定义图像宽度和高度
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	//将图像加载到流中
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//将图像添加到 XForm 资源的图像集合
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	//使用 Do 运算符：此运算符绘制图像
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	//将表格放置到 x=100 y=500 坐标
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	//使用 Do 运算符绘制表单
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	//将表格放置到 x=100 y=300 坐标
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	//使用 Do 运算符绘制表单
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	//在 GSave 之后使用 GRestore 恢复图形状态
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## 结论

在本教程中，您学习了如何使用 Aspose.PDF for .NET 在 PDF 页面上绘制 XForm 表单。按照描述的步骤操作，您将能够在现有页面上添加和定位 XForm 表单，从而为您的 PDF 文档提供更大的灵活性。
