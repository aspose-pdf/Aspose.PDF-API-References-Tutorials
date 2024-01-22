---
title: 取得 PDF 文件中的文件信息
linktitle: 取得 PDF 文件中的文件信息
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 的 PDF 檔案中的 GetFileInfo 功能來檢索 PDF 文件的元資料資訊。
type: docs
weight: 180
url: /zh-hant/net/programming-with-document/getfileinfo/
---
 Aspose.PDF for .NET 是一個流行的 PDF 操作庫，使開發人員能夠在其 .NET 應用程式中建立、編輯和轉換 PDF 文件。該庫提供的功能之一是能夠檢索有關 PDF 文件元資料的資訊。本教學將引導您完成使用`GetFileInfo`Aspose.PDF for .NET 的功能可擷取 PDF 文件元資料的資訊。

## 第 1 步：安裝 Aspose.PDF for .NET

要在 .NET 應用程式中使用 Aspose.PDF for .NET，您必須先安裝程式庫。您可以從以下位置下載該庫的最新版本[Aspose.PDF for .NET 下載頁面](https://releases.aspose.com/pdf/net).

下載該庫後，將 ZIP 檔案的內容解壓縮到電腦上的資料夾中。然後，您需要在 .NET 專案中新增對 Aspose.PDF for .NET DLL 的參考。

## 第 2 步：載入 PDF 文檔

安裝 Aspose.PDF for .NET 並在 .NET 專案中新增對 DLL 的參考後，您就可以開始使用`GetFileInfo`檢索 PDF 文件元資料的資訊的功能。

使用此功能的第一步是載入您想要檢索其資訊的 PDF 文件。為此，您可以使用以下程式碼：

```csharp
// PDF文件的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟 PDF 文檔
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

在上面的程式碼中，替換`"YOUR DOCUMENT DIRECTORY"`以及 PDF 文件所在目錄的路徑。此程式碼會將 PDF 文件載入到`Document`對象，然後您可以使用該對象檢索有關文檔元資料的資訊。

## 第 3 步：檢索文件的元數據

要檢索有關 PDF 文件元資料的信息，您可以使用以下程式碼：

```csharp
//取得文件資訊
DocumentInfo docInfo = pdfDocument.Info;

//顯示文件資訊
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

在上面的程式碼中，每一行會檢索 PDF 文件的不同元資料屬性並將其輸出到控制台。您可以自訂此程式碼以僅檢索您感興趣的屬性。

### 使用 Aspose.PDF for .NET 取得 PDF 檔案資訊的範例原始程式碼

以下是使用以下命令檢索 PDF 文件元資料的完整原始碼`GetFileInfo` Aspose.PDF for .NET 的功能：

```csharp
// PDF文件的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟 PDF 文檔
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

//取得文件資訊
DocumentInfo docInfo = pdfDocument.Info;

//顯示文件資訊
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## 結論

在本教學中，我們討論如何使用 Aspose.PDF for .NET 檢索 PDF 文件元資料的資訊。透過載入 PDF 文件並存取其元資料屬性，您可以收集有關文件特徵和屬性的資訊。 Aspose.PDF for .NET 提供了一個簡單易用的 API 來處理 PDF 文檔，包括檢索元資料信息，使其成為 .NET 應用程式中 PDF 操作的寶貴工具。

### 常見問題解答

#### Q：PDF 文件中的元資料是什麼？

答：PDF文件中的元資料是指描述文件屬性和特徵的資訊。此資訊通常包括文件的標題、作者、主題、關鍵字、建立日期、修改日期等。

#### Q：如何在我的 .NET 專案中安裝 Aspose.PDF for .NET？

答：要安裝 Aspose.PDF for .NET，您需要從以下位置下載該程式庫：[Aspose.PDF for .NET 下載頁面](https://releases.aspose.com/pdf/net)。下載後，解壓縮 ZIP 檔案的內容並在 .NET 專案中新增對 Aspose.PDF for .NET DLL 的參考。

#### Q：我可以自訂程式碼以僅檢索特定元資料屬性嗎？

答：是的，您可以透過註解掉不需要的行來自訂程式碼以擷取特定的元資料屬性。程式碼中的每一行都對應一個特定的元資料屬性，因此您可以根據需要包含或排除屬性。

#### Q：我可以使用 Aspose.PDF for .NET 檢索哪些類型的元資料屬性？

答：使用Aspose.PDF for .NET，您可以擷取PDF文件的各種元資料屬性，包括作者、標題、主題、關鍵字、建立日期和修改日期。