---
title: 頁首頁腳中使用浮動框的頁碼
linktitle: 頁首頁腳中使用浮動框的頁碼
second_title: Aspose.PDF for .NET API 參考
description: 在本逐步教學中，使用 Aspose.PDF for .NET 的浮動框輕鬆在 PDF 頁首和頁尾中新增頁碼。
type: docs
weight: 150
url: /zh-hant/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
## 介紹

當談到以程式設計方式管理 PDF 文件時，Aspose.PDF for .NET 是一款出色的工具。它簡化了我們在 .NET 應用程式中建立、編輯和操作 PDF 文件的方式。無論您是產生發票、報告還是任何文件類型，巧妙地添加頁碼都可以提高 PDF 的專業性和組織性。在本教程中，我們將深入研究如何使用浮動框在 PDF 的頁首和頁尾中添加頁碼。準備好開始了嗎？我們走吧！

## 先決條件

在我們開始進入 PDF 操作領域的令人興奮的旅程之前，您需要具備以下一些條件：

### .NET環境設定
確保您有 .NET 開發環境。您可以使用 Visual Studio，它是 .NET 應用程式開發人員的熱門選擇。

### Aspose.PDF庫
安裝 Aspose.PDF 庫。您可以輕鬆地從網站下載：

- [下載 .NET 版 Aspose.PDF](https://releases.aspose.com/pdf/net/)

### C#程式設計基礎知識
對 C# 的基本了解將幫助您掌握本教程中介紹的概念和編碼片段。

### 存取文件
擁有總是有益的[Aspose.PDF 文檔](https://reference.aspose.com/pdf/net/)方便參考並更深入地探索任何附加功能。

## 導入包

首先，您需要在專案中匯入必要的套件。這確保了 Aspose.PDF 組件可在您的程式碼中使用。操作方法如下：

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

現在，讓我們將使用浮動框添加頁碼的過程分解為易於管理的步驟。跟著我們一起走過。

## 第 1 步：設定您的文件環境

我們首先指定 PDF 文件的儲存目錄。這很重要，因為它決定了輸出檔案的保存位置。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`YOUR DOCUMENT DIRECTORY`以及您選擇的要儲存輸出 PDF 檔案的路徑。

## 第 2 步：實例化文檔

下一步是建立新的 PDF 文件。這涉及使用`Document`來自 Aspose.PDF 庫的類別。

```csharp
//實例化文件實例
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```
在這裡，我們建立一個新的實例`Document`類，它充當我們進行操作的畫布。

## 第 3 步：新增頁面

現在，讓我們為 PDF 文件新增一個頁面。每個 PDF 至少需要一頁，對吧？

```csharp
//將頁面新增至 PDF 文件中
Aspose.Pdf.Page page = pdf.Pages.Add();
```
此程式碼片段為我們的文件添加了一個新頁面，使其準備好接收內容，包括帶有頁碼的浮動框。

## 第四步：建立一個浮動框

接下來，是時候建立用於儲存頁碼的浮動框了。這`FloatingBox`類別允許我們在頁面上自由定位內容。

```csharp
//初始化 FloatingBox 類別的新實例
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);
```
這裡，參數`(140, 80)`指定浮動框的寬度和高度。您可以根據您的佈局偏好調整這些值。

## 步驟5：定位浮動框

定位很關鍵！您想要確定頁碼將出現在頁面上的位置。您將與`Left`和`Top`屬性來指定位置。

```csharp
//指示段落左側位置的浮點數值
box1.Left = 2;
//指示段落頂部位置的浮點數值
box1.Top = 10;
```
這些值決定了浮動框在頁面上的位置。請隨意嘗試它們，看看什麼最適合您的文件。

## 第 6 步：使用頁碼巨集新增文本

現在，我們將新增一個動態顯示頁碼的字串。這就是魔法發生的地方！

```csharp
//將巨集加入到 FloatingBox 的段落集合中
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));
```
在這種情況下，`($p/ $P)`是一個宏，將顯示目前頁碼（`$p`）和總頁數（`$P`）。因此，它將文字格式化為“頁：1/5”之類的內容。

## 步驟7：將浮動框新增至頁面

是時候將浮動框以及頁碼文字新增到我們新建立的頁面中了。

```csharp
//給頁面新增一個floatingBox
page.Paragraphs.Add(box1);
```
該行本質上將浮動框嵌入到頁面中，使其成為文件佈局的一部分。 

## 第 8 步：儲存您的文件

最後，不要忘記保存您的工作！最後一步是使用正確的檔案名稱儲存 PDF 文件。

```csharp
//儲存文件
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```
確保指定的路徑包含您所需的檔案名稱。現在，帶有頁碼的令人驚嘆的 PDF 已創建！ 

## 結論

好了，夥計們！使用 Aspose.PDF for .NET 將頁碼加入 PDF 的頁首和頁尾就是這麼簡單。只需幾行程式碼，您就開始了掌握應用程式中文件處理的旅程。不要猶豫，嘗試不同的佈局和格式——畢竟，創造力是無止境的！準備好產生專業文件了嗎？拿起你的編碼帽子並開始嘗試。

## 常見問題解答

### 我可以自訂頁碼文字的外觀嗎？  
是的，您可以透過調整文字屬性來自訂文字屬性，例如字體大小、顏色和樣式`TextFragment`特性。

### Aspose.PDF 可以免費使用嗎？  
雖然 Aspose.PDF 提供免費試用版，但它是用於生產用途的付費產品。你可以[在這裡買](https://purchase.aspose.com/buy).

### 在哪裡可以找到更詳細的文件？  
您可以在以下位置找到全面的文檔[Aspose.PDF 文件站點](https://reference.aspose.com/pdf/net/).

### 如何將頁首和頁尾套用到多個頁面？  
您可以循環瀏覽文件中的所有頁面，並將浮動框類似地套用到每一頁。

### 如果我需要其他功能的支援怎麼辦？  
如有任何其他問題或支持，您可以訪問[Aspose論壇](https://forum.aspose.com/c/pdf/10).