---
title: 水平和垂直单选按钮
linktitle: 水平和垂直单选按钮
second_title: Aspose.PDF for .NET API 参考
description: 通过本分步教程学习如何使用 Aspose.PDF for .NET 在 PDF 中创建水平和垂直对齐的单选按钮。
type: docs
weight: 180
url: /zh/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
## 介绍

创建交互式 PDF 表单可以显著提升用户体验，尤其是在收集信息时。最常见的表单元素之一是单选按钮，它允许用户从一组选项中选择一个选项。在本教程中，我们将探讨如何使用 Aspose.PDF for .NET 创建水平和垂直对齐的单选按钮。无论您是经验丰富的开发人员还是刚刚入门，本指南都将逐步指导您完成整个过程，确保您清楚了解每个部分。

## 先决条件

在深入研究代码之前，您应该满足一些先决条件：

1.  Aspose.PDF for .NET：确保已安装 Aspose.PDF 库。您可以从[地点](https://releases.aspose.com/pdf/net/).
2. Visual Studio：您可以编写和测试代码的开发环境。
3. C# 基础知识：熟悉 C# 编程将帮助您更好地理解代码片段。

## 导入包

首先，您需要在 C# 项目中导入必要的包。具体操作如下：

### 创建新项目

打开 Visual Studio 并创建一个新的 C# 项目。为了简单起见，您可以选择控制台应用程序。

### 添加 Aspose.PDF 参考

1. 在解决方案资源管理器中右键单击您的项目。
2. 选择“管理 NuGet 包”。
3. 搜索“Aspose.PDF”并安装最新版本。

```csharp
using System;
using System.IO;
using Aspose.Pdf.Facades;
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

现在您已完成所有设置，让我们分解代码以创建水平和垂直对齐的单选按钮。

## 步骤 1：设置文档目录

在此步骤中，我们将定义存储 PDF 文档的目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`替换为您想要保存 PDF 文件的实际路径。这很重要，因为它告诉程序在哪里查找输入文件以及在哪里保存输出。

## 步骤 2：加载现有 PDF 文档

接下来，我们需要加载要处理的 PDF 文档。这是使用`FormEditor`班级。

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

在这里，我们创建一个实例`FormEditor`并将其绑定到名为`input.pdf`确保此文件存在于您指定的目录中。

## 步骤 3：配置单选按钮属性

现在，让我们为单选按钮设置一些属性。这包括按钮之间的间隙、按钮的方向和按钮的大小。

```csharp
formEditor.RadioGap = 4; //单选按钮选项之间的距离
formEditor.RadioHoriz = true; //设置为 true 以进行水平对齐
formEditor.RadioButtonItemSize = 20; //单选按钮的大小
formEditor.Facade.BorderWidth = 1; //边框宽度
formEditor.Facade.BorderColor = System.Drawing.Color.Black; //边框颜色
```

这些属性将有助于定义单选按钮在 PDF 中的显示方式。`RadioGap`属性控制按钮之间的空间，而`RadioHoriz`决定其布局。

## 步骤 4：添加水平单选按钮

现在，让我们将水平单选按钮添加到 PDF 中。

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

在此代码中，我们定义单选按钮的项目并将它们添加到 PDF。`AddField`方法采用几个参数，包括字段类型、字段名称和放置坐标。

## 步骤 5：添加垂直单选按钮

接下来，我们将添加垂直单选按钮。为此，我们需要将方向改回垂直。

```csharp
formEditor.RadioHoriz = false; //设置为 false 以进行垂直对齐
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

就像之前一样，我们定义项目并将它们添加到 PDF，但这次它们将垂直对齐。

## 步骤 6：保存 PDF 文档

最后，我们需要保存修改后的PDF文档。

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
```

此代码使用新添加的单选按钮保存 PDF。请确保检查输出文件的指定目录。

## 结论

使用 Aspose.PDF for .NET 在 PDF 中创建单选按钮是一个简单的过程。按照本教程中概述的步骤，您可以轻松地将水平和垂直对齐的单选按钮添加到 PDF 表单中。这不仅可以增强文档的交互性，还可以改善整体用户体验。所以，继续尝试吧！

## 常见问题解答

### 什么是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一个功能强大的库，允许开发人员以编程方式创建、操作和转换 PDF 文档。

### 我可以免费使用 Aspose.PDF 吗？
是的，Aspose 提供免费试用版，您可以使用它来评估该库。您可以下载它[这里](https://releases.aspose.com/).

### 如何获得 Aspose.PDF 的支持？
您可以通过访问获得支持[Aspose 论坛](https://forum.aspose.com/c/pdf/10).

### 是否可以使用 Aspose.PDF 创建其他表单元素？
当然！Aspose.PDF 支持各种表单元素，包括文本字段、复选框和下拉菜单。

### 我可以在哪里购买 Aspose.PDF for .NET？
您可以从以下网站购买 Aspose.PDF for .NET[购买页面](https://purchase.aspose.com/buy).