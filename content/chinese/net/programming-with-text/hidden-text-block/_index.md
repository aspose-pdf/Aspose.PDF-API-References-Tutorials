---
title: PDF 文件中的隐藏文本块
linktitle: PDF 文件中的隐藏文本块
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中创建隐藏文本块。
type: docs
weight: 230
url: /zh/net/programming-with-text/hidden-text-block/
---
在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库在 PDF 文件中创建隐藏文本块。隐藏文本块是浮动文本，当鼠标光标悬停在特定区域上时，该文本将变为可见。我们将使用提供的 C# 源代码逐步介绍创建隐藏文本块的过程。

## 要求

开始之前，请确保您已准备好以下物品：

- 已安装 Aspose.PDF for .NET 库。
- 对 C# 编程有基本的了解。

## 步骤 1：设置文档目录

首先，您需要设置要保存生成的 PDF 文件的目录路径。替换`"YOUR DOCUMENT DIRECTORY"`在`dataDir`变量为您所需目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：创建示例文档

在此步骤中，我们创建一个示例 PDF 文档并向其中添加一个文本片段。该文本片段将作为显示隐藏文本块的触发器。

```csharp
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
```

## 步骤 3：打开文档

现在，我们使用`Document`班级。

```csharp
Document document = new Document(outputFile);
```

## 步骤 4：查找文本片段

我们使用`TextFragmentAbsorber`对象来查找将触发隐藏文本块显示的文本片段。在本例中，我们搜索的是精确的文本“将鼠标光标移至此处以显示浮动文本”。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## 步骤 5：创建隐藏文本字段

我们创建`TextBoxField`对象来表示隐藏的文本字段。此字段将包含鼠标光标悬停在触发文本上时可见的文本。

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

## 步骤 6：将隐藏文本字段添加到文档

我们将隐藏的文本字段添加到文档的表单集合中。

```csharp
document.Form.Add(floatingField);
```

## 步骤 7：创建隐形按钮

我们创建一个不可见的按钮字段，该字段将位于触发文本片段的顶部。此按钮字段将具有与鼠标进入和退出事件相关的操作。

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## 步骤 8：保存文档

最后，我们保存修改后的带有隐藏文本块的文档。

```csharp
document. Save(outputFile);
```

### 使用 Aspose.PDF for .NET 的隐藏文本块示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
//创建带有文本的示例文档
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
//打开带有文本的文档
Document document = new Document(outputFile);
//创建 TextAbsorber 对象来查找与正则表达式匹配的所有短语
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
//接受文件页面的吸收器
document.Pages.Accept(absorber);
//获取第一个提取的文本片段
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//在页面的指定矩形区域内创建用于浮动文本的隐藏文本字段
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
//设置要显示为字段值的文本
floatingField.Value = "This is the \"floating text field\".";
//对于这种情况，我们建议将字段设为“只读”
floatingField.ReadOnly = true;
//设置“隐藏”标志以使字段在文档打开时不可见
floatingField.Flags |= AnnotationFlags.Hidden;
//设置唯一的字段名称不是必需的，但允许
floatingField.PartialName = "FloatingField_1";
//设置字段外观特征不是必需的，但可以使其变得更好
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
//向文档添加文本字段
document.Form.Add(floatingField);
//在文本片段位置创建隐形按钮
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
//为指定字段（注释）和不可见标志创建新的隐藏操作。
// （如果您上面已指定，您也可以通过名称来引用浮动字段。）
//在不可见按钮字段添加鼠标进入/退出时的操作
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
//向文档添加按钮字段
document.Form.Add(buttonField);
//保存文档
document.Save(outputFile);
```

## 结论

在本教程中，您学习了如何使用 Aspose.PDF for .NET 库创建隐藏文本块。按照分步指南，您可以生成带有隐藏文本字段的 PDF 文档，当鼠标光标悬停在特定区域上时，该文本字段将变为可见。您可以根据需要自定义隐藏文本块的外观和行为。

### 常见问题解答

#### 问：《PDF 文件中的隐藏文本块》教程的目的是什么？

答：“PDF 文件中的隐藏文本块”教程介绍了如何使用 .NET 的 Aspose.PDF 库在 PDF 文件中创建隐藏文本块。隐藏文本块是浮动文本，当鼠标光标悬停在特定区域上时，该文本块会变为可见。本教程使用 C# 源代码提供了分步指南。

#### 问：为什么我要在 PDF 文件中创建隐藏文本块？

答：创建隐藏文本块对于交互式 PDF 文档很有用，您可以在其中提供只有当用户将鼠标光标悬停在指定区域上时才可见的附加信息或上下文。

#### 问：如何设置文档目录？

A：设置文档目录：

1. 代替`"YOUR DOCUMENT DIRECTORY"`在`dataDir`变量为您想要保存生成的 PDF 文件的目录的路径。

#### 问：如何创建示例文档并向其中添加文本片段？

答：在本教程中，您可以使用`Document`类创建示例 PDF 文档并添加文本片段。此文本片段用作显示隐藏文本块的触发器。

#### 问：如何找到触发隐藏文本块的文本片段？

答：本教程演示了如何使用`TextFragmentAbsorber`对象查找触发隐藏文本块显示的文本片段。它在 PDF 文档中搜索特定的文本字符串。

#### 问：如何创建和自定义隐藏文本字段？

答：你创建一个`TextBoxField`对象来表示隐藏的文本字段。本教程提供了设置隐藏文本字段的各种属性（如位置、值、外观和行为）的代码。

#### 问：如何创建与隐藏文本块关联的隐形按钮？

答：使用以下方式创建不可见按钮字段：`ButtonField`类。此按钮字段位于触发文本片段的顶部，并具有与鼠标进入和退出事件相关的操作。这些操作控制隐藏文本块的可见性。

#### 问：我可以自定义隐藏文本块和触发区域的外观吗？

答：是的，您可以自定义隐藏文本字段和隐形按钮的各种属性，包括字体、颜色、大小和定位。

#### 问：如何保存修改后的隐藏文本块的文档？

答：本教程演示如何使用`Save`方法`Document`班级。