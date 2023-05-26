---
title: 确定进度
linktitle: 确定进度
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南和代码示例，了解如何使用 Aspose.PDF for .NET 确定 PDF 文档转换过程的进度。
type: docs
weight: 110
url: /zh/net/programming-with-document/determineprogress/
---

Aspose.PDF for .NET 提供了一项功能，允许您确定 PDF 文档转换过程的进度。在本教程中，我们将提供有关如何使用 C# 和 Aspose.PDF for .NET 实现此功能的分步指南。

## 第 1 步：加载 PDF 文档

第一步是加载要转换的 PDF 文档。对于本教程，我们将使用文件“AddTOC.pdf”。将此文件的路径替换为您自己的 PDF 文档的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddTOC.pdf");
```

## 第 2 步：设置自定义进度处理程序

接下来，我们需要设置将在转换过程中调用的自定义进度处理程序。在本教程中，我们将使用`ConversionProgressEventHandler`Aspose.PDF for .NET 提供的委托。

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.CustomProgressHandler = new UnifiedSaveOptions.ConversionProgressEventHandler(ShowProgressOnConsole);
```

## 第 3 步：保存 PDF 文档

最后，我们需要使用`Save()`的方法`Document`目的。我们将传入在上一步中设置的自定义进度处理程序作为参数。

```csharp
dataDir = dataDir + "DetermineProgress_out.pdf";
pdfDocument.Save(dataDir, saveOptions);
```

## 第 4 步：实施进度处理程序

要实现进度处理程序，我们需要定义一个方法，该方法接受一个类型的参数`ConversionProgressEventArgs`.在转换过程中会调用该方法来报告转换的进度。

```csharp
private void ShowProgressOnConsole(ConversionProgressEventArgs args)
{
    Console.WriteLine("Conversion progress: {0}%", args.Percent);
}
```

### 使用 Aspose.PDF for .NET 确定进度的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "AddTOC.pdf");
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.CustomProgressHandler = new UnifiedSaveOptions.ConversionProgressEventHandler(ShowProgressOnConsole);

dataDir = dataDir + "DetermineProgress_out.pdf";
pdfDocument.Save(dataDir, saveOptions);
Console.ReadLine();

private void ShowProgressOnConsole(ConversionProgressEventArgs args)
{
    Console.WriteLine("Conversion progress: {0}%", args.Percent);
}
```

## 结论

在本教程中，我们提供了有关如何使用 Aspose.PDF for .NET 确定 PDF 文档转换过程的进度的分步指南。我们还提供了一个代码示例，您可以在自己的应用程序中实现此功能时作为参考。