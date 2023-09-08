---
title: 从 Html 转换后删除超链接
linktitle: 从 Html 转换后删除超链接
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 HTML 转换为 PDF 后删除超链接的分步指南。
type: docs
weight: 250
url: /zh/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
在本教程中，我们将引导您完成从使用 Aspose.PDF for .NET 从 HTML 文件生成的 PDF 文件中删除超链接的过程。超链接是可以重定向到其他页面或网站的可点击链接。通过执行以下步骤，您将能够从生成的 PDF 文件中删除超链接。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- 您的系统上安装了适用于 .NET 的 Aspose.PDF 库。
- 开发环境，例如 Visual Studio。

## 第 1 步：加载 HTML 文件并删除超链接
在此步骤中，我们将加载 HTML 文件并从生成的 PDF 文档中删除超链接。使用以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//使用 HTML 加载选项加载 HTML 文件
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());

//浏览文档第一页的注释
foreach(Annotation a in doc.Pages[1].Annotations)
{
     //检查注释是否是链接
     if (a.AnnotationType == AnnotationType.Link)
     {
         LinkAnnotation the = (LinkAnnotation)a;
        
         //检查操作是否属于 GoToURIAction 类型
         if (the.Action is GoToURIAction)
         {
             GoToURIAction gta = (GoToURIAction)the.Action;
             gta.URI = "";
            
             //使用文本片段吸收器查找匹配的文本片段
             TextFragmentAbsorber tfa = new TextFragmentAbsorber();
             tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
             doc.Pages[a.PageIndex].Accept(tfa);
            
             //循环遍历匹配的文本片段并从超链接中删除属性
             foreach(TextFragment tf in tfa.TextFragments)
             {
                 tf.TextState.Underline = false;
                 tf.TextState.ForegroundColor = Color.Black;
             }
         }
        
         //从页面中删除注释
         doc.Pages[a.PageIndex].Annotations.Delete(a);
     }
}
```

一定要更换`"YOUR DOCUMENTS DIRECTORY"`与 HTML 文件所在的实际目录。

## 第 2 步：保存生成的 PDF 文件
最后，我们将保存生成的不带超链接的 PDF 文件。使用以下代码：

```csharp
//保存生成的 PDF 文件
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

上面的代码使用文件名保存生成的 PDF 文件`"RemoveHyperlinksFromText_out.pdf"`.

### 使用 Aspose.PDF for .NET 从 Html 转换后删除超链接的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
doc.Save(new MemoryStream());
foreach (Annotation a in doc.Pages[1].Annotations)
{
	if (a.AnnotationType == AnnotationType.Link)
	{
		LinkAnnotation la = (LinkAnnotation)a;
		if (la.Action is GoToURIAction)
		{
			GoToURIAction gta = (GoToURIAction)la.Action;
			gta.URI = "";
			TextFragmentAbsorber tfa = new TextFragmentAbsorber();
			tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
			doc.Pages[a.PageIndex].Accept(tfa);
			foreach (TextFragment tf in tfa.TextFragments)
			{
				tf.TextState.Underline = false;
				tf.TextState.ForegroundColor = Color.Black;
			}
		}
		doc.Pages[a.PageIndex].Annotations.Delete(a);
	}
}
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 从 HTML 文件生成的 PDF 文件中删除超链接的分步过程。按照上述说明操作，您将能够成功从生成的 PDF 文件中删除超链接。

### 常见问题解答

#### 问：什么是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一个功能强大的库，使开发人员能够在 C# 应用程序中处理 PDF 文档。它提供了广泛的功能，包括将 HTML 文件转换为 PDF 和操作 PDF 内容的能力。

#### 问：为什么我要从 PDF 文件中删除超链接？

答：从 PDF 文件中删除超链接的原因有多种。例如，您可能希望消除用于打印或存档目的的外部链接，或者确保 PDF 内容无法通过超链接进行导航。

#### 问：如何使用 Aspose.PDF for .NET 加载 HTML 文件并删除超链接？

答：要加载 HTML 文件并删除超链接，您可以使用 Aspose.PDF for .NET`HtmlLoadOptions`班级。迭代 PDF 页面的注释以查找链接注释并修改其属性。

#### 问：我可以自定义生成的 PDF 的输出文件名吗？

答：是的，您可以通过修改保存 PDF 文档的代码来自定义生成的 PDF 文件的输出文件名。只需更改所需的文件名即可`doc.Save()`方法。

#### 问：是否可以根据某些条件有选择地删除超链接？

答：是的，您可以根据特定条件有选择地删除超链接。例如，您可以选择仅删除外部链接或指向特定 URL 的链接。