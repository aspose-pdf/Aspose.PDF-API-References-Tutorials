---
title: 隐藏文本块
linktitle: 隐藏文本块
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 中创建隐藏文本块。
type: docs
weight: 230
url: /zh/net/programming-with-text/hidden-text-block/
---

在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库创建隐藏文本块。隐藏文本块是浮动文本，当鼠标光标悬停在特定区域上时，该文本块变得可见。我们将使用提供的 C# 源代码逐步完成创建隐藏文本块的过程。

## 要求

在开始之前，请确保您具备以下条件：

- 安装了 Aspose.PDF for .NET 库。
- 对 C# 编程有基本了解。

## 第 1 步：设置文档目录

首先，您需要设置要保存生成的 PDF 文件的目录路径。代替`"YOUR DOCUMENT DIRECTORY"`在里面`dataDir`变量包含您所需目录的路径。

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

现在，我们使用以下命令打开之前创建的文档`Document`班级。

```csharp
Document document = new Document(outputFile);
```

## 第四步：找到文本片段

我们使用一个`TextFragmentAbsorber`对象查找将触发隐藏文本块显示的文本片段。在本例中，我们正在搜索确切的文本“将鼠标光标移至此处以显示浮动文本”。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
document.Pages.Accept(absorb);
TextFragmentCollection textFragments = absorb.TextFragments;
TextFragment fragment = textFragments[1];
```

## 第 5 步：创建隐藏文本字段

我们创建一个`TextBoxField`对象来表示隐藏的文本字段。该字段将包含当鼠标光标悬停在触发器文本上时变得可见的文本。

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

## 步骤 6：将隐藏文本字段添加到文档中

我们将隐藏文本字段添加到文档的表单集合中。

```csharp
document.Form.Add(floatingField);
```

## 第7步：创建隐形按钮

我们创建一个不可见的按钮字段，该字段将位于触发器文本片段的顶部。该按钮字段将具有与鼠标进入和退出事件相关的操作。

```csharp
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
document.Form.Add(buttonField);
```

## 第 8 步：保存文档

最后，我们使用隐藏文本块保存修改后的文档。

```csharp
document. Save(outputFile);
```

### 使用 Aspose.PDF for .NET 的隐藏文本块的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "TextBlock_HideShow_MouseOverOut_out.pdf";
//创建带有文本的示例文档
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display floating text"));
doc.Save(outputFile);
//打开包含文本的文档
Document document = new Document(outputFile);
//创建 TextAbsorber 对象以查找与正则表达式匹配的所有短语
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display floating text");
//接受文档页面的吸收器
document.Pages.Accept(absorber);
//获取第一个提取的文本片段
TextFragmentCollection textFragments = absorber.TextFragments;
TextFragment fragment = textFragments[1];
//为页面指定矩形中的浮动文本创建隐藏文本字段
TextBoxField floatingField = new TextBoxField(fragment.Page, new Rectangle(100, 700, 220, 740));
//设置要显示为字段值的文本
floatingField.Value = "This is the \"floating text field\".";
//我们建议在这种情况下将字段设置为“只读”
floatingField.ReadOnly = true;
//设置“隐藏”标志以使字段在打开文档时不可见
floatingField.Flags |= AnnotationFlags.Hidden;
//设置唯一的字段名称不是必需的，但允许
floatingField.PartialName = "FloatingField_1";
//设置字段外观的特征不是必需的，但可以使其更好
floatingField.DefaultAppearance = new DefaultAppearance("Helv", 10, System.Drawing.Color.Blue);
floatingField.Characteristics.Background = System.Drawing.Color.LightBlue;
floatingField.Characteristics.Border = System.Drawing.Color.DarkBlue;
floatingField.Border = new Border(floatingField);
floatingField.Border.Width = 1;
floatingField.Multiline = true;
//将文本字段添加到文档中
document.Form.Add(floatingField);
//在文本片段位置创建不可见按钮
ButtonField buttonField = new ButtonField(fragment.Page, fragment.Rectangle);
//为指定字段（注释）和不可见标志创建新的隐藏操作。
//（如果您在上面指定了浮动字段，您也可以通过名称引用浮动字段。）
//在不可见的按钮字段中添加鼠标进入/退出的操作
buttonField.Actions.OnEnter = new HideAction(floatingField, false);
buttonField.Actions.OnExit = new HideAction(floatingField);
//将按钮字段添加到文档中
document.Form.Add(buttonField);
//保存文档
document.Save(outputFile);
```

## 结论

在本教程中，您学习了如何使用 Aspose.PDF for .NET 库创建隐藏文本块。通过遵循分步指南，您可以生成带有隐藏文本字段的 PDF 文档，当鼠标光标悬停在特定区域上时，隐藏文本字段将变为可见。您可以根据您的要求自定义隐藏文本块的外观和行为。