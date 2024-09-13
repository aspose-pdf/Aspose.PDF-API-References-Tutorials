---
title: PDF 檔案中的頁碼標記
linktitle: PDF 檔案中的頁碼標記
second_title: Aspose.PDF for .NET API 參考
description: 透過我們易於遵循的指南（附有程式碼範例），了解如何使用 Aspose.PDF for .NET 將頁碼標記新增至 PDF 檔案。
type: docs
weight: 160
url: /zh-hant/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
## 介紹

您是否曾經發現自己在處理 PDF 文檔，希望它有頁碼以便於導航？無論您是共享筆記的學生、簡報報告的專業人士，還是管理多頁文件的任何人，添加頁碼都可以真正提高 PDF 文件的清晰度。幸運的是，透過強大的 Aspose.PDF for .NET 程式庫，您可以輕鬆地將頁碼標記新增至 PDF 文件中。在本指南中，我們將逐步引導您完成整個過程，確保您掌握所需的所有知識。讓我們深入了解吧！

## 先決條件

在我們開始為您的 PDF 文件添加頁碼圖章之前，請確保您符合以下先決條件：

1. Visual Studio：確保您的系統上安裝了 Visual Studio。您將在這裡編寫並執行程式碼。
2. .NET Framework：熟悉 C# 程式設計和 .NET 框架至關重要，因為 Aspose.PDF 是為 .NET 應用程式設計的。
3.  Aspose.PDF 庫：您可以從以下位置下載 Aspose.PDF 庫：[Aspose PDF 版本](https://releases.aspose.com/pdf/net/). 
4. 對 PDF 的基本了解：雖然您不需要成為專家，但對 PDF 文件工作原理的基本了解將幫助您更好地理解本教學。

一旦設定了這些先決條件，您就可以開始蓋印這些頁碼了！

## 導入包

在深入編碼之前，您需要確保將必要的 Aspose.PDF 套件匯入到您的專案中。這對於無縫利用庫函數至關重要。操作方法如下：

### 建立一個新項目

1. 打開視覺工作室。
2. 點選`File`>`New`>`Project`.
3. 選擇適合 C# 的範本（例如控制台應用程式），為其命名，然後按一下`Create`.

### 新增 Aspose.PDF 參考

1. 右鍵點選解決方案資源管理器中的項目名稱。
2. 點選`Manage NuGet Packages`.
3. 搜尋`Aspose.PDF`並安裝最新版本。

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

庫準備好後，讓我們開始編碼吧！

現在我們的環境已經設定完畢，是時候在 PDF 檔案中新增頁碼戳記了。我們將把這個過程分解為清晰的步驟，以便更好地理解。

## 步驟1：指定文檔目錄

首先，您需要指定 PDF 檔案所在的目錄。這是您的專案的起點。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; //更新此路徑
```

說明： 替換`"YOUR DOCUMENT DIRECTORY"`包含指向包含 PDF 檔案的目錄的路徑。這很重要，因為它告訴您的程式碼在哪裡可以找到您想要操作的檔案。

## 第 2 步：開啟文檔

接下來，我們將開啟要新增頁碼印章的現有 PDF 文件。

```csharp
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

說明：在這裡，我們使用`Document`Aspose.PDF 提供的類別用於開啟我們特定的 PDF 檔案。確保檔案名稱與目錄中的實際檔案相符。

## 第 3 步：建立頁碼標記

現在來了有趣的部分！讓我們建立一個頁碼標記以新增到 PDF 中。

```csharp
PageNumberStamp pageNumberStamp = new PageNumberStamp();
```

解釋：`PageNumberStamp`類別將允許我們建立一個圖章，該圖章將顯示相對於文件中總頁數的當前頁碼。

## 步驟 4：配置標記

現在，您需要配置圖章設定。您可以在此設計圖章的外觀和行為。

```csharp
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;
```

解釋：
- `Background = false`：這意味著圖章將出現在前景中。
- `Format`：在這裡，您將格式設定為顯示“第 X 頁，共 Y 頁”，您可以在其中動態取得文件中的總頁數。
- `BottomMargin`：調整距頁面底部的距離。
- `HorizontalAlignment`：將印記水平居中。
- `StartingNumber`：設定起始頁碼，通常從 1 開始。

## 第 5 步：設定文字屬性

接下來，您可以自訂圖章中文字的外觀。

```csharp
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

說明：這些屬性配置圖章中文字的字體類型、字體大小、樣式（粗體和斜體）和顏色，使其具有視覺吸引力。

## 步驟 6：將圖章新增至特定頁面

配置好圖章後，就可以將其新增至文件中的特定頁面了。

```csharp
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

說明： 此行將圖章新增至 PDF 的第一頁。您可以調整`Pages[1]`根據需要為其他頁面建立索引。

## 步驟7：儲存輸出文檔

最後，儲存修改後的 PDF 文檔，以便您的變更永久生效。

```csharp
dataDir = dataDir + "PageNumberStamp_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);
```

說明：您正在定義輸出檔案路徑並儲存文件。控制台將讓您知道圖章已成功新增以及檔案的儲存位置。

## 結論

使用 Aspose.PDF for .NET 將頁碼標記新增至 PDF 檔案不僅簡單，而且高度可自訂。我們逐步完成了頁碼印記的創建，確保您在過程中獲得清晰的指導。您現在已經掌握了增強 PDF 文件的知識，使它們更加用戶友好和專業。 

## 常見問題解答

### 我可以自訂頁碼的外觀嗎？  
是的！您可以變更頁碼的字體、大小、顏色和格式，如指南中所示。

### Aspose.PDF 可以免費使用嗎？  
 Aspose.PDF 提供免費試用版，但您需要授權才能廣泛使用。查看[購買頁面](https://purchase.aspose.com/buy)了解更多。

### 如果我在實施過程中遇到問題怎麼辦？  
您可以訪問[Aspose 支援論壇](https://forum.aspose.com/c/pdf/10)尋求幫助。

### 如何自動產生多頁頁碼？  
該指南的程式碼會自動計算總頁數，從而輕鬆自訂多個頁面。

### 我可以在其他程式語言中使用 Aspose.PDF 嗎？  
雖然本指南重點介紹 .NET，但 Aspose 也提供適用於 Java、Python 等的程式庫。