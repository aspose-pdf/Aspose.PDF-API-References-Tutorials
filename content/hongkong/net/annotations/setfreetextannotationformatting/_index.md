---
title: 設定自由文字註釋格式
linktitle: 設定自由文字註釋格式
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 在 PDF 文件中設定自由文字註解格式。
type: docs
weight: 140
url: /zh-hant/net/annotations/setfreetextannotationformatting/
---
## 介紹

在數位時代，操作和註釋 PDF 文件的能力對於各個領域的專業人士來說已經變得至關重要。無論您是批改作業的老師、審查合約的律師還是分享回饋的專案經理，擁有正確的工具都可以發揮重要作用。 Aspose.PDF for .NET 就是這樣一個強大的工具，它是一個強大的庫，允許開發人員輕鬆建立、編輯和操作 PDF 文件。在本教學中，我們將深入了解使用 Aspose.PDF for .NET 設定自由文字註解格式的細節。在本指南結束時，您將掌握使用自訂註解增強 PDF 文件的知識，從而使您的工作流程更加順暢和高效。

## 先決條件

在我們深入了解編碼的細節之前，讓我們確保您擁有開始使用所需的一切。這是您應該擁有的：

1. C# 基礎知識：熟悉 C# 程式設計將有助於您理解本教學中提供的範例和程式碼片段。
2.  Aspose.PDF for .NET：您需要安裝 Aspose.PDF 庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/pdf/net/).
3. Visual Studio：像 Visual Studio 這樣的開發環境將使編寫和測試程式碼變得更加容易。
4. PDF 文件：對於本教學課程，您需要使用範例 PDF 文件。您可以建立一個簡單的範例或從 Internet 下載範例。

一旦滿足了這些先決條件，您就可以進入 PDF 註釋的世界了！

## 導入包

要開始使用 Aspose.PDF for .NET，您需要將必要的套件匯入到您的專案中。您可以這樣做：

### 第 1 步：建立一個新項目

開啟 Visual Studio 並建立一個新的 C# 專案。為了簡單起見，您可以選擇控制台應用程式。

### 第2步：新增Aspose.PDF參考

1. 在解決方案資源管理器中以滑鼠右鍵按一下您的專案。
2. 選擇“管理 NuGet 套件”。
3. 搜尋“Aspose.PDF”並安裝最新版本。

### 第 3 步：導入命名空間

在 C# 檔案的頂部，匯入 Aspose.PDF 命名空間：

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

現在我們已經完成了所有設置，讓我們繼續教程的主要部分：設置自由文字註釋格式。

## 第 1 步：定義文檔目錄

首先，您需要指定文檔目錄的路徑。這是您的 PDF 文件所在的位置。您可以這樣做：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`與儲存 PDF 檔案的實際路徑。此步驟至關重要，因為它告訴您的程式在哪裡可以找到您想要使用的 PDF 文件。

## 第 2 步：開啟 PDF 文檔

接下來，您需要開啟要註釋的 PDF 文件。這是使用以下方法完成的`Document`Aspose.PDF 庫中的類別：

```csharp
//開啟文件
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

這行程式碼初始化一個新的`Document`對象並加載您指定的 PDF 文件。確保檔案名稱與目錄中的檔案名稱相符。

## 第 3 步：實例化 DefaultAppearance 對象

現在，讓我們建立一個`DefaultAppearance`目的。該物件將定義自由文字註釋的外觀，例如字體、大小和顏色：

```csharp
//實例化 DefaultAppearance 對象
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

在此範例中，我們使用 Arial 字體，將字體大小設為 28，並選擇紅色作為顏色。請隨意自訂這些值以滿足您的需求！

## 第 4 步：建立自由文字註釋

設定外觀後，就可以建立實際的自由文字註解了。您可以在此指定註釋在 PDF 上的顯示位置：

```csharp
//建立註釋
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

在這一行中，我們正在創建一個新的`FreeTextAnnotation`在 PDF 的第一頁。矩形定義註解的位置和大小。您可以調整座標（200、400、400、600）以將註釋準確地放置在您想要的位置。

## 第5步：指定註釋的內容

現在我們已經創建了註釋，讓我們在其中添加一些文字：

```csharp
//指定註釋的內容
freetext.Contents = "Free Text";
```

您可以更換`"Free Text"`以及您想要在註釋中顯示的任何訊息。這是任何查看 PDF 的人都可以看到的文字。

## 第 6 步：將註釋新增至頁面

接下來，我們需要將註解新增到頁面的註解集合中：

```csharp
//新增註解到頁面註解集合
pdfDocument.Pages[1].Annotations.Add(freetext);
```

這行程式碼確保您新建立的註解實際上已新增到 PDF 文件中。如果沒有此步驟，您的註解將不會出現在最終輸出中。

## 步驟7：儲存更新後的文檔

最後，是時候儲存您的變更了。您需要為更新的文檔指定新的檔案名稱：

```csharp
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
//儲存更新後的文檔
pdfDocument.Save(dataDir);
```

此程式碼使用新名稱儲存修改後的 PDF，確保您的原始文件保持不變。現在您可以開啟新的 PDF 檔案來查看正在運行的自由文字註釋！

## 結論

恭喜！您已成功學習如何使用 Aspose.PDF for .NET 設定自由文字註解格式。透過執行以下步驟，您可以使用自訂註釋來增強 PDF 文檔，使其更具互動性和資訊量。無論您是新增註解、註解還是反白顯示，Aspose.PDF 都能提供您簡化工作流程所需的工具。因此，請繼續嘗試不同的樣式和位置，讓您的 PDF 適合您！

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個函式庫，可讓開發人員以程式設計方式建立、編輯和操作 PDF 文件。

### 我可以免費使用 Aspose.PDF 嗎？
是的，Aspose 提供免費試用版，您可以使用它來探索該程式庫的功能。你可以下載它[這裡](https://releases.aspose.com/).

### 如何獲得 Aspose.PDF 支援？
您可以透過造訪 Aspose 論壇獲得支持[這裡](https://forum.aspose.com/c/pdf/10).

### 是否可以自訂註釋的外觀？
絕對地！您可以使用以下命令自訂註解的字體、大小、顏色和其他屬性`DefaultAppearance`班級。

### 哪裡可以購買 Aspose.PDF for .NET？
您可以購買 Aspose.PDF 的許可證[這裡](https://purchase.aspose.com/buy).