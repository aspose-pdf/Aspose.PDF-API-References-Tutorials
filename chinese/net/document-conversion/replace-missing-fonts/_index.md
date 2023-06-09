---
title: 替换丢失的字体
linktitle: 替换丢失的字体
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 替换 PDF 文件中缺失字体的分步指南。
type: docs
weight: 260
url: /zh/net/document-conversion/replace-missing-fonts/
---

在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 替换 PDF 文件中缺失字体的过程。当您在缺少特定字体的机器上打开 PDF 文件时，可能会出现字体显示问题。在这种情况下，可以用机器上可用的另一种字体替换丢失的字体。按照以下步骤，您将能够替换 PDF 文件中丢失的字体。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- .NET 的 Aspose.PDF 库安装在您的系统上。
- 开发环境，例如 Visual Studio。

## 第 1 步：查找丢失的字体
第一步是在 PDF 文件中找到丢失的字体。使用以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
     //找到原始字体
     originalFont = FontRepository.FindFont("AgencyFB");
}
catch(Exception)
{
     //目标机器上缺少字体
     //添加简单的字体替换
     FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用您的 PDF 文件所在的实际目录。

## 第 2 步：替换丢失的字体
接下来，我们将用另一种可用字体替换丢失的字体。使用以下代码：

```csharp
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");

//将 PDF 文件转换为 PDF/A 格式并删除错误
pdf.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

//保存生成的 PDF 文件
pdf.Save(fileNew.FullName);
```

务必更换`"input.pdf"`使用原始 PDF 文件的实际路径和`"newfile_out.pdf"`使用生成的 PDF 文件的所需名称。

## 第 3 步：保存生成的 PDF 文件
最后，我们将使用替换后的字体保存生成的 PDF 文件。使用以下代码：

```csharp
//保存生成的 PDF 文件
pdf.Save(fileNew.FullName);
```

确保已为生成的 PDF 文件设置正确的目标路径。

### 使用 Aspose.PDF for .NET 替换缺失字体的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Text.Font originalFont = null;
try
{
	originalFont = FontRepository.FindFont("AgencyFB");
}
catch (Exception)
{
	//目标机器上缺少字体
	FontRepository.Substitutions.Add(new SimpleFontSubstitution("AgencyFB", "Arial"));
}
var fileNew = new FileInfo(dataDir + "newfile_out.pdf");
var pdf = new Document(dataDir + "input.pdf");
pdf.Convert( dataDir +  "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
pdf.Save(fileNew.FullName);
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 替换 PDF 文件中缺失字体的分步过程。按照上述说明，您将能够成功替换 PDF 文件中缺失的字体。