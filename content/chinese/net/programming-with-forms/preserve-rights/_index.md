---
title: 保留权利
linktitle: 保留权利
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 保留 PDF 文档中的表单权限。
type: docs
weight: 210
url: /zh/net/programming-with-forms/preserve-rights/
---
在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 保留 PDF 文档中的表单权限。我们将逐步解释 C# 源代码以指导您完成此过程。

## 步骤 1：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：打开文档

使用打开源 PDF 文档`FileStream`具有读写权限：

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## 步骤 3：编辑表单字段

浏览文档中的所有表单字段并进行必要的更改。在此示例中，我们将更改名称中包含“A1”的表单字段的值：

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

## 步骤 4：保存更新的文档

保存修改后的PDF文档：

```csharp
pdfDocument.Save();
```

## 步骤 5：关闭`FileStream`

不要忘记关闭`FileStream`完成后的对象：

```csharp
fs. Close();
```

### 使用 Aspose.PDF for .NET 保留权限的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//使用 FileAccess 的读写功能读取源 PDF 格式。
//我们需要 ReadWrite 权限，因为修改后，
//我们需要将更新的内容保存在同一个文档/文件中。
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
//实例化 Document 实例
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
//获取所有字段的值
foreach (Field formField in pdfDocument.Form)
{
	//如果字段全名包含A1，则执行操作
	if (formField.FullName.Contains("A1"))
	{
		//将表单字段转换为文本框
		TextBoxField textBoxField = formField as TextBoxField;
		//修改字段值
		textBoxField.Value = "Testing";
	}
}
//将更新后的文档保存在 FileStream 中
pdfDocument.Save();
//关闭文件流对象
fs.Close();
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 保留 PDF 文档中表单的权限。通过遵循这些步骤，您可以轻松访问表单字段并进行特定更改，同时保留访问和写入权限。


### 常见问题解答

#### 问：我可以保留特定表单域的权限而不影响 PDF 文档中的其他域吗？

答：是的，通过使用`FullName`表单字段的属性，您可以针对特定的表单字段进行保存，同时不影响其他字段。

#### 问：我可以保留受密码保护的 PDF 文档中表单的权限吗？

答：是的，Aspose.PDF for .NET 允许您即使在受密码保护的 PDF 文档中保留表单的权限，只要您提供正确的密码来访问和修改文件。

#### 问：如果我尝试修改表单字段而没有适当的访问权限，会发生什么情况？

答：如果您尝试在没有适当访问权限的情况下修改表单字段，则更改将不会保存在 PDF 文档中，并且您可能会收到异常或错误消息。

#### 问：Aspose.PDF for .NET 是否与所有版本的 .NET Framework 兼容？

答：是的，Aspose.PDF for .NET 与所有版本的 .NET Framework 兼容，包括 .NET Core 和 .NET Standard。

#### 问：除了 C# 之外，我还可以使用其他编程语言以编程方式保留 PDF 文档中的表单权限吗？

答：是的，Aspose.PDF for .NET 除了支持 C# 之外，还支持多种编程语言，例如 VB.NET 和 ASP.NET。