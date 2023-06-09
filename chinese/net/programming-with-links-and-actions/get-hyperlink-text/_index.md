---
title: 获取超链接文本
linktitle: 获取超链接文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 文件中提取超链接文本。
type: docs
weight: 70
url: /zh/net/programming-with-links-and-actions/get-hyperlink-text/
---

通过此分步指南，了解如何使用 Aspose.PDF for .NET 从 PDF 文件的超链接中提取文本。

## 第 1 步：设置环境

确保您已经使用 C# 项目和适当的 Aspose.PDF 参考设置了您的开发环境。

## 第 2 步：加载 PDF 文件

使用以下代码设置文档的目录路径并上传 PDF 文件：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//加载 PDF 文件
Document document = new Document(dataDir + "input.pdf");
```

## 第 3 步：浏览文档页面

使用 a 遍历文档的每一页`foreach`环形：

```csharp
foreach(Page page in document.Pages)
{
     //显示链接注释
     ShowLinkAnnotations(page);
}
```

## 第 4 步：错误处理

添加错误处理以捕获任何异常并显示相应的错误消息：

```csharp
catch (Exception ex)
{
     Console.WriteLine(ex.Message);
}
```

### 使用 Aspose.PDF for .NET 获取超链接文本的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//加载 PDF 文件
	Document document = new Document(dataDir + "input.pdf");
	//遍历 PDF 的每一页
	foreach (Page page in document.Pages)
	{
		//显示链接注释
		ShowLinkAnnotations(page);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论

恭喜！您现在知道如何使用 Aspose.PDF for .NET 从 PDF 文件中提取超链接文本。您可以使用这些知识来处理项目中的超链接并自动执行与 PDF 文件相关的任务。

现在您已经完成了本指南，您可以将这些概念应用到您自己的项目中并进一步探索 Aspose.PDF for .NET 提供的功能。