---
title: 在 HTML 轉 PDF 過程中提供憑證
linktitle: 在 HTML 轉 PDF 過程中提供憑證
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 將 HTML 轉換為 PDF。非常適合希望簡化文件產生的開發人員。
type: docs
weight: 240
url: /zh-hant/net/document-conversion/provide-credentials-during-html-to-pdf/
---
## 介紹

在軟體開發領域，將 HTML 轉換為 PDF 是一個常見的要求。無論您是產生報告、發票還是任何其他文檔，擁有一個可靠的庫來處理此任務都可以為您節省大量時間和精力。 Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員輕鬆建立、操作和轉換 PDF 文件。在本教學中，我們將引導您完成使用 Aspose.PDF 將 HTML 轉換為 PDF 的過程，同時提供安全存取憑證。所以，拿起你的編碼帽子，讓我們開始吧！

## 先決條件

在我們開始之前，您需要準備好一些東西：

1. Visual Studio：確保您的電腦上安裝了 Visual Studio。這將是我們的開發環境。
2.  Aspose.PDF for .NET：您可以從下列位置下載程式庫：[網站](https://releases.aspose.com/pdf/net/) 。如果您想先嘗試一下，您還可以獲得[免費試用](https://releases.aspose.com/).
3. C#基礎知識：熟悉C#程式設計將有助於您更好地理解範例。
4. 網路存取：由於我們將從 URL 取得 HTML 內容，因此請確保您擁有有效的網路連線。

## 導入包

要開始使用 Aspose.PDF，您需要將必要的套件匯入到您的專案中。您可以這樣做：

1. 開啟您的 Visual Studio 專案。
2. 在解決方案資源管理器中以滑鼠右鍵按一下您的項目，然後選擇「管理 NuGet 套件」。
3. 搜尋“Aspose.PDF”並安裝最新版本。

```csharp
using System.IO;
using Aspose.Pdf;
using System;
using System.Net;
```
現在我們已經完成了所有設置，讓我們將使用憑證將 HTML 轉換為 PDF 的過程分解為可管理的步驟。

## 第 1 步：設定您的文件目錄

在將 HTML 轉換為 PDF 之前，我們需要指定輸出 PDF 的儲存位置。這是透過定義文檔目錄的路徑來完成的。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`與您要儲存 PDF 檔案的實際路徑。這可以是桌面上的資料夾或系統上的任何其他位置。

## 第 2 步：建立 Web 請求

接下來，我們需要建立一個請求以從特定 URL 取得 HTML 內容。這是我們將使用的地方`WebRequest`班級。

```csharp
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
```

在這裡，我們建立一個對包含我們要轉換的 HTML 的 URL 的請求。確保將 URL 替換為您想要使用的 URL。

## 第 3 步：設定憑證（如果需要）

如果伺服器需要憑證才能存取內容，我們需要對其進行設定。這是使用以下方法完成的`CredentialCache.DefaultCredentials`.

```csharp
request.Credentials = CredentialCache.DefaultCredentials;
```

此行確保請求使用目前使用者的預設憑證。如果您需要提供特定憑證，您可以建立一個新的`NetworkCredential`目的。

## 第 4 步：取得回應

現在我們已經設定了請求，是時候從伺服器獲取回應了。

```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```

該行發送請求並等待伺服器回應。如果一切順利，我們將收到我們需要的 HTML 內容。

## 第 5 步：讀取回應流

收到回應後，我們需要讀取伺服器傳回的內容。這是使用一個`StreamReader`.

```csharp
Stream dataStream = response.GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader.Close();
dataStream.Close();
response.Close();
```

在這裡，我們將回應流的全部內容讀取到一個名為的字串變數中`responseFromServer`。不要忘記關閉閱讀器和串流以釋放資源。

## 第 6 步：將 HTML 轉換為 PDF

現在到了令人興奮的部分！我們將使用 Aspose.PDF 將 HTML 內容轉換為 PDF 文件。

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("http://My.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

Document pdfDocument = new Document(stream, options);
```

在此步驟中，我們將建立一個`MemoryStream`從 HTML 內容和設定`HtmlLoadOptions`。這允許我們為 HTML 可能引用的任何外部資源（如圖像或樣式表）指定基本 URL。

## 第7步：儲存PDF文檔

最後，我們需要將產生的PDF文件儲存到指定的目錄中。

```csharp
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

此行保存 PDF 文件，名稱為`ProvideCredentialsDuringHTMLToPDF_out.pdf`在我們之前指定的目錄中。

## 結論

現在你就擁有了！您已使用 Aspose.PDF for .NET 成功將 HTML 轉換為 PDF，同時提供了安全存取憑證。這個強大的庫可以輕鬆處理 PDF 文檔，只需幾行程式碼，您就可以從 HTML 內容生成具有專業外觀的 PDF。 

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個函式庫，可讓開發人員在 .NET 應用程式中建立、操作和轉換 PDF 文件。

### 如何安裝 Aspose.PDF？
您可以透過 Visual Studio 中的 NuGet 套件管理器安裝 Aspose.PDF 或從[網站](https://releases.aspose.com/pdf/net/).

### 我可以免費使用 Aspose.PDF 嗎？
是的，Aspose 提供免費試用版，您可以在購買之前使用它來評估該庫。

### 我可以使用 Aspose.PDF 建立哪些類型的文件？
您可以使用 Aspose.PDF 建立各種文檔，包括報告、發票和表單。

### 在哪裡可以找到對 Aspose.PDF 的支援？
您可以在以下位置找到支援並提出問題[Aspose 支援論壇](https://forum.aspose.com/c/pdf/10).