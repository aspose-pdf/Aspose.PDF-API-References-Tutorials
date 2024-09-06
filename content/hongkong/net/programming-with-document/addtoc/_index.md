---
title: 新增目錄到 PDF 文件
linktitle: 新增目錄到 PDF 文件
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 將目錄新增至 PDF。本逐步指南簡化了流程並確保在文件中輕鬆導航。
type: docs
weight: 40
url: /zh-hant/net/programming-with-document/addtoc/
---
## 介紹

您是否曾經無止盡地瀏覽過一份冗長的 PDF，希望它有一個組織良好的目錄？好吧，今天就是你的幸運日！在本教學中，您將學習如何使用 Aspose.PDF for .NET 將目錄新增至 PDF 檔案。無論您正在處理複雜的報告、電子書還是商業提案，目錄都可以將您的文件轉變為專業的、易於導航的傑作。

## 先決條件

在我們進入程式碼之前，讓我們確保您已擁有所需的一切：

1. Aspose.PDF for .NET：請確定您已下載並安裝了 Aspose.PDF 庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/pdf/net/).
   
2. 開發環境：確保您的電腦上設定有 .NET 開發環境，例如 Visual Studio。

3. 許可證：如果您沒有許可證，可以獲得免費試用或申請臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

## 導入包

首先，請確保在程式碼檔案的開頭匯入必要的命名空間。方法如下：

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

這些命名空間可讓您存取 PDF 特定的功能並操作文件中的文字元素。

讓我們把這個任務分成幾個小步驟。每個步驟將引導您完成建立目錄並將其插入 PDF 文件的過程。

## 第 1 步：載入 PDF 文檔

我們需要做的第一件事是載入現有的 PDF 文件，將其新增到要新增目錄的位置。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

在此步驟中，我們指定文件目錄的路徑並使用以下命令載入 PDF`Document`目的。確保更換`"YOUR DOCUMENT DIRECTORY"`與文件的實際路徑。

## 第 2 步：為目錄插入新頁面

接下來，我們在 PDF 文件的開頭插入一個新頁面。此頁將包含目錄。

```csharp
Page tocPage = doc.Pages.Insert(1);
```

透過在開頭插入 TOC 頁面，我們確保它作為讀者在 PDF 中首先看到的內容出現。

## 步驟 3：建立 TOC 資訊對象

現在，讓我們建立一個表示 TOC 資訊的物件。我們還將為目錄添加標題以使其脫穎而出。

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

在這裡，我們將目錄標題設為“目錄”，增大了字體大小，並加粗以示強調。

## 步驟 4：定義目錄元素

在此步驟中，我們定義將在目錄中顯示的元素（或標題）。這些元素將幫助讀者導航到文件的特定部分。

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
```

我們建立了一個字串數組，用作目錄項，對應於 PDF 中的不同頁面。

## 第 5 步：建立目錄標題

現在到了關鍵部分——向目錄添加標題並將它們連結到各自的頁面。

```csharp
for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;
    segment2.Text = titles[i];

    tocPage.Paragraphs.Add(heading2);
}
```

這是發生的事情：
- 標題：我們創建一個`Heading`對象並添加一個`TextSegment`到它。
- 目標頁面：我們設定每個標題將連結到的頁面。
- 頂部位置：我們指定標題在頁面上指向的位置。
- 文字：每個標題從我們之前創建的數組中獲取其各自的標題。

此循環為目錄中的前兩個元素建立標題並將它們連結到相應的頁面。

## 第 6 步：儲存 PDF 和目錄

最後，在新增所有目錄元素後，是時候儲存更新的 PDF 了。

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
```

現在，文件已儲存，目錄已新增至 PDF。恭喜您 - 您已成功新增目錄！

## 步驟7：確認訊息

為了讓使用者知道流程已完成，我們將在控制台中顯示簡單的訊息。

```csharp
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## 結論

現在你就擁有了！透過 Aspose.PDF for .NET，在 PDF 中新增目錄不僅簡單，而且可以自訂。無論您需要建立簡單的導航連結還是複雜的結構，這個工具都能滿足您的需求。因此，下次您處理冗長的 PDF 時，請不要忘記添加目錄以實現專業的風格！

## 常見問題解答

### 我可以在 Aspose.PDF 中自訂 TOC 的外觀嗎？  
是的，您可以完全自訂目錄的外觀，包括字體樣式、大小和對齊方式。

### 如何為目錄新增副標題？  
您可以透過調整來新增副標題`Heading`水平（例如，`Heading(2)`）建立分層目錄。

### 如果文件發生變化，是否可以自動更新目錄？  
不，目錄不會自動更新。如果文件結構發生更改，您將需要重新建立它。

### 我可以將目錄條目連結到外部文件嗎？  
是的，您可以使用超連結將目錄條目連結到外部 PDF 或 URL。

### Aspose.PDF 支援多層目錄嗎？  
是的，Aspose.PDF 支援帶有子部分的複雜文件的多層目錄。