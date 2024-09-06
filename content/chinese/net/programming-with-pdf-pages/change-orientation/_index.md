---
title: 改变方向
linktitle: 改变方向
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 更改 PDF 页面方向的分步指南。易于遵循并在您的项目中实施。
type: docs
weight: 10
url: /zh/net/programming-with-pdf-pages/change-orientation/
---
在本教程中，我们将引导您逐步使用 Aspose.PDF for .NET 更改 PDF 文档的页面方向。我们将解释捆绑的 C# 源代码并为您提供全面的指南，以帮助您理解并在自己的项目中实现此功能。在本教程结束时，您将了解如何使用 Aspose.PDF for .NET 更改 PDF 文档的页面方向。

## 先决条件
开始之前，请确保您已准备好以下物品：

- C# 编程语言的基础知识
- 在您的开发环境中安装 Aspose.PDF for .NET

## 步骤1：定义文档目录
首先，您需要设置文档目录的路径。这是输入 PDF 文件所在的位置，也是您要保存修改后的输出 PDF 文件的位置。将“您的文档目录”替换为适当的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载 PDF 文档
然后，您可以使用`Document`Aspose.PDF 类。请确保指定 PDF 文件的正确路径。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 步骤 3：更改页面方向
现在，我们将浏览文档的每一页并更改其方向。对于每一页，我们修改媒体框的尺寸（`MediaBox`)，然后我们调整媒体框的坐标以保持页面的位置。最后，我们将页面旋转设置为 90 度。

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## 步骤4：保存修改后的PDF文档
最后，您可以使用`Save()`方法`Document`类。请确保指定正确的路径和文件名。

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 更改方向的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	//我们必须将页面上移以补偿页面大小的变化
	//（页面下边缘为 0,0，信息通常从
	//页面顶部。这就是为什么我们将情人边缘移到上层
	//新旧高度。
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	//有时我们还需要设置CropBox（如果在原始文件中设置了）
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	//设置页面旋转角度
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
//保存输出文件
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 更改 PDF 文档的页面方向。按照上面概述的步骤，您可以轻松地在自己的项目中实现此功能。请随意探索 Aspose.PDF 文档以发现处理 PDF 文件的其他有用功能。

### 常见问题解答

#### 问：更改 PDF 文档中的页面方向有什么目的？

答：更改 PDF 文档中的页面方向可让您将页面内容旋转 90 度。这在需要以不同方向显示或打印原始内容的情况下非常有用，例如从纵向模式切换到横向模式或反之亦然。

#### 问：我可以更改 PDF 文档中特定页面的方向吗？

答：是的，您可以更改 PDF 文档中特定页面的方向。在提供的 C# 源代码中，`foreach`循环用于遍历文档的每一页并更改其方向。如果您只想更改特定页面的方向，则可以修改循环以根据页码或其他条件定位这些页面。

#### 问：改变页面方向会影响页面内容的布局吗？

答：是的，更改页面方向会影响页面内容的布局。内容将旋转 90 度，页面的宽度和高度将互换。因此，页面内容的放置和对齐方式可能会发生变化。

#### 问：我可以将页面旋转 90 度以外的角度吗？

答：在提供的 C# 源代码中，页面旋转设置为 90 度，使用`page.Rotate = Rotate.on90;`。但是，您可以根据需要将旋转角度更改为其他值。例如，您可以使用`Rotate.on180`将页面旋转 180 度或`Rotate.on270`将其旋转 270 度。

#### 问： 如何处理改变方向后溢出的页面内容？

答：更改页面方向时，页面尺寸可能会发生变化，从而导致内容溢出。为了解决这个问题，您可能需要调整页面上内容的布局和格式。您可以使用 Aspose.PDF for .NET 提供的功能，例如调整元素大小、调整边距或重新组织内容，以确保页面内容在方向更改后能够正确适应。