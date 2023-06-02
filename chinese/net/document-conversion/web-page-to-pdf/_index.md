---
title: 网页转PDF
linktitle: 网页转PDF
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将网页转换为 PDF 的分步指南。
type: docs
weight: 320
url: /zh/net/document-conversion/web-page-to-pdf/
---

在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 库将网页转换为 PDF。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。在本教程结束时，您将能够毫不费力地将网页转换为 PDF 文档。

## 介绍
将网页转换为 PDF 格式是许多应用程序中的常见要求。通过将网页内容转换为 PDF，您可以轻松保留原始网页的布局、格式和图像。 Aspose.PDF for .NET 是一个功能强大的库，可让您高效准确地执行此转换。

## 要求
在我们开始之前，请确保您具备以下先决条件：
- 计算机上安装的 Visual Studio
- Aspose.PDF for .NET library（可以到Aspose官网下载）
- C#编程基础知识


## 第 1 步：定义文档目录
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
代替`"YOUR DOCUMENT DIRECTORY"`使用要保存生成的 PDF 文件的路径。

## 第 2 步：创建 Web 请求
```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
创建一个 Web 请求对象并指定要转换的网页的 URL。您可以将 URL 替换为任何所需的网页。

## 第 3 步：获取 Web 响应
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
发送 Web 请求并从服务器检索响应。

## 第 4 步：阅读网页内容
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
使用 a 读取网页内容`StreamReader`并将其存储在`responseFromServer`多变的。

## 第 5 步：将 HTML 转换为 PDF
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://en.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
创建一个`MemoryStream`对象加载网页内容。然后，创建一个实例`HtmlLoadOptions`并传递网页的基本 URL。接下来，创建一个`Document`使用加载流和 HTML 加载选项的对象。设置`IsLandscape`财产给`true`如果您希望 PDF 横向显示。最后将PDF文档保存到指定目录

.

## 第 6 步：处理异常
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
捕获转换过程中可能发生的任何异常并显示错误消息。

### 使用 Aspose.Words for .NET 将网页转为 PDF 的示例源代码

```csharp
try
{
	
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//创建对 URL 的请求。
	WebRequest request = WebRequest.Create("https://En.wikipedia.org/wiki/Main_Page");
	//如果服务器需要，请设置凭据。
	request.Credentials = CredentialCache.DefaultCredentials;
	//请求超时前的超时毫秒数
	//Request.Timeout = 100;

	//得到回应。
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	//获取包含服务器返回内容的流。
	Stream dataStream = response.GetResponseStream();
	//使用 StreamReader 打开流以便于访问。
	StreamReader reader = new StreamReader(dataStream);
	//阅读内容。
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
	HtmlLoadOptions options = new HtmlLoadOptions("https:// en.wikipedia.org/wiki/");


	//加载 HTML 文件
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	//将输出另存为 PDF 格式
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 库将网页转换为 PDF。我们通过分步指南解释了所提供的 C# 源代码。按照这些说明，您可以轻松地将网页到 PDF 的转换功能集成到您自己的 .NET 应用程序中。