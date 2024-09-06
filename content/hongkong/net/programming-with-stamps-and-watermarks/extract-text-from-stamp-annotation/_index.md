---
title: 從圖章註釋中提取文本
linktitle: 從圖章註釋中提取文本
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 從 PDF 文件中的圖章註解中輕鬆擷取文字。
type: docs
weight: 80
url: /zh-hant/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
在本教學中，我們將逐步指導您如何使用 Aspose.PDF for .NET 從 PDF 文件中的圖章註解中提取文字。我們將向您展示如何使用提供的 C# 原始程式碼從 PDF 文件給定頁面上的特定圖章註釋中提取文字。

## 第一步：建構環境

在開始之前，請確保您具備以下條件：

- 已安裝的 .NET 開發環境。
- 下載 .NET 的 Aspose.PDF 庫並在您的專案中引用。

## 第 2 步：載入 PDF 文檔

第一步是將現有的 PDF 文件載入到您的專案中。方法如下：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入文檔
Document doc = new Document(dataDir + "test.pdf");
```

請務必將「您的文件目錄」替換為 PDF 文件所在目錄的實際路徑。

## 步驟 3：從圖章註釋中擷取文本

現在您已經加載了 PDF 文檔，您可以從特定圖章註釋中提取文字。方法如下：

```csharp
//檢索緩衝區註釋
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

//建立文字吸收器
TextAbsorber ta = new TextAbsorber();

//存取註釋的外觀
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

//顯示提取的文字
Console.WriteLine(ta.Text);
```

上面的程式碼從 PDF 文件的指定頁面檢索圖章註釋，然後使用文字吸收器從註釋的外觀中提取文字。然後，提取的文字將顯示在輸出中。

### 使用 Aspose.PDF for .NET 從圖章註解中擷取文字的範例原始程式碼 
```csharp

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
TextAbsorber ta = new TextAbsorber();
XForm ap = annot.Appearance["N"];
ta.Visit(ap);
Console.WriteLine(ta.Text);

```

## 結論

恭喜！您已了解如何使用 Aspose.PDF for .NET 從 PDF 文件中的圖章註釋中提取文字。現在您可以使用此方法從 PDF 文件中的其他註釋中提取文字。

### 從圖章註釋中提取文本的常見問題解答

#### Q：什麼是 PDF 文件中的圖章註釋？

答：PDF 文件中的圖章註釋是一種圖形元素，可用於提供附加資訊，例如浮水印或橡皮圖章。當您想要從這些註釋中檢索基於文字的內容（可能包括註釋、標籤或其他文字資訊）時，從圖章註釋中提取文字非常有用。

#### Q：提供的 C# 原始碼如何從圖章註解中提取文字？

答：提供的原始程式碼示範如何從 PDF 文件的給定頁面上的特定圖章註釋中提取文字。它使用 Aspose.PDF 庫來檢索圖章註釋，使用`TextAbsorber`，然後在輸出中顯示提取的文字。

#### Q：我可以使用類似的方法從不同類型的註釋中提取文字嗎？

答：是的，您可以使用類似的方法從其他類型的註釋中提取文本，例如文本註釋或彈出註釋。您需要修改程式碼以定位要從中提取文字的特定註釋類型。

####  Q：這樣做的目的是什麼`TextAbsorber` class in the code?

答： 的`TextAbsorber`類別用於從 PDF 文件的不同部分提取文本，包括圖章註釋。它「吸收」或捕獲 PDF 指定區域或元素中的文字內容。

#### 問：如何辨識要從中提取文本的特定圖章註釋？

答：在提供的代碼中，透過存取標記註釋來識別`Annotations`特定頁面的集合並使用索引來檢索所需的註釋。您可以調整索引或使用其他標準來識別目標註釋。

#### Q：我可以從同一頁上的多個圖章註釋中提取文字嗎？

 A：是的，你可以修改程式碼來循環遍歷`Annotations`頁面的集合，過濾掉圖章註釋，並從每個頁面中提取文字。

#### Q：印章註解沒有文字怎麼辦？代碼仍然有效嗎？

答：該程式碼仍然可以工作，但如果圖章註釋的外觀不包含任何文字內容，它將提取並顯示一個空字串。

#### Q：如何將提取的文字儲存到文件而不是在輸出中顯示？

答：您可以修改程式碼，將提取的文字儲存到文件中，而不是將其顯示在控制台中。只需更換`Console.WriteLine`帶有將文字寫入文件的程式碼的語句。

#### 問：如何使用擷取的文字進行進一步處理或分析？

答：使用提供的方法提取文字後，您可以將其儲存在變數中，對其進行操作、分析，或根據需要將其整合到應用程式的其他部分。