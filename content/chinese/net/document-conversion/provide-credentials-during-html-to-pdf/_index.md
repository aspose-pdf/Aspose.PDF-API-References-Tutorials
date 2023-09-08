---
title: 在 HTML 转 PDF 过程中提供凭据
linktitle: 在 HTML 转 PDF 过程中提供凭据
second_title: Aspose.PDF for .NET API 参考
description: 通过使用 Aspose.PDF for .NET 提供凭据来将 HTML 转换为 PDF 的分步指南。
type: docs
weight: 240
url: /zh/net/document-conversion/provide-credentials-during-html-to-pdf/
---
在本教程中，我们将引导您完成将 HTML 文件转换为 PDF 的过程，同时在使用 Aspose.PDF for .NET 访问安全 URL 时提供凭据。通过执行以下步骤，您将能够使用适当的凭据将 HTML 内容转换为 PDF。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- 您的系统上安装了适用于 .NET 的 Aspose.PDF 库。
- 开发环境，例如 Visual Studio。

## 第 1 步：获取安全的 HTML 内容
在此步骤中，我们将使用适当的凭据从 URL 获取安全的 HTML 内容。使用以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建 URL 请求。
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
//如果服务器需要，请设置凭据。
request.Credentials = CredentialCache.DefaultCredentials;
//得到回应。
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

//获取包含服务器返回内容的流。
Stream dataStream = response. GetResponseStream();
//使用 StreamReader 打开流以方便访问。
StreamReader reader = new StreamReader(dataStream);
//阅读内容。
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

一定要更换`"YOUR DOCUMENTS DIRECTORY"`与您要保存生成的 PDF 文件的实际目录。

## 第 2 步：通过提供凭据将 HTML 转换为 PDF
现在，我们将加载检索到的 HTML 内容并将其转换为 PDF 格式，同时提供适当的凭据。使用以下代码：

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

//加载 HTML 文件
Document pdfDocument = new Document(stream, options);
```

## 步骤 3：保存生成的 PDF 文件
最后，我们将保存生成的 PDF 文件。使用以下代码：

```csharp
//保存生成的 PDF 文件
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

上面的代码使用文件名保存生成的 PDF 文件`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### 使用 Aspose.PDF for .NET 在 HTML 转 PDF 期间提供凭据的示例源代码

```csharp
try
{
	
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//创建 URL 请求。
	WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	//如果服务器需要，请设置凭据。
	request.Credentials = CredentialCache.DefaultCredentials;
	//得到回应。
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	//获取包含服务器返回内容的流。
	Stream dataStream = response.GetResponseStream();
	//使用 StreamReader 打开流以方便访问。
	StreamReader reader = new StreamReader(dataStream);
	//阅读内容。
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
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
在本教程中，我们介绍了将 HTML 文件转换为 PDF 的分步过程，同时在使用 Aspose.PDF for .NET 访问安全 URL 时提供凭据。按照上述说明，您将能够在提供正确的凭据的同时成功将 HTML 内容转换为 PDF。

### 常见问题解答

#### 问：什么是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一个强大的库，使开发人员能够在 C# 应用程序中处理 PDF 文档。它提供了广泛的功能，包括 HTML 到 PDF 的转换。

#### 问：如何从 URL 获取安全的 HTML 内容？

答：要从 URL 获取安全的 HTML 内容，您可以使用`WebRequest`C# 中的类。确保使用设置适当的凭据`Credentials`财产。

#### 问：本教程的先决条件是什么？

答：在继续学习本教程之前，请确保您满足以下先决条件：

- C# 编程语言的基础知识。
- 您的系统上安装了适用于 .NET 的 Aspose.PDF 库。
- 开发环境，例如 Visual Studio。

#### 问：Aspose.PDF for .NET 在将 HTML 转换为 PDF 时如何处理外部资源？

答：Aspose.PDF for .NET 提供了`HtmlLoadOptions`类在 HTML 到 PDF 转换期间处理外部资源。您可以使用以下命令设置外部资源凭据`ExternalResourcesCredentials`财产。

#### 问：我可以自定义生成的 PDF 文件的文件名吗？

答：是的，您可以通过修改保存 PDF 文档的代码来自定义生成的 PDF 文件的文件名。只需更改所需的文件名即可`pdfDocument.Save()`方法。