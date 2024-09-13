---
title: 在 PDF 文件中建立本地超鏈接
linktitle: 在 PDF 文件中建立本地超鏈接
second_title: Aspose.PDF for .NET API 參考
description: 透過我們的逐步指南，了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中輕鬆建立本機超連結。
type: docs
weight: 40
url: /zh-hant/net/programming-with-links-and-actions/create-local-hyperlink/
---
## 介紹

在本指南中，我們將引導您完成使用 Aspose.PDF for .NET 在 PDF 檔案中建立本機超連結的過程。我們將清楚地分解每個步驟，確保即使您是 PDF 操作領域的新手，您也能夠輕鬆遵循。

## 先決條件

在深入研究程式碼之前，讓我們確保您擁有所需的一切：

1.  Visual Studio：您需要它來開發 .NET 應用程式。從以下位置下載[網站](https://visualstudio.microsoft.com/).
2. Aspose.PDF for .NET：您可以透過以下方式下載該程式庫：[下載連結在這裡](https://releases.aspose.com/pdf/net/)。它具有豐富的 PDF 操作功能。
3. C# 基礎：稍微熟悉一下 C# 程式設計會有幫助，但不用擔心；我們將逐行查看程式碼。
4.  .NET Framework：請確定您的電腦上安裝了 .NET Framework。您可以在Aspose.PDF上查看要求[文件](https://reference.aspose.com/pdf/net/).

設定完這些先決條件後，您就可以學習如何在 PDF 文件中建立本機超連結了！

## 導入包

現在您已做好一切準備，是時候在 C# 專案中匯入必要的套件了。 Aspose.PDF庫包含我們需要的所有類別。操作方法如下：

### 打開您的項目

開啟現有的 .NET 專案或在 Visual Studio 中建立一個新專案。如果您是全新開始，請從啟動畫面中選擇「建立新專案」。

### 新增對 Aspose.PDF 的引用

在解決方案資源管理器中右鍵點選專案資料夾中的「依賴項」。選擇“管理 NuGet 套件”，然後搜尋`Aspose.PDF`。安裝可用的最新版本。這將帶來創建和操作 PDF 所需的所有工具。

### 導入命名空間

在 .cs 檔案的頂部，新增 Aspose.PDF 庫的 using 指令，如下所示：

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

這樣，您就可以存取該庫的功能。

讓我們將建立本地超連結的過程分解為簡單的步驟。每個步驟都會得到全面的解釋，幫助您理解背後的邏輯。

## 第 1 步：設定文檔實例

在此步驟中，您將建立 Document 類別的新實例，它代表您將使用的 PDF 檔案。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; //設定您的文檔目錄
Document doc = new Document(); //建立文件實例
```
這`dataDir`變數是新建立的 PDF 所在的位置。你需要更換`"YOUR DOCUMENT DIRECTORY"`與系統上的實際路徑。這`Document`類別創建一個新的 PDF 文檔，我們可以在其中添加頁面和連結。

## 步驟 2：新增頁面

接下來，您將向 PDF 文件新增頁面。 

```csharp
Page page = doc.Pages.Add(); //將頁面新增至頁面集合
```
這`Pages.Add()`方法向文件新增頁面。這是您所有內容的存放位置。

## 第 3 步：建立文字片段

現在，讓我們建立一段文字作為可點擊的連結。

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
```
這`TextFragment`代表 PDF 中的一段文字。在這裡，我們創建一個鏈接，告訴用戶它將帶他們到第 7 頁。

## 第四步：建立本地超連結

這就是奇蹟發生的地方！您需要建立一個本地超連結來告訴文字片段指向哪裡。

```csharp
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink(); //建立本地超連結
link.TargetPageNumber = 7; //設定連結實例的目標頁面
text.Hyperlink = link; //設定 TextFragment 超鏈接
```
這`LocalHyperlink`類別允許我們指向同一文檔中的其他頁面。透過設定`TargetPageNumber`到7，您告訴超連結在點擊時跳到該特定頁面。

## 第 5 步：將文字片段新增至頁面

設定超連結後，是時候將文字片段新增至我們建立的頁面了。

```csharp
page.Paragraphs.Add(text); //將文字加入頁面的段落集合中
```
此行將可點選文字新增至頁面的段落集合中。

## 第 6 步：建立另一個文字片段（可選）

讓我們新增另一個超連結以導覽回第 1 頁。

```csharp
text = new TextFragment("link page number test to page 1"); //建立新的 TextFragment
text.IsInNewPage = true; //將其新增至新頁面
```
創建一個新的`TextFragment`對於第二個鏈接，我們設置`IsInNewPage`為 true，表示該文字將轉到新頁面。

## 步驟 7：設定第二個本地超鏈接

就像以前一樣，您將為頁面 1 建立另一個本地超連結。

```csharp
link = new LocalHyperlink(); //建立另一個本地超連結實例
link.TargetPageNumber = 1; //設定第二個超連結的目標頁面
text.Hyperlink = link; //設定第二個 TextFragment 的鏈接
```
此超連結針對第 1 頁，允許使用者在到達第二頁時跳回。

## 步驟 8：將第二個文字片段新增至新頁面

現在，讓我們將此文字新增到其頁面中。

```csharp
page.Paragraphs.Add(text); //將文字加入到頁面物件的段落集合中
```
與步驟 5 類似，此行將新的超連結文字新增至新建立的頁面。

## 第9步：儲存文檔

最後，是時候拯救你的辛勞了！ 

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf"; //指定輸出檔名
doc.Save(dataDir); //儲存更新的文檔
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);
```
這會將您的目錄路徑與檔案名稱結合。這`Save()`方法會保存您的文檔，並且一條確認訊息會讓您知道一切順利！

## 結論

使用 Aspose.PDF for .NET 在 PDF 文件中建立本地超連結不僅僅是一個很酷的技巧；這是一項增強導航和使用者體驗的實用功能。您現在已經具備了知識，可以將您的讀者直接指向他們需要的資訊。回想我們最初的比喻——不再有迷失的靈魂在無盡的書頁中徘徊。

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個函式庫，可讓開發人員使用 .NET 框架以程式設計方式建立、操作和轉換 PDF 文件。

### 我可以建立指向外部網頁的超連結嗎？
是的，除了 PDF 中的本機超連結之外，Aspose.PDF 還支援建立指向外部 URL 的超連結。

### Aspose.PDF 有免費試用版嗎？
絕對地！您可以從以下位置存取免費試用版：[地點](https://releases.aspose.com/).

### Aspose 支援哪些程式語言？
Aspose 提供各種程式語言的函式庫，包括 Java、C++、Python 等。

### 如何獲得 Aspose 產品的支援？
您可以透過以下方式尋求支持[Aspose論壇](https://forum.aspose.com/c/pdf/10).