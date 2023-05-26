---
title: 设置打印对话框的属性
linktitle: 设置打印对话框的属性
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用分步指南在 Aspose.PDF for .NET 中设置打印对话框的属性。
type: docs
weight: 320
url: /zh/net/programming-with-document/setpropertiesforprintdialog/
---
下面是使用 Aspose.PDF for .NET 设置打印对话框属性的分步指南：


## 第 1 步：定义您的 PDF 文档所在的目录：

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";
```
   
## 第 2 步：创建一个新的实例`Document` class:

```csharp
using (Document doc = new Document())
{
  //代码在这里
}
```
   
## 第 3 步：向文档添加新页面：

```csharp
doc.Pages.Add();
```
   
## 第 4 步：将双工属性设置为`DuplexFlipLongEdge`:

```csharp
doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
```
   
## 第五步：以指定的文件名和格式保存文档：

```csharp
doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
```

## 结论

Aspose.PDF for .NET 可以轻松设置 PDF 文件中打印对话框的属性。按照上面的分步指南，您可以快速优化 PDF 文件以进行打印。

### 使用 Aspose.PDF for .NET 设置打印对话框属性的示例源代码

```csharp

	var dataDir = "YOUR DOCUMENT DIRECTORY";

	using (Document doc = new Document())
	{
		doc.Pages.Add();
		doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
		doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
	}

```
