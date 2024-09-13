---
title: 改变方向
linktitle: 改变方向
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 更改 PDF 页面方向的分步指南。易于遵循并在您的项目中实施。
type: docs
weight: 10
url: /zh/net/programming-with-pdf-pages/change-orientation/
---
## 介绍

您是否曾经遇到过 PDF 文件页面方向不对的问题？也许您正在处理扫描或创建不正确的文档，页面需要旋转才能正常显示。幸运的是，Aspose.PDF for .NET 提供了一种简单、强大的方法来以任何可以想象的方式操作 PDF 文件，包括更改页面方向。无论您是想从纵向切换到横向还是从横向切换到纵向，本指南都会逐步指导您完成该过程。

因此，如果您已准备好深入研究并轻松旋转这些 PDF 页面，那就开始吧！

## 先决条件

在我们深入了解更改 PDF 中的页面方向的细节之前，让我们快速介绍一下您需要准备的内容：

-  Aspose.PDF for .NET：确保您已安装 Aspose.PDF 库 for .NET。如果没有，您可以[点击下载](https://releases.aspose.com/pdf/net/).
- .NET 开发环境：您可以使用 Visual Studio、JetBrains Rider 或任何首选 IDE 来处理 .NET。
- C# 基础知识：虽然本指南很简单，但对 C# 的一些基本了解将使其更容易遵循。
- PDF 文件：以下示例假设您有一个包含多页的 PDF 文件。如果您手边没有，请创建或下载一个示例 PDF 以供使用。

另外，如果你刚刚开始，你可以尝试使用 Aspose.PDF[免费临时驾照](https://purchase.aspose.com/temporary-license/)在决定[购买完整版](https://purchase.aspose.com/buy).

## 导入命名空间

在操作 PDF 中的页面方向之前，您需要在 C# 项目中导入必要的命名空间。请确保您具有以下内容：

```csharp
using System.IO;
using Aspose.Pdf;
```

导入完成后，我们就可以进入本教程的主要部分了。

## 步骤 1：加载 PDF 文档

我们需要做的第一件事是加载要修改的 PDF 文件。您可以使用`Document`来自 Aspose.PDF 命名空间的类来打开您的 PDF。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
```

此行从您指定的目录加载 PDF。请确保替换`"YOUR DOCUMENT DIRECTORY"`替换为文件的实际路径。`"input.pdf"`是您要更改方向的 PDF。

## 步骤 2：循环遍历每一页

现在我们已经加载了文档，让我们循环遍历 PDF 中的每一页。我们将使用`foreach`循环遍历每一页，让我们将方向改变应用到所有页面。

```csharp
foreach (Page page in doc.Pages)
{
    //操纵每一页
}
```

此循环将遍历文档中的所有页面。

## 步骤 3：获取页面的 MediaBox

 PDF 中的每一页都有一个`MediaBox`定义页面的边界。我们需要访问它来确定当前方向并进行修改。

```csharp
Aspose.Pdf.Rectangle r = page.MediaBox;
```

这`MediaBox`为我们提供页面的尺寸，例如其宽度、高度和定位。

## 步骤 4：交换宽度和高度

要将页面方向从纵向改为横向或从横向改为纵向，我们只需交换宽度和高度值。此步骤将调整页面的尺寸。

```csharp
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
```

此代码交换高度和宽度并重新定位左下角（`LLY`) 以便内容旋转后能够整齐地排列。

## 步骤 5：更新 MediaBox 和 CropBox

现在我们有了新的高度和宽度，让我们将更改应用到页面的`MediaBox`和`CropBox` 。 这`CropBox`如果原始文档有一套，这很重要，以确保整个页面正确显示。

```csharp
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
```

此步骤根据我们刚刚计算的新尺寸调整页面大小。

## 步骤 6：旋转页面

最后，我们设置页面的旋转角度。Aspose.PDF 使这变得非常简单。我们可以将页面旋转 90 度，从纵向转换为横向，反之亦然。

```csharp
page.Rotate = Rotation.on90;
```

此代码将页面旋转 90 度，将其翻转到所需的方向。

## 步骤 7：保存输出 PDF

将方向更改应用到所有页面后，我们将修改后的文档保存到新文件中。 

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);
```

确保提供新的文件名（在本例中，`ChangeOrientation_out.pdf`) 保存输出。这样，您就不会覆盖原始文件。

### 结论

就这样！使用 Aspose.PDF for .NET 更改 PDF 文件的页面方向非常简单，只需加载文档、循环浏览页面、调整 MediaBox 并保存更新的文件即可。无论您处理的是扫描质量不佳的文档还是需要旋转页面以满足您的格式需求，本分步指南都可以满足您的需求。

## 常见问题解答

### 我可以旋转 PDF 中的特定页面而不是所有页面吗？  
是的，您可以修改循环以使用索引来定位特定页面，而不是循环遍历所有页面。

### 什么是`MediaBox`?  
这`MediaBox`定义 PDF 文件中页面的大小和形状。页面内容就放在这里。

### Aspose.PDF for .NET 能适用于其他文件格式吗？  
是的，Aspose.PDF 可以处理各种文件格式，如 HTML、XML、XPS 等。

### 有没有适用于 .NET 的 Aspose.PDF 免费版本？  
是的，你可以从[免费试用](https://releases.aspose.com/)或请求[临时执照](https://purchase.aspose.com/temporary-license/).

### 保存后我可以撤消更改吗？  
一旦保存文档，更改将永久生效。请务必在副本上操作或保留原始文件的备份。