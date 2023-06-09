---
title: 在 HTML 到 PDF 期间提供凭据
linktitle: 在 HTML 到 PDF 期间提供凭据
second_title: Aspose.PDF for .NET API 参考
description: 通过为 .NET 提供 Aspose.PDF 凭据，逐步指导将 HTML 转换为 PDF。
type: docs
weight: 240
url: /zh/net/document-conversion/provide-credentials-during-html-to-pdf/
---

在本教程中，我们将引导您完成将 HTML 文件转换为 PDF 的过程，同时在使用 Aspose.PDF for .NET 访问安全 URL 时提供凭据。按照以下步骤，您将能够使用适当的凭据将 HTML 内容转换为 PDF。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- .NET 的 Aspose.PDF 库安装在您的系统上。
- 开发环境，例如 Visual Studio。

## 第 1 步：获取安全的 HTML 内容
在此步骤中，我们将使用适当的凭据从 URL 中获取安全的 HTML 内容。使用以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建对 URL 的请求。
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
//如果服务器需要，请设置凭据。
request.Credentials = CredentialCache.DefaultCredentials;
//得到回应。
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

//获取包含服务器返回内容的流。
Stream dataStream = response. GetResponseStream();
//使用 StreamReader 打开流以便于访问。
StreamReader reader = new StreamReader(dataStream);
//阅读内容。
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用您要保存生成的 PDF 文件的实际目录。

## 第 2 步：通过提供凭据将 HTML 转换为 PDF
现在我们将加载检索到的 HTML 内容并将其转换为 PDF 格式，同时提供适当的凭据。使用以下代码：

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://我的.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

//加载 HTML 文件
Document pdfDocument = new Document(stream, options);
```

## 第 3 步：保存生成的 PDF 文件
最后，我们将保存生成的 PDF 文件。使用以下代码：

```csharp
//保存生成的 PDF 文件
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

上面的代码使用文件名保存生成的 PDF 文件`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### 使用 Aspose.PDF for .NET 在 HTML 到 PDF 期间提供凭据的示例源代码

```csharp
try
{
	
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//创建对 URL 的请求。
	WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	//如果服务器需要，请设置凭据。
	request.Credentials = CredentialCache.DefaultCredentials;
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

	HtmlLoadOptions options = new HtmlLoadOptions("http://我的.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	//加载 HTML 文件
	Document pdfDocument = new Document(stream, options);
	//保存结果文件
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论
在本教程中，我们介绍了将 HTML 文件转换为 PDF 的分步过程，同时在使用 Aspose.PDF for .NET 访问安全 URL 时提供凭据。按照上述说明，您将能够在提供正确凭据的同时成功地将 HTML 内容转换为 PDF。