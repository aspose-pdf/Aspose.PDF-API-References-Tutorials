---
title: 新增 PDF 註釋
linktitle: 新增註釋
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，使用 Aspose.PDF for .NET 輕鬆為 PDF 新增自訂註解。使用特定的細節和圖示自訂您的註釋。
type: docs
weight: 10
url: /zh-hant/net/annotations/addannotation/
---
## 介紹

註釋是豐富 PDF 文件的好方法，使它們具有互動性和資訊性。無論您是為協作者留下註釋還是為讀者添加額外信息，註釋都是必不可少的。在本教學中，我們將深入探討使用 Aspose.PDF for .NET 新增 PDF 註解的過程。我們將分解每個步驟，以便在本指南結束時，您將成為在 PDF 文件中嵌入註釋的專家。讓我們開始吧！

## 先決條件

在我們深入研究程式碼之前，讓我們確保您擁有所需的一切：

-  Aspose.PDF for .NET：請確定您已安裝 Aspose.PDF 庫。您可以從[Aspose.PDF for .NET 下載頁面](https://releases.aspose.com/pdf/net/).
- 開發環境：Visual Studio 或您選擇的任何其他 C# IDE。
- C# 基礎知識：本指南假設您熟悉 C# 程式設計。
- PDF 文件：您將向其中新增註釋的範例 PDF 文件。

如果您還沒有 Aspose.PDF 庫，您可以從上面的連結取得它並啟動一個[免費試用](https://releases.aspose.com/)或購買一個[執照](https://purchase.aspose.com/buy). 

## 導入包

在開始編碼之前，請確保導入了必要的命名空間：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

這些命名空間提供對 PDF 操作和註釋所需的類別和方法的存取。

## 第 1 步：載入您的 PDF 文檔

首先，您需要載入要新增註釋的 PDF 文件。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DATA DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

發生的事情是這樣的：您指定 PDF 檔案的儲存目錄，然後使用`Document`由 Aspose.PDF 提供的類別。此步驟至關重要，因為如果不載入文檔，您就無法對其進行任何更改。

## 第 2 步：建立註釋

### 定義註釋屬性
現在，讓我們建立註釋本身。我們將使用一個`TextAnnotation`，非常適合在 PDF 中添加評論或註釋。

```csharp
//建立註釋
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

在這個片段中：
- 位置和大小：`Rectangle`類別定義註解在頁面上的顯示位置及其尺寸。
- 標題、主題和內容：這些屬性可讓您指定註釋的內容和內容。
- 圖示:`TextIcon.Key`為註釋設定圖標，使其更具視覺吸引力。

## 第 3 步：自訂註釋的外觀

接下來，讓我們透過添加邊框並調整其外觀來使該註釋脫穎而出。

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

以下是所發生情況的詳細說明：
- 邊界：我們創建一個`Border`物件並將其寬度設為 5，為我們的註釋提供突出的輪廓。
- 破折號圖案：`Dash`屬性允許您建立虛線邊框，為註釋添加一些樣式。

## 步驟 4：將註解新增至 PDF 頁面

建立並自訂註釋後，就可以將其新增至 PDF 頁面了。

```csharp
//新增註釋到頁面的註釋集合中
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

此程式碼將註解新增至 PDF 的第一頁。這`Annotations`集合保存特定頁面的所有註釋，此步驟可確保您的新註釋是該集合的一部分。

## 步驟5：儲存更新後的PDF文檔

最後，讓我們保存文檔，以便永久添加註釋。

```csharp
//儲存輸出檔案
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nAnnotation added successfully.\nFile saved at " + dataDir);
```

透過使用新名稱儲存文件（`AddAnnotation_out.pdf`），您保留原始文件並產生一個添加了註釋的新文件。控制台訊息確認一切成功，您現在可以在指定目錄中找到帶有註釋的 PDF。

## 結論

在 PDF 中添加註釋不僅是一個強大的功能，而且是一個強大的功能。使用 Aspose.PDF for .NET 也非常簡單。無論您是標記文件以供審閱還是添加註釋以供將來參考，本指南都涵蓋了您需要了解的所有內容。透過執行這些步驟，您可以建立自訂註釋來豐富您的 PDF，使其更加有用且更具互動性。

## 常見問題解答

### 我可以使用 Aspose.PDF for .NET 新增哪些類型的註解？
您可以新增各種類型的註釋，包括文字、連結、突出顯示和圖章註釋等。

### 我可以自訂註釋的外觀嗎？
絕對地！您可以自訂註釋的大小、顏色、邊框甚至圖示。

### 是否可以在一個頁面上新增多個註解？
是的，您可以根據需要在 PDF 中的任何頁面中添加任意數量的註釋。

### 新增註釋後可以刪除嗎？
是的，可以使用以下命令刪除註釋`Annotations.Delete`Aspose.PDF提供的方法。

### 我需要許可證才能使用 Aspose.PDF for .NET 嗎？
是的，要解鎖所有功能並避免任何限制，您需要[執照](https://purchase.aspose.com/buy)。您還可以獲得[臨時執照](https://purchase.aspose.com/temporary-license/)進行評估。