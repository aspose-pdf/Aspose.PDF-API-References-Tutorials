---
title: 设置目标链接
linktitle: 设置目标链接
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中设置目标链接。
type: docs
weight: 100
url: /zh/net/programming-with-links-and-actions/set-target-link/
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
Document document = new Document(dataDir + "UpdateLinks.pdf");
```

## 第 3 步：编辑目标链接

使用以下代码获取要修改的链接注释：

```csharp
LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
```

您可以调整`[1]`用于选择特定页面或注释的索引。

接下来，更新目标而不更新文件：

```csharp
goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
```

如果您还想更新文件：

```csharp
goToR.File = new FileSpecification(dataDir + "input.pdf");
```

## 第 4 步：使用更新后的链接保存文档

使用更新的链接保存文档`Save`方法：

```csharp
dataDir = dataDir + "SetTargetLink_out.pdf";
document. Save(dataDir);
```

## 第 5 步：显示结果

显示一条消息，指示目标链接已成功配置，并指定保存文件的位置：

```csharp
Console.WriteLine("\nConfiguration of target link successful.\nFile saved at location: " + dataDir);
```

### 使用 Aspose.PDF for .NET 设置目标链接的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//加载 PDF 文件
	Document document = new Document(dataDir + "UpdateLinks.pdf");
	LinkAnnotation linkAnnot = (LinkAnnotation)document.Pages[1].Annotations[1];
	GoToRemoteAction goToR = (GoToRemoteAction)linkAnnot.Action;
	//下一行更新目标，不更新文件
	goToR.Destination = new XYZExplicitDestination(2, 0, 0, 1.5);
	//下一行更新文件
	goToR.File = new FileSpecification(dataDir +  "input.pdf");
	dataDir = dataDir + "SetTargetLink_out.pdf";
	//使用更新的链接保存文档
	document.Save(dataDir);
	Console.WriteLine("\nTarget link setup successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论

恭喜！您现在知道如何使用 Aspose.PDF for .NET 在 PDF 文件中设置目标链接。使用这些知识来自定义 PDF 文档中的链接并为用户创建交互式体验。

现在您已经完成了本指南，您可以将这些概念应用到您自己的项目中并进一步探索 Aspose.PDF for .NET 提供的功能。