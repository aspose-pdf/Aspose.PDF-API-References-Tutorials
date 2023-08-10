---
title: 维护权利
linktitle: 维护权利
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 保留 PDF 文档中的表单权限。
type: docs
weight: 210
url: /zh/net/programming-with-forms/preserve-rights/
---
在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 保留 PDF 文档中的表单权限。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第 1 步：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤 2：打开文档

使用以下命令打开源 PDF 文档`FileStream`具有读写权限：

```csharp
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## 第 3 步：编辑表单字段

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

## 步骤 4：保存更新后的文档

保存修改后的PDF文档：

```csharp
pdfDocument.Save();
```

## 第 5 步：关闭`FileStream`

不要忘记关闭`FileStream`完成后对象：

```csharp
fs. Close();
```

### 使用 Aspose.PDF for .NET 保留权利的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//使用 Read 和 Write 的 FileAccess 读取源 PDF 表单。
//我们需要读写权限，因为修改后，
//我们需要将更新的内容保存在同一个文档/文件中。
FileStream fs = new FileStream(dataDir + "input.pdf", FileMode.Open, FileAccess.ReadWrite);
//实例化文档实例
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
//从所有字段获取值
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
//将更新后的文档保存在 save FileStream 中
pdfDocument.Save();
//关闭文件流对象
fs.Close();
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 保留 PDF 文档中表单的权限。通过执行这些步骤，您可以轻松访问表单字段并进行特定更改，同时保留访问和写入权限。


### 常见问题解答

#### 问：我可以保留特定表单字段的权利而不影响 PDF 文档中的其他字段吗？

答：是的，通过使用`FullName`表单字段的属性，您可以针对特定的表单字段进行保存，同时使其他字段不受影响。

#### 问：我可以保留受密码保护的 PDF 文档中表单的权利吗？

答：是的，Aspose.PDF for .NET 允许您保留表单的权利，即使在受密码保护的 PDF 文档中，只要您提供正确的密码来访问和修改文件。

#### 问：如果我尝试在没有适当访问权限的情况下修改表单字段，会发生什么情况？

答：如果您在没有适当访问权限的情况下尝试修改表单字段，所做的更改将不会保存在 PDF 文档中，并且您可能会收到异常或错误消息。

#### 问：Aspose.PDF for .NET 是否与所有版本的 .NET Framework 兼容？

答：是的，Aspose.PDF for .NET 与所有版本的 .NET Framework 兼容，包括 .NET Core 和 .NET Standard。

#### 问：除了 C# 之外，我还可以使用其他编程语言以编程方式保留 PDF 文档中的表单权限吗？

答：是的，除了 C# 之外，Aspose.PDF for .NET 还支持各种编程语言，例如 VB.NET 和 ASP.NET。