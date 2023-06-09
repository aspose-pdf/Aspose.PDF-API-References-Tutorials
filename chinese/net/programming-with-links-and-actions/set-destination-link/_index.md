---
title: 设置目标链接
linktitle: 设置目标链接
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中设置目标链接。
type: docs
weight: 90
url: /zh/net/programming-with-links-and-actions/set-destination-link/
---

通过此分步指南了解如何使用 Aspose.PDF for .NET 在 PDF 文件中设置目标链接。

## 第 1 步：设置环境

确保您已经使用 C# 项目和适当的 Aspose.PDF 参考设置了您的开发环境。

## 第 2 步：加载 PDF 文件

使用以下代码设置文档的目录路径并上传 PDF 文件：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//加载 PDF 文件
Document doc = new Document(dataDir + "UpdateLinks.pdf");
```

## 第 3 步：编辑目标链接

使用以下代码获取要修改的链接注释：

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
```

您可以调整`[1]`用于选择特定页面或注释的索引。

接下来，通过更改链接操作并将目标设置为网址来编辑链接：

```csharp
linkAnnot.Action = new GoToURIAction("www.aspose.com");
```

## 第 4 步：使用更新后的链接保存文档

使用更新的链接保存文档`Save`方法：

```csharp
dataDir = dataDir + "SetDestinationLink_out.pdf";
doc.Save(dataDir);
```

## 第 5 步：显示结果

显示一条消息，指示目标链接已成功配置并指定保存文件的位置：

```csharp
Console.WriteLine("\nDestination link configured successfully.\nFile saved to location: " + dataDir);
```

### 使用 Aspose.PDF for .NET 设置目标链接的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//加载 PDF 文件
	Document doc = new Document(dataDir + "UpdateLinks.pdf");
	//从文档的第一页获取第一个链接注释
	LinkAnnotation linkAnnot = (LinkAnnotation)doc.Pages[1].Annotations[1];
	//修改链接：更改链接动作，将目标设置为网址
	linkAnnot.Action = new GoToURIAction("www.aspose.com");           
	dataDir = dataDir + "SetDestinationLink_out.pdf";
	//使用更新的链接保存文档
	doc.Save(dataDir);
	Console.WriteLine("\nDestination link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论

恭喜！您现在知道如何使用 Aspose.PDF for .NET 在 PDF 文件中设置目标链接。使用这些知识来自定义 PDF 文档中的链接并为用户创建交互式体验。

现在您已经完成了本指南，您可以将这些概念应用到您自己的项目中并进一步探索 Aspose.PDF for .NET 提供的功能。