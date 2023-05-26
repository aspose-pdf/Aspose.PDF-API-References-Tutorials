---
title: 提取突出显示的文本
linktitle: 提取突出显示的文本
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南了解如何使用 Aspose.PDF for .NET 提取突出显示的文本。
type: docs
weight: 60
url: /zh/net/annotations/extracthighlightedtext/
---
要从 PDF 文档中提取突出显示的文本，您可以使用 Aspose.PDF for .NET API。此 API 提供了一种简单的方法来检索文档中已突出显示的所有文本。

## 第 1 步：加载 PDF 文档

从 PDF 文档中提取高亮文本的第一步是使用 Aspose.PDF for .NET API 加载文档。您可以通过创建一个新的实例来做到这一点`Document`类并将 PDF 文档的路径作为参数传递。 

```csharp
//文档目录的路径。
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## 第 2 步：循环遍历所有注释

下一步是遍历 PDF 文档中的所有注释。您可以使用`foreach`循环，像这样：

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	//代码在这里
}
```

## 第 3 步：过滤文本标记注释

在 - 的里面`foreach`循环，您将需要过滤掉所有不是文本标记注释的注释。您可以通过检查注释是否是`TextMarkupAnnotation`班级。

```csharp
if (annotation is TextMarkupAnnotation)
{
	//代码在这里
}
```

## 第 4 步：检索突出显示的文本片段

过滤掉所有文本标记注释后，您可以为每个注释检索突出显示的文本片段。您可以通过调用`GetMarkedTextFragments()`上的方法`TextMarkupAnnotation`目的。

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## 第 5 步：显示突出显示的文本

最后，您可以向用户显示突出显示的文本。您可以通过遍历每个`TextFragment`中的对象`TextFragmentCollection`并调用`Text`财产。

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

