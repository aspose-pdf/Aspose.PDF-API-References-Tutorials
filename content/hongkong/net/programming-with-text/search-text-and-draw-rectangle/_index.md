---
title: 搜尋文字並繪製一個矩形
linktitle: 搜尋文字並繪製一個矩形
second_title: Aspose.PDF for .NET API 參考
description: 學習使用 Aspose.PDF for .NET 在 PDF 中搜尋文字並用矩形突出顯示它！簡單的逐步教學可增強 PDF 操作技能。
type: docs
weight: 460
url: /zh-hant/net/programming-with-text/search-text-and-draw-rectangle/
---
## 介紹

您想提升 PDF 操作技能嗎？您想了解如何在 PDF 文件中搜尋特定文字並用矩形突出顯示它嗎？您已經找到了完美的指南！今天，我將引導您了解如何使用 Aspose.PDF for .NET 在 PDF 文件中搜尋文字並在其周圍繪製矩形。本文將提供一個逐步教程，其設計時考慮到清晰性和實用性，確保您可以遵循這些技術並將其應用到您的專案中。 

## 先決條件

在深入學習本教學之前，讓我們先準備好確保工作流程順利進行所需的準備：

1. 對 .NET 的基本了解：您應該熟悉 C# 程式設計和 .NET 框架，才能有效遵循本教學。
   
2. 安裝了 Visual Studio：您將需要一個整合開發環境 (IDE) 來編寫和測試程式碼。 Visual Studio Community 是一個不錯的選擇，而且是免費的。
   
3. Aspose.PDF for .NET：您需要在專案中安裝 Aspose.PDF 庫。你可以下載它[這裡](https://releases.aspose.com/pdf/net/)或考慮[臨時執照](https://purchase.aspose.com/temporary-license/)用於擴充功能。
   
4. 範例 PDF 文件：對於本教學課程，您將需要一個名為的範例 PDF 文件`SearchAndGetTextFromAll.pdf`儲存在您的專案目錄中。 

## 導入包

首先，您需要將必要的套件匯入到 .NET 專案中。請依照下列步驟操作：

### 打開視覺工作室

啟動 Visual Studio 並建立一個新的控制台應用程序，或使用要實現 PDF 功能的現有控制台應用程式。

### 將 Aspose.PDF 新增到您的專案中

1. 在解決方案資源管理器中以滑鼠右鍵按一下您的專案。
2. 選擇“管理 NuGet 套件”。
3. 搜尋`Aspose.PDF`並安裝最新版本。

透過這樣做，您就為即將執行的所有令人驚奇的 PDF 操作奠定了基礎。

## 導入命名空間

在程式檔案的頂部，您需要從 Aspose 庫匯入相關的命名空間：

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

這使得您可以更輕鬆地存取 Aspose.PDF 庫中的類別和方法來執行任務。


現在您已完成所有設置，讓我們將在 PDF 中搜尋文字並在其周圍繪製矩形的過程分解為易於管理的步驟。

## 第 1 步：設定文檔的路徑

首先，設定 PDF 文件的路徑。確保更換`YOUR DOCUMENT DIRECTORY`與你的實際路徑`SearchAndGetTextFromAll.pdf`被儲存。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：開啟 PDF 文檔

接下來，建立一個實例`Document`載入 PDF 的類別：

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

這行程式碼會開啟您指定的 PDF 文件，允許您進一步操作它。

## 第 3 步：建立文字吸收器

現在，您需要一種方法來搜尋該文件中的文字。為此，我們使用`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

正規表示式`@"[\S]+"`旨在匹配 PDF 中的任何非空白字串。 

## 步驟 4：設定文字搜尋選項

接下來，您應該設定文字搜尋選項：

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

在這裡，`true`參數意味著搜尋將區分大小寫。您可以將其設定為`false`如果您想要不區分大小寫的搜尋。

## 第 5 步：接受文件中的文字吸收器

與你的`TextFragmentAbsorber`搜尋選項準備就緒，是時候從文件中吸收文字了：

```csharp
document.Pages.Accept(textAbsorber);
```

此方法檢查 PDF 中的每個頁面，以尋找與指定模式相符的文字片段。

## 第 6 步：建立 PdfContentEditor

要在文件上繪製形狀，您將需要`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

此編輯器可讓您輕鬆操作和編輯 PDF 內容。

## 第 7 步：循環找到的文字片段

現在，您需要循環遍歷找到的文字片段以在它們周圍繪製矩形：

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

此循環迭代每個文字片段及其片段，調用`DrawBox`矩形繪製方法。

## 第8步：定義DrawBox方法

您需要定義`DrawBox`方法，它將處理矩形繪製邏輯。這是一個簡單的實作：

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    //根據文字段計算矩形尺寸
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    //使用計算值繪製矩形
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

此方法根據段的邊界矩形確定矩形的位置和大小，並使用編輯器繪製它。

## 步驟9：儲存修改後的文檔

在找到的文字周圍繪製矩形後，您可以儲存修改後的文件：

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

確保使用不同的名稱儲存新文件，以避免覆蓋原始文件。

## 第10步：確認訊息

最後，在控制台列印一條確認訊息，讓您知道操作成功：

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

現在你就擁有了！您已成功建立一個腳本來搜尋 PDF 中的文字並用矩形突出顯示它。

## 結論

恭喜！您剛剛解鎖了一項強大的技能，可以使用 Aspose.PDF for .NET 大幅增強您的 PDF 操作能力。只需幾個簡單的步驟，您就可以搜尋文件中的任何文字並以視覺方式突出顯示它，從而使您的 PDF 文件更具互動性和易於管理。不要猶豫，嘗試不同的正規表示式模式和顏色選項，真正讓這個工具成為您自己的工具！

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個函式庫，提供了以程式設計方式建立、操作和轉換 PDF 文件的綜合方法。

### 我可以免費使用 Aspose.PDF 嗎？
是的，Aspose 提供免費試用版，您可以用它來測試庫的功能。一探究竟[這裡](https://releases.aspose.com/).

### Aspose.PDF for .NET 需要使用什麼程式語言？
Aspose.PDF for .NET 設計用於與 C# 和其他 .NET 語言一起使用。

### 如何獲得有關 Aspose.PDF 的協助？
您可以造訪 Aspose 支援論壇，以取得您可能遇到的任何問題或疑問的協助。尋求支持[這裡](https://forum.aspose.com/c/pdf/10).

### 在哪裡下載 Aspose.PDF for .NET？
您可以從 Aspose 網站下載該庫，[這裡](https://releases.aspose.com/pdf/net/).