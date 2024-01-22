---
title: 在 HTML 轉 PDF 過程中提供憑證
linktitle: 在 HTML 轉 PDF 過程中提供憑證
second_title: Aspose.PDF for .NET API 參考
description: 透過使用 Aspose.PDF for .NET 提供憑證來將 HTML 轉換為 PDF 的逐步指南。
type: docs
weight: 240
url: /zh-hant/net/document-conversion/provide-credentials-during-html-to-pdf/
---
在本教學中，我們將引導您完成將 HTML 檔案轉換為 PDF 的過程，同時在使用 Aspose.PDF for .NET 存取安全 URL 時提供憑證。透過執行以下步驟，您將能夠使用適當的憑證將 HTML 內容轉換為 PDF。

## 先決條件
在開始之前，請確保滿足以下先決條件：

- C# 程式語言的基礎知識。
- 您的系統上安裝了適用於 .NET 的 Aspose.PDF 庫。
- 開發環境，例如 Visual Studio。

## 第 1 步：取得安全的 HTML 內容
在此步驟中，我們將使用適當的憑證從 URL 取得安全的 HTML 內容。使用以下程式碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//建立 URL 請求。
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
//如果伺服器需要，請設定憑證。
request.Credentials = CredentialCache.DefaultCredentials;
//得到回應。
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

//取得包含伺服器回傳內容的流。
Stream dataStream = response. GetResponseStream();
//使用 StreamReader 開啟流以方便存取。
StreamReader reader = new StreamReader(dataStream);
//閱讀內容。
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`與您想要儲存產生的 PDF 檔案的實際目錄。

## 第 2 步：透過提供憑證將 HTML 轉換為 PDF
現在，我們將載入檢索到的 HTML 內容並將其轉換為 PDF 格式，同時提供適當的憑證。使用以下程式碼：

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

//載入 HTML 文件
Document pdfDocument = new Document(stream, options);
```

## 步驟 3：儲存產生的 PDF 文件
最後，我們將保存生成的 PDF 文件。使用以下程式碼：

```csharp
//儲存生成的 PDF 文件
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

上面的程式碼使用文件名保存生成的 PDF 文件`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### 使用 Aspose.PDF for .NET 在 HTML 轉 PDF 期間提供憑證的範例原始碼

```csharp
try
{
	
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//建立 URL 請求。
	WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	//如果伺服器需要，請設定憑證。
	request.Credentials = CredentialCache.DefaultCredentials;
	//得到回應。
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	//取得包含伺服器回傳內容的流。
	Stream dataStream = response.GetResponseStream();
	//使用 StreamReader 開啟流以方便存取。
	StreamReader reader = new StreamReader(dataStream);
	//閱讀內容。
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// My.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	//載入 HTML 文件
	Document pdfDocument = new Document(stream, options);
	//儲存結果文件
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論
在本教程中，我們介紹了將 HTML 檔案轉換為 PDF 的逐步過程，同時在使用 Aspose.PDF for .NET 存取安全 URL 時提供憑證。按照上述說明，您將能夠在提供正確的憑證的同時成功將 HTML 內容轉換為 PDF。

### 常見問題解答

#### Q：什麼是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一個強大的程式庫，讓開發人員能夠在 C# 應用程式中處理 PDF 文件。它提供了廣泛的功能，包括 HTML 到 PDF 的轉換。

#### Q：如何從 URL 取得安全的 HTML 內容？

答：若要從 URL 取得安全的 HTML 內容，您可以使用`WebRequest`C# 中的類別。確保使用設定適當的憑證`Credentials`財產。

#### Q：本教程的先決條件是什麼？

答：在繼續學習本教學之前，請確保您符合以下先決條件：

- C# 程式語言的基礎知識。
- 您的系統上安裝了適用於 .NET 的 Aspose.PDF 庫。
- 開發環境，例如 Visual Studio。

#### Q：Aspose.PDF for .NET 在將 HTML 轉換為 PDF 時如何處理外部資源？

答：Aspose.PDF for .NET 提供了`HtmlLoadOptions`類別在 HTML 到 PDF 轉換期間處理外部資源。您可以使用以下命令設定外部資源憑證`ExternalResourcesCredentials`財產。

#### Q：我可以自訂生成的 PDF 檔案的檔案名稱嗎？

答：是的，您可以透過修改儲存 PDF 文件的程式碼來自訂產生的 PDF 檔案的檔案名稱。只需更改所需的檔案名稱即可`pdfDocument.Save()`方法。