---
title: 隱藏目錄中的頁碼
linktitle: 隱藏目錄中的頁碼
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在目錄中隱藏頁碼。請按照此包含程式碼範例的詳細指南來建立專業的 PDF。
type: docs
weight: 220
url: /zh-hant/net/programming-with-document/hidepagenumbersintoc/
---
## 介紹

當您使用 PDF 時，有時您可能想要產生目錄 (TOC)，但透過隱藏頁碼來保持簡潔。如果沒有它們，文件可能會更好地流動，或者這可能是一種美學選擇。無論您的原因是什麼，如果您使用 Aspose.PDF for .NET，本教學將準確地向您展示如何在目錄中隱藏頁碼。

## 先決條件

在我們開始之前，您需要準備一些東西。這是一個快速清單：

- 已安裝 Visual Studio：您需要 Visual Studio 的工作版本才能進行編碼。
- Aspose.PDF for .NET 程式庫：請確定您已安裝 Aspose.PDF for .NET 程式庫。
  - 下載連結：[.NET 的 Aspose.PDF](https://releases.aspose.com/pdf/net/)
- 臨時許可證：如果您正在測試這些功能，那麼擁有臨時許可證會很有幫助。
  - 臨時許可證：[在這裡獲取](https://purchase.aspose.com/temporary-license/)

## 導入包

在開始編寫程式碼之前，請確保在 C# 專案中匯入以下命名空間。這些將提供處理 PDF 文件和建立目錄 (TOC) 所需的類別和方法。

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

現在您的環境已準備就緒並且套件已匯入，讓我們分解流程的每個步驟。我們將介紹程式碼的每個部分以確保清晰，以便您可以輕鬆遵循。

## 步驟 1：初始化您的 PDF 文檔

我們需要做的第一件事是建立一個新的 PDF 文件並新增目錄 (TOC) 頁面。


```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
```

- dataDir：這是保存輸出檔的目錄。
- Document()：初始化一個新的 PDF 文件。
- Pages.Add()：在文件中新增一個新的空白頁，稍後將儲存您的目錄。

## 第 2 步：設定目錄資訊和標題

接下來，我們將定義目錄訊息，包括設定將顯示在目錄頂部的標題。

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

- TocInfo：該物件保存有關 TOC 的所有資訊。
- TextFragment：代表TOC標題的文本，這裡我們將其設定為「Table Of Contents」。
- FontStyle：我們透過將 TOC 標題的大小設為 20 並將其設為粗體來設定其樣式。
- tocPage.TocInfo：我們將目錄資訊指派給將顯示目錄的頁面。

## 步驟 3：隱藏目錄中的頁碼

現在是有趣的部分！這是我們配置目錄以隱藏頁碼的地方。

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
```

-  IsShowPageNumbers：這是隱藏頁碼的神奇開關。將其設定為`false`，且頁碼不會出現在目錄中。
- FormatArrayLength：我們將其設為 4，表示我們要定義四個層級的 TOC 標題的格式。

## 第 4 步：自訂目錄格式

為了在目錄中添加更多樣式，我們現在將為不同等級的標題定義格式。

```csharp
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
```

- FormatArray：此陣列控制 TOC 條目的格式。每個索引代表不同的標題層級。
- 邊距和文字樣式：我們設定邊距並為每個標題層級套用粗體、斜體和底線等字體樣式。

## 步驟 5：為文件新增標題

最後，讓我們添加將成為目錄一部分的實際標題。

```csharp
Page page = doc.Pages.Add();
for (int Level = 1; Level != 5; Level++)
{ 
    Heading heading2 = new Heading(Level); 
    TextSegment segment2 = new TextSegment(); 
    heading2.TocPage = tocPage; 
    heading2.Segments.Add(segment2); 
    heading2.IsAutoSequence = true; 
    segment2.Text = "this is heading of level " + Level; 
    heading2.IsInList = true; 
    page.Paragraphs.Add(heading2); 
}
```

- Heading 和 TextSegment：它們代表將出現在 TOC 中的標題。每個關卡都有自己的標題。
- IsAutoSequence：自動對標題進行編號。
- IsInList：確保每個標題都出現在目錄中。

## 第 6 步：儲存文檔

一切設定完成後，將 PDF 文件儲存到指定的輸出檔案。

```csharp
doc.Save(outFile);
```

就是這樣！您已成功建立帶有目錄的 PDF，並且頁碼已隱藏！

## 結論

在 PDF 中建立目錄並隱藏頁碼可能看起來很棘手，但使用 Aspose.PDF for .NET，這一切變得輕而易舉。透過遵循本逐步指南，您已了解如何自訂目錄格式、隱藏頁碼以及對標題套用不同的樣式。現在，您可以根據您的特定需求建立專業的 PDF。

## 常見問題解答

### 我可以在目錄中顯示特定標題的頁碼嗎？
不，Aspose.PDF 隱藏或顯示整個目錄的頁碼。您無法選擇性地隱藏特定條目的它們。

### 是否可以在目錄中新增更多層級？
是的，您可以增加`FormatArrayLength`定義更多層級的目錄標題。

### 如何更改所有目錄條目的字型？
可以透過修改字體來改變`TextState.Font`中每個層級的屬性`FormatArray`.

### 我可以在目錄中插入超連結嗎？
是的，您可以使用以下連結將每個目錄條目連結到文件中的特定部分`Heading.TocPage`財產。

### 我需要 Aspose.PDF 授權嗎？
是的，生產使用需要有效的許可證。您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/)來測試功能。