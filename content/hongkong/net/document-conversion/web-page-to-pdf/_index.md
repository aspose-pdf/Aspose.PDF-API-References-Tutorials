---
title: 網頁轉PDF
linktitle: 網頁轉PDF
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 將網頁轉換為 PDF 的逐步指南。
type: docs
weight: 320
url: /zh-hant/net/document-conversion/web-page-to-pdf/
---
在本教學中，我們將逐步指導您如何使用 Aspose.PDF for .NET 庫將網頁轉換為 PDF。我們將解釋提供的 C# 原始程式碼，並向您展示如何在您自己的專案中實現它。在本教學結束時，您將能夠輕鬆地將網頁轉換為 PDF 文件。

## 介紹
將網頁轉換為 PDF 格式是許多應用程式中的常見要求。透過將網頁內容轉換為 PDF，您可以輕鬆保留原始網頁的版面、格式和圖片。 Aspose.PDF for .NET 是一個功能強大的程式庫，可讓您有效率且精確地執行此轉換。

## 要求
在我們開始之前，請確保您具備以下先決條件：
- 您的電腦上安裝了 Visual Studio
- Aspose.PDF for .NET庫（可從Aspose官方網站下載）
- C# 程式設計基礎知識


## 第 1 步：定義文檔目錄
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
代替`"YOUR DOCUMENT DIRECTORY"`以及您要儲存生成的 PDF 檔案的路徑。

## 第 2 步：建立 Web 請求
```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
建立一個 Web 請求物件並指定要轉換的網頁的 URL。您可以將 URL 替換為任何所需的網頁。

## 第 3 步：取得網路回應
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
發送 Web 請求並從伺服器檢索回應。

## 第 4 步：閱讀網頁內容
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
使用a讀取網頁內容`StreamReader`並將其儲存在`responseFromServer`多變的。

## 第 5 步：將 HTML 轉換為 PDF
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://en.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
創建一個`MemoryStream`對象載入網頁內容。然後，建立一個實例`HtmlLoadOptions`並傳遞網頁的基本 URL。接下來，創建一個`Document`使用載入的流和 HTML 載入選項的物件。設定`IsLandscape`財產給`true`如果您希望 PDF 為橫向。最後將PDF文檔儲存到指定目錄

.

## 第 6 步：處理異常
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
捕獲轉換過程中可能發生的任何異常並顯示錯誤訊息。

### 使用 Aspose.PDF for .NET 將網頁轉為 PDF 的範例原始碼

```csharp
try
{
	
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//建立 URL 請求。
	WebRequest request = WebRequest.Create("https://En.wikipedia.org/wiki/Main_Page");
	//如果伺服器需要，請設定憑證。
	request.Credentials = CredentialCache.DefaultCredentials;
	//請求超時前的超時時間（以毫秒為單位）
	//請求超時= 100；

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
	HtmlLoadOptions options = new HtmlLoadOptions("https:// En.wikipedia.org/wiki/");


	//載入 HTML 文件
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	//將輸出儲存為 PDF 格式
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論
在本教學中，我們學習如何使用 Aspose.PDF for .NET 函式庫將網頁轉換為 PDF。我們完成了解釋所提供的 C# 原始程式碼的逐步指南。透過遵循這些說明，您可以輕鬆地將網頁到 PDF 轉換功能整合到您自己的 .NET 應用程式中。

### 常見問題解答

#### Q：什麼是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員在 C# 應用程式中處理 PDF 文件。它提供各種功能，包括將網頁轉換為 PDF。

#### Q：為什麼我要將網頁轉換為 PDF？

答：將網頁轉換為 PDF 對於保留原始網頁內容的版面、格式和圖片很有用。它允許您建立網頁快照以供離線查看或與他人共用。

#### Q：本教程的先決條件是什麼？

答：要學習本教學，您需要在電腦上安裝 Visual Studio、Aspose.PDF for .NET 函式庫，並且對 C# 程式設計有基本的了解。

#### Q：我可以將任何網頁轉換為 PDF 嗎？

答：是的，您可以透過在程式碼中提供網頁的 URL 將任何網頁轉換為 PDF。 Aspose.PDF for .NET 將擷取網頁內容並將其轉換為 PDF 格式。

#### Q：如何自訂 PDF 輸出，例如頁面方向？

答：您可以使用以下選項自訂 PDF 輸出`IsLandscape`設定頁面方向。在提供的程式碼中，`options.PageInfo.IsLandscape = true`用於建立橫向 PDF。