---
title: 维护权利
linktitle: 维护权利
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 保留 PDF 文档中的表单权限。
type: docs
weight: 210
url: /zh/net/programming-with-forms/preserve-rights/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 在 PDF 文档中保留表单权限。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第一步：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：打开文档

使用`FileStream`具有读写权限：

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## 第 3 步：编辑表单域

浏览文档中的所有表单域并进行必要的更改。在此示例中，我们正在更改名称中包含“A1”的表单字段的值：

```csharp
foreach(Field formField in pdfDocument.Form)
{
if (formField.FullName.Contains("A1"))
{
TextBoxField textBoxField = formField as TextBoxField;
textBoxField.Value = "Testing";
}
}
```

## 第 4 步：保存更新后的文档

保存修改后的 PDF 文档：

```csharp
pdfDocument.Save();
```

## 第 5 步：关闭`FileStream`

不要忘记关闭`FileStream`完成后反对：

```csharp
fs. Close();
```

### 使用 Aspose.Words for .NET 的保留权限示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//使用读取和写入的文件访问权限读取源 PDF 表单。
//我们需要读写权限，因为修改后，
//我们需要将更新的内容保存在同一个文档/文件中。
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
//实例化文档实例
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
//从所有字段中获取值
foreach (Field formField in pdfDocument.Form)
{
	//如果字段的全名包含A1，则执行操作
	if (formField.FullName.Contains("A1"))
	{
		//将表单字段转换为 TextBox
		TextBoxField textBoxField = formField as TextBoxField;
		//修改字段值
		textBoxField.Value = "Testing";
	}
}
//将更新的文档保存在 save FileStream 中
pdfDocument.Save();
//关闭文件流对象
fs.Close();
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 保留 PDF 文档中表单的权限。通过执行这些步骤，您可以轻松访问表单字段并进行特定更改，同时保留访问和写入权限。
