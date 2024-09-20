---
title: 提取 PDF 文件中的列文本
linktitle: 提取 PDF 文件中的列文本
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 從 PDF 檔案中提取文字列。本指南透過程式碼範例和說明分解了每個步驟。
type: docs
weight: 150
url: /zh-hant/net/programming-with-text/extract-columns-text/
---
## 介紹

您是否正在處理 PDF 文件並需要提取特定列格式的文字？無論您是處理發票、報告還是任何結構化文檔，從 PDF 中準確提取文字都可能是一件棘手的事情。這就是 Aspose.PDF for .NET 發揮作用來簡化流程的地方。在本教程中，我們將引導您了解如何輕鬆地從 PDF 文件中提取文字列。 

## 先決條件

在深入研究程式碼之前，讓我們先介紹一下您需要的基本內容：

-  Aspose.PDF for .NET：請確定您已安裝了最新版本的 Aspose.PDF for .NET。如果沒有，您可以[在這裡下載](https://releases.aspose.com/pdf/net/).
- 開發環境：您需要 Visual Studio 或其他 .NET 開發環境來處理程式碼。
- PDF 文檔：手邊有一個範例 PDF 文檔，最好是帶有文字列的文檔，因為我們將從其中提取文字。

如果您還沒有安裝 Aspose.PDF for .NET，您可以取得[免費試用](https://releases.aspose.com/)或者[購買許可證](https://purchase.aspose.com/buy)以獲得完整的功能。您還可以申請[臨時執照](https://purchase.aspose.com/temporary-license)如果需要的話。

## 導入命名空間

若要在專案中使用 Aspose.PDF for .NET，您需要匯入以下命名空間：

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## 逐步指南：從 PDF 提取文字列

現在，讓我們分解程式碼的每個部分，以便更好地理解它是如何工作的。請跟隨我們一步步進行，解釋過程的每個部分。

## 第 1 步：載入 PDF 文檔

您需要做的第一件事是將 PDF 文件加載到`Document`目的。這就是 Aspose.PDF 與文件互動的方式。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

在此步驟中，我們只是定義儲存 PDF 文件的目錄。代替`"YOUR DOCUMENT DIRECTORY"`以及本地 PDF 檔案的路徑。這`Document`物件將 PDF 載入到記憶體中，以便可以進行進一步處理。

## 第 2 步：設定文字片段吸收器

接下來，我們將使用一個`TextFragmentAbsorber`吸收或捕獲 PDF 文件中的所有文字。此吸收器類別旨在從 PDF 中的特定區域提取文字片段，這使其成為提取文字列的理想選擇。

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
```

在這裡，我們建立一個實例`TextFragmentAbsorber`並將其套用到 PDF 的所有頁面`Accept()` 。這`TextFragmentCollection`儲存提取的文本，從這個集合中，我們可以根據需要操作或提取文本。

## 步驟 3：調整擷取文字的字體大小

捕獲文字片段後，您可能需要減小其字體大小，尤其是當原始文字太大時。在此範例中，我們將字體大小減小了 70%。

```csharp
foreach (TextFragment tf in tfc)
{
    //將字體大小縮小 70%
    tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

這段程式碼循環遍歷每個`TextFragment`並將其字體大小縮小了 70%。調整字體大小可以使提取的文字更易於管理，特別是當您出於不同目的對其進行格式化時。

## 步驟 4：將文件儲存到記憶體流

修改文字後，我們將PDF儲存為`MemoryStream`。這使我們能夠將文件保留在記憶體中以供進一步處理，而無需將其寫回磁碟。

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
```

在這裡，我們將 PDF 儲存到記憶體流中，然後重新載入文件。當您處理大檔案並希望避免不必要的磁碟操作時，此方法非常有用。

## 第 5 步：使用文本吸收器提取所有文本

現在我們已經準備好了 PDF，是時候提取文字了。我們將使用`TextAbsorber`從文件中獲取所有文字。

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
```

在這一步中，`TextAbsorber`吸收PDF中的所有文本，提取的文本存儲在`extractedText`細繩。這就是奇蹟發生的地方——您的文字列現在採用純文字格式！

## 第 6 步：將提取的文字儲存到文件中

最後，我們將提取的文字儲存到`.txt`文件以便於存取和進一步使用。

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

此程式碼將提取的文字寫入新的`.txt`文件並將其保存在您指定的目錄中。控制台中會顯示一則訊息，確認流程已成功。

## 結論

給你了！使用 Aspose.PDF for .NET 從 PDF 文件中提取文字列比您想像的要容易。只需幾行程式碼，您就可以載入 PDF、提取特定文字、調整格式並將結果儲存到文字檔案中。

該技術對於處理結構化文件（例如表格、報告或按列組織的任何內容）非常有用。無論您需要自動提取資料還是處理批次文檔，Aspose.PDF 都提供了有效實現這一目標的工具。

## 常見問題解答

### 我可以從 PDF 的特定頁面中提取文字嗎？  
是的！您可以修改`TextFragmentAbsorber`使用以下命令來定位特定頁面`pdfDocument.Pages[pageIndex].Accept(tfa);`方法。

### 是否可以僅從多列 PDF 中的一列中提取文字？  
是的，但是您需要使用以下命令來處理文字片段的座標`TextFragment.Rectangle`針對文檔的特定區域。

### 如何提高文字擷取的準確性？  
為了獲得更高的準確性，請確保 PDF 的結構定義良好，並避免使用佈局複雜的文件。您還可以微調`TextFragmentAbsorber`根據字體樣式、大小或區域提取文字。

### Aspose.PDF支援從掃描文件中提取文字嗎？  
是的，但您需要使用 OCR（光學字元辨識）技術。 Aspose 也為此提供了工具。

### 如何處理數千頁的大型 PDF 檔案？  
對於大型 PDF，請透過一次從幾頁中提取文字來分塊處理文檔，以避免高記憶體使用量。