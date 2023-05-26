---
title: 获取字体替换警告
linktitle: 获取字体替换警告
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 的 GetWarningsForFontSubstitution 功能在打开 PDF 文档时检测字体替换警告。
type: docs
weight: 190
url: /zh/net/programming-with-document/getwarningsforfontsubstitution/
---

 Aspose.PDF for .NET 是一个流行的 PDF 操作库，它使开发人员能够在其 .NET 应用程序中创建、编辑和转换 PDF 文件。该库提供的功能之一是能够在打开 PDF 文档时检测字体替换警告。本教程将指导您完成使用`GetWarningsForFontSubstitution`Aspose.PDF for .NET 的功能用于在打开 PDF 文档时检测字体替换警告。

## 第 1 步：为 .NET 安装 Aspose.PDF

要在您的 .NET 应用程序中使用 Aspose.PDF for .NET，您必须首先安装该库。您可以从以下位置下载最新版本的库[Aspose.PDF for .NET 下载页面](https://relases.aspose.com/pdf/net).

下载库后，将 ZIP 文件的内容解压缩到计算机上的文件夹中。然后您需要在您的 .NET 项目中添加对 Aspose.PDF for .NET DLL 的引用。

## 第 2 步：加载 PDF 文档

一旦您安装了 Aspose.PDF for .NET 并在您的 .NET 项目中添加了对 DLL 的引用，您就可以开始使用`GetWarningsForFontSubstitution`打开 PDF 文档时检测字体替换警告的功能。

使用此功能的第一步是加载要检测字体替换警告的 PDF 文档。为此，您可以使用以下代码：

```csharp
// PDF文档的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开 PDF 文档
Document doc = new Document(dataDir + "input.pdf");
```

在上面的代码中，替换`"YOUR DOCUMENT DIRECTORY"`以及您的 PDF 文档所在目录的路径。此代码会将 PDF 文档加载到`Document`对象，然后您可以使用它来检测字体替换警告。

## 第 3 步：检测字体替换警告

要在打开 PDF 文档时检测字体替换警告，您可以使用以下代码：

```csharp
doc.FontSubstitution += new Document.FontSubstitutionHandler(OnFontSubstitution);
```

在上面的代码中，`OnFontSubstitution`是一种在检测到字体替换警告时将被调用的方法。您可以自定义此方法以按照您喜欢的任何方式处理字体替换警告。

这是一个示例实现`OnFontSubstitution`方法：

```csharp
private void OnFontSubstitution(object sender, Document.FontSubstitutionEventArgs e)
{
    Console.WriteLine("Font substitution: {0} => {1}", e.OriginalFontName, e.SubstitutedFontName);
}
```

在上面的代码中，`OnFontSubstitution`只要检测到字体替换警告，方法就会简单地将原始字体名称和替换字体名称输出到控制台。您可以自定义此方法以按照您喜欢的任何方式处理字体替换警告。

### 使用 Aspose.NET for PDF 获取字体替换警告的示例源代码

这是使用打开 PDF 文档时检测字体替换警告的完整源代码`GetWarningsForFontSubstitution`Aspose.PDF for .NET 的特点：

```csharp
// PDF文档的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开 PDF 文档
Document doc = new Document(dataDir + "input.pdf");

//检测字体替换警告
doc.FontSubstitution += new Document.FontSubstitutionHandler(OnFontSubstitution);

//处理字体替换警告
private void OnFontSubstitution(object sender, Document.FontSubstitutionEventArgs e)
{
    Console.WriteLine("Font substitution: {0} => {1}", e.