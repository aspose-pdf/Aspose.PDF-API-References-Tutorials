---
title: 在页面上绘制 XForm
linktitle: 在页面上绘制 XForm
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 页面上绘制 XForm 表单的分步指南。添加表单并将其放置在页面上。
type: docs
weight: 10
url: /zh/net/programming-with-operators/draw-xform-on-page/
---
在本教程中，我们将为您提供有关如何使用 Aspose.PDF for .NET 在页面上绘制 XForm 的分步指南。 Aspose.PDF 是一个功能强大的库，允许您以编程方式创建、操作和转换 PDF 文档。使用 Aspose.PDF 提供的运算符，您可以在现有 PDF 页面上添加和定位 XForm 表单。

## 先决条件

在开始之前，请确保您具备以下先决条件：

1. 随 .NET Framework 安装的 Visual Studio。
2. 适用于 .NET 的 Aspose.PDF 库。

## 第 1 步：项目设置

首先，在 Visual Studio 中创建一个新项目并添加对 Aspose.PDF for .NET 库的引用。您可以从Aspose官方网站下载该库并将其安装到您的计算机上。

## 第 2 步：导入必要的命名空间

在您的 C# 代码文件中，导入访问 Aspose.PDF 提供的类和方法所需的命名空间：

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

## 第三步：设置文件路径

定义背景图像、输入PDF文件和输出PDF文件的文件路径：

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string imageFile = dataDir + "aspose-logo.jpg";
string inFile = dataDir + "DrawXFormOnPage.pdf";
string outFile = dataDir + "blank-sample2_out.pdf";
```

请务必指定计算机上的实际文件路径。

## 第 4 步：加载输入 PDF 文件

使用以下代码加载输入 PDF 文件：

```csharp
using (Document doc = new Document(inFile))
{
OperatorCollection pageContents = doc.Pages[1].Contents;
//以下代码使用 GSave/GRestore 运算符
//该代码使用 ContatenateMatrix 运算符来定位 XForm
//代码使用Do操作符在页面上绘制XForm
// GSave/GRestore 运算符包装现有内容
//这样做是为了在现有内容末尾获取初始图形状态
//否则，现有操作符链的末端可能会留下不需要的转换
pageContents. Insert(1, new GSave());
pageContents. Add(new GRestore());
//添加 GSave 运算符以在新命令后正确重置图形状态
pageContents. Add(new GSave());

//创建 XForm
XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
doc.Pages[1].Resources.Forms.Add(form);
form.Contents.Add(new GSave());
//设置图像的宽度和高度
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
//将 XForm 放置在坐标 x=100 和 y=500 处
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 500));
//使用 Do 运算符绘制 XForm
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

pageContents. Add(new GSave());
//将 XForm 放置在坐标 x=100 和 y=300 处
pageContents. Add(new ConcatenateMatrix(1, 0, 0, 1, 100, 300));
//使用 Do 运算符绘制 XForm
pageContents.Add(new Do(form.Name));
pageContents. Add(new GRestore());

//GSave 之后使用 GRestore 恢复图形状态
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
	//示例演示了
	//GSave/GRestore 运算符用法
	//ContatenateMatrix 运算符用于定位 xForm
	//使用运算符在页面上绘制 xForm
	//使用 GSave/GRestore 运算符对包装现有内容
	//这是为了获取现有内容的初始图形状态
	//否则，现有运营商链的末端可能会残留一些不良的转变
	pageContents.Insert(1, new Aspose.Pdf.Operators.GSave());
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	//添加保存图形状态运算符以在新命令后正确清除图形状态
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	#region create xForm
	//创建xForm
	XForm form = XForm.CreateNewForm(doc.Pages[1], doc);
	doc.Pages[1].Resources.Forms.Add(form);
	form.Contents.Add(new Aspose.Pdf.Operators.GSave());
	//定义图像宽度和高度
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
	//将表单放置到 x=100 y=500 坐标
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 500));
	//使用 Do 运算符绘制表格
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	pageContents.Add(new Aspose.Pdf.Operators.GSave());
	//将表单放置到 x=100 y=300 坐标
	pageContents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(1, 0, 0, 1, 100, 300));
	//使用 Do 运算符绘制表格
	pageContents.Add(new Aspose.Pdf.Operators.Do(form.Name));
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	//GSave 之后使用 GRestore 恢复图形状态
	pageContents.Add(new Aspose.Pdf.Operators.GRestore());
	doc.Save(outFile);                
}

```

## 结论

在本教程中，您学习了如何使用 Aspose.PDF for .NET 在 PDF 页面上绘制 XForm 表单。通过执行所描述的步骤，您将能够在现有页面上添加和定位 XForm 表单，从而为 PDF 文档提供更大的灵活性。

### 页面上绘制 XForm 的常见问题解答

#### 问：Aspose.PDF 中的 XForm 是什么？

答：XForm 是 PDF 文档中可重用的图形对象。它允许您定义和绘制可以在不同页面上多次重复使用的复杂图形、图像或文本。

#### 问：如何导入 Aspose.PDF 所需的命名空间？

答：在您的 C# 代码文件中，使用`using`指令导入访问 Aspose.PDF 提供的类和方法所需的命名空间：
```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Operators;
```

#### 问：GSave 和 GRestore 运算符的目的是什么？

答： 的`GSave`和`GRestore`Aspose.PDF中的运算符用于保存和恢复图形状态。它们有助于确保应用于内容某一部分的转换和设置不会影响后续部分。

#### 问：如何使用 Aspose.PDF 定义 XForm？

答：要创建 XForm，请使用`XForm.CreateNewForm`方法并将其添加到`Resources.Forms`特定页面的集合。然后您可以将内容添加到 XForm 的`Contents`财产。

#### 问：如何在 XForm 中绘制图像？

 A：将图像加载到流中并将其添加到`Resources.Images`XForm 的集合。使用`Do`XForm 中的运算符`Contents`绘制图像。

#### 问：如何在 PDF 页面上放置 XForm？

答：要将 XForm 放置在页面上，请使用`ConcatenateMatrix`页面内的运算符`Contents`。调整矩阵参数以指定 XForm 的平移（位置）和缩放。

#### 问：我可以在同一页上绘制多个 XForm 吗？

答：是的，您可以在同一页面上绘制多个 XForm，只需调整`ConcatenateMatrix`将每个 XForm 定位在不同坐标的参数。

#### 问：XForm 创建后可以修改其内容吗？

答：是的，您可以在创建后通过向其添加附加运算符来修改 XForm 的内容`Contents`财产。

#### 问：如果我省略 GSave 和 GRestore 运算符，会发生什么情况？

答：省略 GSave 和 GRestore 运算符可能会导致不必要的转换或设置应用于后续内容。使用它们有助于保持干净的图形状态。

#### 问：我可以在 PDF 文档的不同页面上重复使用 XForms 吗？

答：是的，您可以通过将相同的 XForm 添加到页面来在多个页面上重复使用 XForm。`Resources.Forms`不同页面的集合。

#### 问：我可以创建的 XForm 数量有限制吗？

答：虽然对可以创建的 XForm 数量没有严格限制，但请记住，太多的 XForm 可能会影响性能和内存使用。明智地使用它们。

#### 问：我可以旋转 XForm 或应用其他转换吗？

答：是的，您可以使用`ConcatenateMatrix`运算符将旋转、缩放和平移等变换应用到 XForm。
