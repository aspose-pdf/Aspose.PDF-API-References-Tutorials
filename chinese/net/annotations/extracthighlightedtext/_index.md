---
title: 提取 PDF 文件中突出显示的文本
linktitle: 提取 PDF 文件中突出显示的文本
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南，了解如何使用 Aspose.PDF for .NET 提取 PDF 文件中突出显示的文本。
type: docs
weight: 60
url: /zh/net/annotations/extracthighlightedtext/
---
要提取 PDF 文件中突出显示的文本，您可以使用 Aspose.PDF for .NET API。此 API 提供了一种简单的方法来检索文档中突出显示的所有文本。

## 第 1 步：加载 PDF 文档

提取 PDF 文件中突出显示的文本的第一步是使用 Aspose.PDF for .NET API 加载文档。您可以通过创建一个新实例来完成此操作`Document`类并将 PDF 文档的路径作为参数传递。 

```csharp
//文档目录的路径。
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## 第 2 步：循环遍历所有注释

下一步是循环遍历 PDF 文档中的所有注释。您可以使用`foreach`循环，像这样：

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	//代码放在这里
}
```

## 步骤 3：过滤文本标记注释

在 - 的里面`foreach`循环中，您需要过滤掉所有不是文本标记注释的注释。您可以通过检查注释是否是`TextMarkupAnnotation`班级。

```csharp
if (annotation is TextMarkupAnnotation)
{
	//代码放在这里
}
```

## 步骤 4：检索突出显示的文本片段

过滤掉所有文本标记注释后，您可以检索每个注释的突出显示的文本片段。您可以通过调用来做到这一点`GetMarkedTextFragments()`方法上的`TextMarkupAnnotation`目的。

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## 第 5 步：显示突出显示的文本

最后，您可以向用户显示突出显示的文本。您可以通过循环遍历每个来完成此操作`TextFragment`对象在`TextFragmentCollection`并调用`Text`财产。

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### 使用 Aspose.PDF for .NET 提取突出显示文本的示例源代码

```csharp
//文档目录的路径。
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

## 结论

在本教程中，我们探讨了如何使用 Aspose.PDF for .NET 从 PDF 文档中提取突出显示的文本。通过遵循分步指南并使用提供的 C# 源代码，开发人员可以轻松提取和管理 PDF 文档中突出显示的文本。

### 提取 PDF 文件中突出显示文本的常见问题解答

#### 问：什么是 PDF 文档中的文本标记注释？

答：文本标记注释是突出显示或标记 PDF 文档中特定文本的注释。文本标记注释的示例包括突出显示、下划线和删除线。

#### 问：我可以使用 Aspose.PDF for .NET 从其他类型的注释中提取文本吗？

答：是的，Aspose.PDF for .NET 提供了多种方法从不同类型的注释中提取文本，包括文本标记注释、自由文本注释等。

#### 问：Aspose.PDF for .NET 支持从受密码保护的 PDF 文件中提取文本吗？

答：是的，Aspose.PDF for .NET 支持从受密码保护的 PDF 文件中提取文本。使用以下方式加载 PDF 文档时需要提供正确的密码`Document`班级。

#### 问：我可以根据其他条件（例如颜色或作者）过滤突出显示的文本吗？

答：是的，您可以根据其他条件（例如颜色、作者或创建日期）过滤突出显示的文本。 Aspose.PDF for .NET 提供了根据属性访问和过滤注释的方法。

#### 问：是否可以将提取的突出显示文本保存到单独的文件中？

答：是的，您可以将提取的突出显示文本保存到单独的文件中或将其存储在数据结构中以供进一步处理或分析。
