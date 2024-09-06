---
title: 在页面上绘制 XForm
linktitle: 在页面上绘制 XForm
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 页面上绘制 XForm 表单的分步指南。在页面上添加和定位表单。
type: docs
weight: 10
url: /zh/net/programming-with-operators/draw-xform-on-page/
---
在本教程中，我们将为您提供使用 Aspose.PDF for .NET 在页面上绘制 XForm 的分步指南。Aspose.PDF 是一个功能强大的库，允许您以编程方式创建、操作和转换 PDF 文档。使用 Aspose.PDF 提供的运算符，您可以在现有 PDF 页面上添加和定位 XForm 表单。

## 先决条件

开始之前，请确保您已满足以下先决条件：

1. 安装了 .NET 框架的 Visual Studio。
2. 适用于 .NET 的 Aspose.PDF 库。

## 步骤 1：项目设置

首先，在 Visual Studio 中创建一个新项目并添加对 Aspose.PDF for .NET 库的引用。您可以从 Aspose 官方网站下载该库并将其安装在您的机器上。

## 第 2 步：导入必要的命名空间

在您的 C# 代码文件中，导入访问 Aspose.PDF 提供的类和方法所需的命名空间：

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## 步骤 3：设置文件路径

定义背景图像、输入 PDF 文件和输出 PDF 文件的文件路径：

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

请确保指定您机器上的实际文件路径。

## 步骤 4：加载输入 PDF 文件

使用以下代码加载输入的 PDF 文件：

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
//以下代码使用 GSave/GRestore 运算符
//代码使用 ContatenateMatrix 运算符来定位 XForm
//代码使用 Do 运算符在页面上绘制 XForm
// GSave/GRestore 操作符包装现有内容
//这样做是为了获取现有内容末尾的初始图形状态
//否则，现有操作符链的末端可能会留下不必要的转换
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
//添加 GSave 操作符以在新命令后正确重置图形状态
pageContents. Add(new GSave());

//创建 XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
//设置图片的宽度和高度
form.Contents.Add(new ConcatenateMatrix(200, 0, 0, 200, 0, 0));
//将图像加载到流中
Stream imageStream = new FileStream(imageFile, FileMode.Open);
//将图像添加到 XForm 资源图像集合
form.Resources.Images.Add(imageStream);
XImage ximage = form.Resources.Images[form.Resources.Images.Count];
//使用 Do 运算符：该运算符绘制图像
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

确保指定实际的文件路径并根据需要调整页码和 XForm 位置。

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
	//该示例演示
	//GSave/GRestore 操作符用法
	//使用 ContatenateMatrix 运算符来定位 xForm
	//使用 Do 运算符在页面上绘制 xForm
	//使用 GSave/GRestore 操作符对包装现有内容
	//这是为了获取现有内容的初始图形状态
	//否则，现有运营商链的末端可能会存在一些不良的转变
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	//添加保存图形状态操作符以便在新命令之后正确清除图形状态
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	//创建 xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	//定义图像的宽度和高度
	form.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(200, 0, 0, 200, 0, 0));
	//将图像加载到流中
	Stream imageStream = new FileStream(imageFile, FileMode.Open);
	//将图像添加到 XForm 资源的图像集合中
	form.Resources.Images.Add(imageStream);
	XImage ximage = form.Resources.Images[form.Resources.Images.Count];
	//使用 Do 运算符：该运算符绘制图像
	form.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
	form.Contents.Add(new Aspose.Pdf.Operators.GRestore());
	#endregion
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	//将表格放置到 x=100 y=500 坐标处
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	//使用 Do 运算符绘制表格
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	//将表格放置到 x=100 y=300 坐标处
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	//使用 Do 运算符绘制表格
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	//在 GSave 之后使用 GRestore 恢复图形状态
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## 结论

在本教程中，您学习了如何使用 Aspose.PDF for .NET 在 PDF 页面上绘制 XForm 表单。通过遵循所述步骤，您将能够在现有页面上添加和定位 XForm 表单，从而为您的 PDF 文档提供更大的灵活性。

### 关于 draw XForm 的常见问题解答

#### 问：Aspose.PDF 中的 XForm 是什么？

答：XForm 是 PDF 文档中可重复使用的图形对象。它允许您定义和绘制可在不同页面上多次重复使用的复杂图形、图像或文本。

#### 问：如何导入 Aspose.PDF 必要的命名空间？

答：在您的 C# 代码文件中，使用`using`指令导入访问 Aspose.PDF 提供的类和方法所需的命名空间：
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### 问：GSave 和 GRestore 操作符的用途是什么？

答：`GSave`和`GRestore` Aspose.PDF 中的操作符用于保存和恢复图形状态。它们有助于确保应用于内容某一部分的转换和设置不会影响后续部分。

#### 问：如何使用 Aspose.PDF 定义 XForm？

答：要创建 XForm，请使用`XForm.CreateNewForm`方法并将其添加到`Resources.Forms`特定页面的集合。然后您可以将内容添加到 XForm 的`Contents`财产。

#### 问：如何在 XForm 中绘制图像？

A：将图像加载到流中并将其添加到`Resources.Images`XForm 的集合。使用`Do`XForm 中的运算符`Contents`绘制图像。

#### 问：如何在 PDF 页面上定位 XForm？

答：要在页面上定位 XForm，请使用`ConcatenateMatrix`页面中的操作符`Contents`调整矩阵参数来指定XForm的平移（位置）和缩放。

#### 问：我可以在同一页面上绘制多个 XForms 吗？

答：是的，您可以通过调整`ConcatenateMatrix`参数将每个 XForm 定位到不同的坐标。

#### 问：创建 XForm 后我可以修改其内容吗？

答：是的，您可以在创建 XForm 后通过向其添加其他操作符来修改其内容`Contents`财产。

#### 问：如果我省略 GSave 和 GRestore 操作符会发生什么？

答：省略 GSave 和 GRestore 操作符可能会导致不必要的转换或设置应用于后续内容。使用它们有助于保持干净的图形状态。

#### 问：我可以在 PDF 文档的不同页面之间重复使用 XForms 吗？

答：是的，您可以通过将相同的 XForm 添加到`Resources.Forms`不同页面的集合。

#### 问：我可以创建的 XForms 数量有限制吗？

答：虽然您可以创建的 XForms 数量没有严格限制，但请记住，过多的 XForms 可能会影响性能和内存使用。请谨慎使用它们。

#### 问：我可以旋转 XForm 或应用其他转换吗？

答：是的，您可以使用`ConcatenateMatrix`运算符对 XForm 应用旋转、缩放和平移等变换。
