---
title: 隐藏文本块
linktitle: 隐藏文本块
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 中创建隐藏文本块。
type: docs
weight: 230
url: /zh/net/programming-with-text/hidden-text-block/
---

在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库创建隐藏文本块。隐藏文本块是一种浮动文本，当鼠标光标悬停在特定区域上时会变得可见。我们将逐步完成使用提供的 C# 源代码创建隐藏文本块的过程。

## 要求

在开始之前，请确保您具有以下内容：

- 安装了 Aspose.PDF for .NET 库。
- 对 C# 编程有基本的了解。

## 第 1 步：设置文档目录

首先，您需要将路径设置为要保存生成的 PDF 文件的目录。代替`"YOUR DOCUMENT DIRECTORY"`在里面`dataDir`带有所需目录路径的变量。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建示例文档

在此步骤中，我们创建一个示例 PDF 文档并向其中添加一个文本片段。文本片段将作为显示隐藏文本块的触发器。

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## 第 3 步：打开文档

现在，我们使用`Document`班级。

```csharp
Document document = new Document(outputFile);
```

## 第 4 步：查找文本片段

我们使用一个`TextFragmentAbsorber`对象以查找将触发隐藏文本块显示的文本片段。在这种情况下，我们正在搜索确切的文本“将鼠标光标移至此处以显示浮动文本”。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## 第 5 步：创建隐藏文本字段

我们创造一个`TextBoxField`对象来表示隐藏的文本字段。该字段将包含当鼠标光标悬停在触发文本上时变得可见的文本。

```csharp
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
floatingField.Value = "This is the \"floating text field\".";
floatingField. ReadOnly = true;
floatingField.Flags |= AnnotationFlags.Hidden;
floatingField.PartialName = "FloatingField_1";
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField. Multiline = true;
```

## 第 6 步：将隐藏文本字段添加到文档

我们将隐藏的文本字段添加到文档的表单集合中。

```csharp
document.Form.Add(floatingField);
```

## 第 7 步：创建隐形按钮

我们创建一个不可见的按钮字段，该字段将位于触发文本片段的顶部。此按钮字段将具有与鼠标进入和退出事件关联的操作。

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## 第 8 步：保存文件

最后，我们用隐藏的文本块保存修改后的文档。

```csharp
document. Save(outputFile);
```

### 使用 Aspose.PDF for .NET 的隐藏文本块示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
//使用文本创建示例文档
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
//打开带有文本的文档
Document document = new Document(outputFile);
//创建 TextAbsorber 对象以查找与正则表达式匹配的所有短语
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
//接受文档页面的吸收器
document.Pages.Accept(absorber);
//获取第一个提取的文本片段
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//在页面的指定矩形中为浮动文本创建隐藏文本字段
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
//设置要显示为字段值的文本
floatingField.Value = "This is the \"floating text field\".";
//对于这种情况，我们建议将字段设置为“只读”
floatingField.ReadOnly = true;
//设置“隐藏”标志以使字段在文档打开时不可见
floatingField.Flags |= AnnotationFlags.Hidden;
//设置唯一的字段名称不是必需的，但允许
floatingField.PartialName = "FloatingField_1";
//设置字段外观的特征不是必需的，但会使其变得更好
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
//向文档添加文本字段
document.Form.Add(floatingField);
//在文本片段位置创建不可见按钮
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
//为指定字段（注释）和不可见标志创建新的隐藏操作。
// （如果您在上面指定了名称，您也可以通过名称引用浮动字段。）
//在不可见按钮字段添加鼠标进入/退出操作
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
//将按钮字段添加到文档
document.Form.Add(buttonField);
//保存文档
document.Save(outputFile);
```

## 结论

在本教程中，您学习了如何使用 Aspose.PDF for .NET 库创建隐藏文本块。按照分步指南，您可以生成一个带有隐藏文本字段的 PDF 文档，当鼠标光标悬停在特定区域时，该文本字段会变得可见。您可以根据需要自定义隐藏文本块的外观和行为。