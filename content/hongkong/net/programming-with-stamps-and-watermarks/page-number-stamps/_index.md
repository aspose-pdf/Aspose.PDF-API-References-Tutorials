---
title: PDF 檔案中的頁碼標記
linktitle: PDF 檔案中的頁碼標記
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中新增頁碼戳記。
type: docs
weight: 160
url: /zh-hant/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
在本教學中，我們將逐步指導您如何使用 Aspose.PDF for .NET 在 PDF 檔案中新增頁碼戳記。我們將使用提供的 C# 原始程式碼開啟現有 PDF 文件、建立頁碼戳記、設定其屬性並將其新增至 PDF 文件中的特定頁面。

## 第一步：建構環境

在開始之前，請確保您具備以下條件：

- 已安裝的 .NET 開發環境。
- 下載 .NET 的 Aspose.PDF 庫並在您的專案中引用。

## 步驟 2： 載入現有 PDF 文檔

第一步是將現有的 PDF 文件載入到您的專案中。方法如下：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//開啟現有的 PDF 文檔
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

請務必將「您的文件目錄」替換為 PDF 文件所在目錄的實際路徑。

## 步驟 3：建立並設定頁碼標記

現在 PDF 文件已加載，我們可以建立頁碼緩衝區並根據需要進行配置。方法如下：

```csharp
//建立頁碼緩衝區
PageNumberStamp pageNumberStamp = new PageNumberStamp();

//定義緩衝區是否在背景
pageNumberStamp.Background = false;

//頁編號緩衝區的格式
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

//頁碼緩衝區的下邊距
pageNumberStamp.BottomMargin = 10;

//頁碼緩衝區的水平對齊
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

//頁碼起始編號
pageNumberStamp.StartingNumber = 1;

//設定頁碼緩衝區文字屬性
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

上面的程式碼建立了一個頁碼標記，其屬性包括頁碼格式、下邊距、水平對齊方式、起始編號和文字屬性。

## 步驟 4：將頁碼標記新增至特定頁面

配置頁碼標記後，我們可以將其新增至 PDF 文件的特定頁面。方法如下：

```csharp
//將頁碼緩衝區新增至特定頁面
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

上面的程式碼將頁碼標記新增到 PDF 文件的第一頁。您可以根據需要變更頁碼。

## 步驟5：儲存修改後的PDF文檔

一旦頁碼標記加入PDF文件中，我們就可以儲存修改後的PDF文件。方法如下：

```csharp
//儲存修改後的PDF文檔
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

請務必將「您的文件目錄」替換為您要儲存編輯後的 PDF 文件的目錄的實際路徑。

### 使用 Aspose.PDF for .NET 的頁碼圖章範例原始碼 
```csharp

//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//開啟文件
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

//建立頁碼印記
PageNumberStamp pageNumberStamp = new PageNumberStamp();

//印章是否為背景
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

//設定文字屬性
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

//新增圖章到特定頁面
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

//儲存輸出文檔
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## 結論

恭喜！您已了解如何使用 Aspose.PDF for .NET 將頁碼標記新增至 PDF 文件。現在，您可以透過添加清晰且資訊豐富的頁碼來個性化您的 PDF 文件。

### PDF 檔案中頁碼標記的常見問題

#### Q：什麼是頁碼標記，如何使用它為 PDF 檔案添加頁碼？

答：頁碼標記是 Aspose.PDF 中的一項功能，可讓您將動態頁碼新增至 PDF 文件的特定頁面。在本教程中，它是透過建立 PageNumberStamp 物件、配置其屬性並將其新增至指定頁面來實現的。

#### Q：提供的 C# 原始程式碼如何完成在 PDF 檔案中新增頁碼戳記？

答：程式碼示範如何載入現有的 PDF 文檔，建立 PageNumberStamp，設定各種屬性（如格式、字型、對齊方式等），然後將圖章新增至特定頁面。郵票會自動計算總頁數並插入正確的頁碼。

#### Q：我可以自訂頁碼的外觀，例如字體樣式、顏色和大小嗎？

答：當然，您可以透過調整字體、字體大小、字體樣式（粗體、斜體等）和文字顏色等屬性來自訂頁碼標記的外觀。

#### Q：是否可以在 PDF 文件的多個頁面上新增頁碼標記？

答：是的，您可以透過建立多個 PageNumberStamp 物件並將每個物件新增至所需頁面來將頁碼標記新增至多個頁面。

#### Q：我可以選擇頁碼標記是作為頁面內容的一部分還是作為背景元素顯示？

答：是的，您可以透過設定頁碼標記來控制頁碼標記是作為頁面內容的一部分還是作為背景元素顯示。`Background` PageNumberStamp 的屬性。

#### Q：如何指定頁碼的格式，包括總頁數？

答：該程式碼使用`Format`PageNumberStamp 屬性指定頁碼的格式。巨集“# of”用於表示總頁數。

#### Q：如果我在多個頁面上新增相同的頁碼戳記，會發生什麼事？

答：將相同的 PageNumberStamp 實例新增至多個頁面將顯示每個頁面的正確頁碼。印章會自動調整頁碼和總頁數。

#### Q：我可以將頁碼標記新增至 PDF 文件的頁首或頁尾部分嗎？

答：雖然 PageNumberStamp 通常直接加入到頁面內容中，但您可以使用 FloatingBox 或其他技術將它們放置在頁首或頁尾部分中。

#### Q：如何指定頁碼標記在頁面上的位置？

答： 的`BottomMargin`和`HorizontalAlignment` PageNumberStamp 的屬性可讓您控制圖章在頁面中的位置。

#### Q：如果我想從不同的數字而不是 1 開始頁碼，該怎麼辦？

答：您可以設定`StartingNumber`PageNumberStamp 屬性來指定起始頁碼。