---
title: 在 PDF 文件中添加日期时间戳
linktitle: 在 PDF 文件中添加日期时间戳
second_title: Aspose.PDF for .NET API 参考
description: 通过本分步指南了解如何使用 Aspose.PDF for .NET 向您的 PDF 文件添加日期和时间戳。非常适合增强文档真实性。
type: docs
weight: 10
url: /zh/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
## 介绍

在管理文档（尤其是 PDF）时，添加日期和时间戳可能会改变游戏规则。无论您处理的是法律文件、项目报告还是发票，时间戳不仅可以增加真实性，还可以提供文档创建或修改时间的清晰记录。在本指南中，我们将引导您完成使用 .NET 的 Aspose.PDF 库向 PDF 文件添加日期和时间戳的过程。 

本文旨在简单易懂，因此即使您是编程或 Aspose.PDF 库的新手，您也能够自信地实现此功能。让我们开始吧！

## 先决条件

在开始之前，您需要满足一些先决条件：

1. Visual Studio：确保您的机器上安装了 Visual Studio。您将在这里编写和执行代码。
2. Aspose.PDF for .NET：您需要下载并安装 Aspose.PDF 库。您可以找到最新版本[这里](https://releases.aspose.com/pdf/net/).
3. C# 基础知识：熟悉 C# 编程将帮助您更好地理解示例，但如果您刚刚开始，请不要担心；我们将逐步解释一切。
4.  PDF 文件：准备好一个示例 PDF 文件。在我们的示例中，我们将使用名为`AddTextStamp.pdf`.

一旦满足这些先决条件，您就可以开始向 PDF 文件添加日期和时间戳了！

## 导入包

首先，您需要在 C# 项目中导入必要的命名空间。操作方法如下：

### 创建新项目

1. 打开 Visual Studio：启动您的 Visual Studio 应用程序。
2. 创建新项目：从开始屏幕选择“创建新项目”。
3. 选择控制台应用程序：从项目模板列表中选择“控制台应用程序（.NET Framework）”。
4. 命名您的项目：为您的项目命名，例如，`PDFDateTimeStamp`.

### 添加 Aspose.PDF 参考

1. 右键单击“引用”：在解决方案资源管理器中，右键单击项目的“引用”文件夹。
2. 选择“添加引用”：从上下文菜单中选择“添加引用”。
3. 浏览 Aspose.PDF：导航到您下载 Aspose.PDF 的位置并选择它。单击“确定”将其添加到您的项目中。

### 导入所需的命名空间

在你的顶部`Program.cs`文件，您需要导入以下命名空间：

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Annotations;
```

现在我们已经完成所有设置，让我们将向 PDF 文件添加日期和时间戳的过程分解为清晰、易于管理的步骤。

## 步骤 1：设置文档目录

首先，您需要指定 PDF 文件所在的目录。这很重要，因为代码将在此目录中查找 PDF。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY"; //替换为你的实际路径
```

确保更换`YOUR DOCUMENT DIRECTORY`使用您的 PDF 文件的实际路径。

## 第 2 步：打开 PDF 文档

接下来，您将打开想要添加时间戳的 PDF 文档。 

```csharp
//打开文档
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

这行代码初始化`Document`类并将您的 PDF 文件加载到`pdfDocument`目的。

## 步骤 3：创建日期时间戳

现在是时候生成日期和时间戳了。您将对其进行格式化以特定方式显示。 

```csharp
string annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");
```

这里，`DateTime.Now`获取当前日期和时间，以及`ToString`将其格式化为您想要的格式。

## 步骤 4：创建文本图章

准备好日期和时间字符串后，您现在可以创建将添加到 PDF 的文本戳。

```csharp
//创建文本印章
TextStamp textStamp = new TextStamp(annotationText);
```

这行代码创建了`TextStamp`使用格式化的日期和时间字符串。

## 步骤 5：设置图章的属性

您可以自定义图章的外观和位置。设置其属性的方法如下：

```csharp
//设置图章的属性
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

在此步骤中，我们设置边距并将印章与 PDF 页面的右下角对齐。

## 步骤 6：将图章添加到 PDF

现在是时候将文本印章添加到您的 PDF 文档了。 

```csharp
//在集邮册上添加邮票
pdfDocument.Pages[1].AddStamp(textStamp);
```

此行将图章添加到 PDF 的第一页。如果您想将其放在其他页面上，可以更改页码。

## 步骤 7：创建自由文本注释（可选）

如果要为图章添加注释，可以创建`FreeTextAnnotation`如下：

```csharp
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;
```

此可选步骤可创建一个自由文本注释，可以提供有关邮票的额外背景或信息。

## 步骤 8：配置注释边框

如果您想自定义注释的边框，也可以这样做：

```csharp
Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

此代码片段将边框宽度设置为 0，使其不可见，并将注释添加到 PDF。

## 步骤 9：保存 PDF 文档

最后，需要保存修改后的PDF文档。 

```csharp
dataDir = dataDir + "AddDateTimeStamp_out.pdf"; //指定输出文件名
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);
```

此行将添加时间戳的 PDF 保存到新文件。您可以检查指定的目录以查看输出。

## 结论

恭喜！您已成功使用 Aspose.PDF for .NET 向 PDF 文件添加了日期和时间戳。这个简单而有效的功能可以增强您的文档，使其更加专业，并提供创建或修改时间的清晰记录。 

## 常见问题解答

### 我可以自定义时间戳中的日期格式吗？
是的，你可以修改`ToString`方法将日期格式更改为您的偏好。

### Aspose.PDF 可以免费使用吗？
 Aspose.PDF 提供免费试用，但要获得完整功能，您需要购买许可证。您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).

### 我可以向 PDF 添加多个时间戳吗？
当然！您可以创建多个`TextStamp`实例并将它们添加到 PDF 中的不同页面或位置。

### 如果我没有 Visual Studio 怎么办？
您可以使用任何 C# IDE 或文本编辑器，但为了运行和调试项目，建议使用 Visual Studio。

### 在哪里可以找到更多使用 Aspose.PDF 的示例？
您可以在[Aspose.PDF 文档](https://reference.aspose.com/pdf/net/).