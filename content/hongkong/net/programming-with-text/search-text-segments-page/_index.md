---
title: 在 PDF 檔案中搜尋文字段頁面
linktitle: 在 PDF 檔案中搜尋文字段頁面
second_title: Aspose.PDF for .NET API 參考
description: 透過這份詳細的逐步指南，了解如何使用 Aspose.PDF for .NET 搜尋 PDF 檔案中的文字段。提取文字、分析片段等等。
type: docs
weight: 470
url: /zh-hant/net/programming-with-text/search-text-segments-page/
---
## 介紹

有沒有想過如何使用 Aspose.PDF for .NET 在 PDF 文件中定位特定文字區段？嗯，你很幸運！在本指南中，我們將以簡單的逐步方式引導您完成整個過程。無論您是嘗試提取資訊、分析文本，還是只是瀏覽複雜的 PDF 操作，Aspose.PDF for .NET 都能滿足您的需求。讓我們深入了解吧！

## 先決條件

在開始之前，讓我們確保您已擁有所需的一切：

-  Aspose.PDF for .NET：請確定您已安裝程式庫。你可以從[這裡](https://releases.aspose.com/pdf/net/).
- .NET Framework：確保您的電腦上安裝了 .NET。
- 開發環境：建議使用 Visual Studio 或任何支援 .NET 的 IDE。
- PDF 文件：您將在其中搜尋文本段的 PDF 文件。

如果您還沒有 Aspose.PDF for .NET，請別擔心！您可以從以下位置獲得免費試用[這裡](https://releases.aspose.com/)或購買它[這裡](https://purchase.aspose.com/buy).

## 導入包

在我們開始編碼之前，將必要的套件匯入到您的專案中至關重要。這可以確保所有必需的類別和方法都可用於您的 PDF 操作任務。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

準備好要點後，讓我們直接進入逐步指南。


## 第 1 步：載入 PDF 文檔

過程的第一步是將 PDF 檔案載入到程式中。如果沒有載入的文檔，就沒有什麼可搜尋的，對吧？操作方法如下。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

- `dataDir` ：該變數保存 PDF 檔案的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與儲存檔案的實際目錄。
- `pdfDocument` ：使用`Document`類別中，我們將 PDF 載入到記憶體中。

## 第 2 步：設定文字搜尋

現在您的文件已加載，下一步是建立一個`TextFragmentAbsorber`對象，它允許我們搜尋文件中的特定文字。

```csharp
//建立 TextAbsorber 物件以尋找輸入搜尋短語的所有實例
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

- `TextFragmentAbsorber` ：該物件用於捕獲您正在搜尋的文字的所有出現位置。代替`"text"`與您要搜尋的實際文字。

## 第 3 步：接受特定頁面的吸收器

您可能不會總是想搜尋整個 PDF 文件。在此範例中，我們將其範圍縮小到特定頁面。

```csharp
//接受所有頁面的吸收器
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

- `pdfDocument.Pages[2]`：這表示我們只搜尋文件的第二頁。您可以修改索引以定位其他頁面。
- `Accept()` ：該方法允許`TextFragmentAbsorber`處理指定頁面內的文字。

## 第四步：擷取文字片段

搜尋頁面後，我們將找到的文字片段提取到集合中。

```csharp
//取得擷取的文字片段
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`：此集合保存在搜尋過程中找到的文字片段的所有實例。

## 第 5 步：循環文字片段並提取數據

現在，讓我們循環遍歷每個文字片段並提取其詳細信息，例如位置、字體和顏色。

```csharp
//循環遍歷片段
foreach (TextFragment textFragment in textFragmentCollection)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        Console.WriteLine("Text : {0} ", textSegment.Text);
        Console.WriteLine("Position : {0} ", textSegment.Position);
        Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
        Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
        Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
        Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
        Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
        Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
        Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
        Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
    }
}
```

- `foreach (TextFragment textFragment in textFragmentCollection)` ：我們循環遍歷每個`TextFragment`在集合中。
- `foreach (TextSegment textSegment in textFragment.Segments)`：每個片段內部有多個片段。我們循環遍歷它們以收集所有相關資訊。
- 的各種屬性`textSegment`：這些為我們提供了有關文字的詳細信息，例如其位置（X 和 Y）、字體詳細資訊、大小和顏色。

## 第六步：輸出結果

最後，提取所有資訊後，在控制台中列印出結果。這可以幫助您準確地查看文字的位置及其格式詳細資訊。

為了清楚起見，以下是一個範例輸出：

```
Text : text
Position : X: 45.0, Y: 75.0
XIndent : 45.0
YIndent : 75.0
Font - Name : Arial
Font - IsAccessible : True
Font - IsEmbedded : False
Font - IsSubset : False
Font Size : 12.0
Foreground Color : System.Drawing.Color [Black]
```

- 此輸出為您提供指定頁面上文字「text」的確切位置和格式資訊。

## 結論

現在你就擁有了！您剛剛學習如何使用 Aspose.PDF for .NET 在 PDF 文件中搜尋特定文字段。在處理大型 PDF 時，此過程非常方便，可讓您有效地找出並提取關鍵文字。無論是分析資料、提取訊息，還是簡單地瀏覽文檔，Aspose.PDF 都為您提供了完成工作的強大工具。

## 常見問題解答

### 我可以搜尋多個單字或短語嗎？
是的，您可以修改`TextFragmentAbsorber`透過更改輸入字串來搜尋不同的文字。

### 是否可以跨多個頁面進行搜尋？
絕對地！您可以透過迭代來循環瀏覽 PDF 中的所有頁面`pdfDocument.Pages`.

### 如何搜尋不區分大小寫的文字？
你可以使用`TextSearchOptions`啟用不區分大小寫的搜尋。

### 找到文字後可以修改嗎？
是的，一旦您找到了`TextFragment`，您可以修改其文字屬性。

### 此方法適用於加密的 PDF 嗎？
可以，只要您使用正確的密碼解鎖 PDF。