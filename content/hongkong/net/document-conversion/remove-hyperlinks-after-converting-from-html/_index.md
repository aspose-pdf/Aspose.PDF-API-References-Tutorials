---
title: 從 Html 轉換後刪除超鏈接
linktitle: 從 Html 轉換後刪除超鏈接
second_title: Aspose.PDF for .NET API 參考
description: 在此逐步指南中，了解如何使用 Aspose.PDF for .NET 將 HTML 文件轉換為 PDF 後刪除超連結。
type: docs
weight: 250
url: /zh-hant/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
## 介紹

在數位時代，將 HTML 文件轉換為 PDF 是一項常見任務。但是，有時您可能出於各種原因想要從轉換後的 PDF 中刪除超鏈接，例如增強可讀性或防止不必要的導航。在本教學中，我們將探索如何使用 Aspose.PDF for .NET 來實現這一目標。 

## 先決條件

在深入研究程式碼之前，請確保您符合以下先決條件：

1. Visual Studio：確保您的電腦上安裝了 Visual Studio。這將是您的開發環境。
2.  Aspose.PDF for .NET：您需要擁有 Aspose.PDF 庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/pdf/net/).
3. C#基礎知識：熟悉C#程式設計將有助於您更好地理解程式碼。

## 導入包

首先，您需要在 C# 專案中匯入必要的套件。您可以這樣做：

1. 開啟您的 Visual Studio 專案。
2. 在解決方案資源管理器中以滑鼠右鍵按一下您的項目，然後選擇「管理 NuGet 套件」。
3. 搜尋`Aspose.PDF`並安裝它。

```csharp
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.IO;
```

現在您已完成所有設置，讓我們分解一下將 HTML 文件轉換為 PDF 後從 HTML 文件中刪除超連結的過程。

## 第 1 步：設定文檔目錄

首先，您需要指定文檔目錄的路徑。這是 HTML 檔案所在的位置以及輸出 PDF 的儲存位置。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`與儲存 HTML 檔案的實際路徑。

## 第 2 步：載入 HTML 文檔

接下來，您將使用以下命令載入 HTML 文檔`Document`來自 Aspose.PDF 的類別。此類別可讓您輕鬆處理 PDF 文件。

```csharp
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
```

在這裡，我們載入名為的 HTML 文件`SampleHtmlFile.html`。確保該檔案存在於您指定的目錄中。

## 步驟 3：將文件儲存到記憶體流

在開始處理註解之前，我們需要將文件儲存到記憶體流中。此步驟至關重要，因為它為進一步操作準備文件。

```csharp
doc.Save(new MemoryStream());
```

該行將文件保存在記憶體中，使我們無需將其寫入磁碟即可使用它。

## 第 4 步：迭代註釋

現在，我們將迭代文件中的註釋。註釋是連結、評論和突出顯示等元素。我們對連結註釋特別感興趣。

```csharp
foreach (Annotation a in doc.Pages[1].Annotations)
{
    if (a.AnnotationType == AnnotationType.Link)
    {
        //處理連結註釋
    }
}
```

在此循環中，我們檢查註解類型是否為連結。如果是，我們將繼續執行後續步驟。

## 第 5 步：刪除超連結操作

對於每個連結註釋，我們需要檢查它是否具有超連結操作。如果是這樣，我們將透過將超連結的 URI 設為空字串來刪除該超連結。

```csharp
LinkAnnotation la = (LinkAnnotation)a;
if (la.Action is GoToURIAction)
{
    GoToURIAction gta = (GoToURIAction)la.Action;
    gta.URI = "";
```

此程式碼片段可確保有效刪除超連結操作。

## 第六步：吸收文字片段

接下來，我們將吸收與連結註釋相關的文字片段。這使我們能夠操縱文字的外觀。

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
doc.Pages[a.PageIndex].Accept(tfa);
```

在這裡，我們創建一個`TextFragmentAbsorber`並將其搜尋選項設為註釋的矩形。這有助於我們找到連結的文字。

## 步驟7：修改文字外觀

一旦我們有了文字片段，我們就可以修改它們的外觀。在這種情況下，我們將刪除下劃線並將文字顏色變更為黑色。

```csharp
foreach (TextFragment tf in tfa.TextFragments)
{
    tf.TextState.Underline = false;
    tf.TextState.ForegroundColor = Color.Black;
}
```

此步驟透過刪除超連結樣式來增強文字的可讀性。

## 步驟8：刪除註釋

修改文字後，我們可以安全地從文件中刪除連結註解。

```csharp
doc.Pages[a.PageIndex].Annotations.Delete(a);
}
```

此行從 PDF 中刪除超鏈接，確保它不再存在於最終輸出中。

## 步驟9：儲存修改後的文檔

最後，我們需要將修改後的文件儲存到新的PDF文件中。這是我們流程的最後一步。

```csharp
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

此行保存已刪除超連結的文檔，建立一個名為的新 PDF 文件`RemoveHyperlinksFromText_out.pdf`.

## 結論

現在你就擁有了！使用 Aspose.PDF for .NET 將 HTML 文件轉換為 PDF 後，您已成功刪除了其中的超連結。此過程不僅可以增強 PDF 的可讀性，還可以讓您控制所呈現的內容。 

## 常見問題解答

### 我可以從任何 PDF 文件中刪除超連結嗎？
是的，您可以使用 Aspose.PDF for .NET 從任何 PDF 文件中刪除超連結。

### Aspose.PDF 可以免費使用嗎？
 Aspose.PDF 提供免費試用版，但要獲得完整功能，您需要購買授權。檢查[購買頁面](https://purchase.aspose.com/buy).

### 如果我在使用 Aspose.PDF 時遇到問題怎麼辦？
您可以在以下方面尋求協助[支援論壇](https://forum.aspose.com/c/pdf/10).

### 我可以使用 Aspose 將其他文件格式轉換為 PDF 嗎？
是的，Aspose 支援將各種文件格式轉換為 PDF。

### 哪裡可以下載 Aspose.PDF for .NET？
您可以從[下載連結](https://releases.aspose.com/pdf/net/).