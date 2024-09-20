---
title: 將結構元素加入元素中
linktitle: 將結構元素加入元素中
second_title: Aspose.PDF for .NET API 參考
description: 在此全面的逐步教學中，了解如何使用 Aspose.PDF for .NET 將輔助功能結構元素新增至 PDF 中。
type: docs
weight: 20
url: /zh-hant/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
## 介紹

在當今的數位世界中，可訪問性是關鍵。每個人都應該有平等的機會獲取信息，並以所有人都能輕鬆瀏覽的格式提供信息至關重要。在本教學中，我們將深入探討如何使用 Aspose.PDF for .NET 新增結構元素來增強 PDF 的可存取性。這個功能強大的程式庫使開發人員能夠無縫地處理 PDF 文檔，從而創建符合輔助功能標準的標籤的 PDF。

## 先決條件

在我們開始進入 PDF 結構元素的世界之前，讓我們確保您擁有所需的一切：

1.  視覺工作室：這是您的 IDE，您將在其中編寫和執行 C# 程式碼。您可以從以下位置下載：[Visual Studio](https://visualstudio.microsoft.com/)如果你還沒有。
2.  Aspose.PDF for .NET Library：您需要該程式庫來操作 PDF。從以下位置下載最新版本[阿斯普斯網站](https://releases.aspose.com/pdf/net/)。這個庫對於我們的專案至關重要。
3. C# 基礎知識：熟悉 C# 語法和物件導向程式設計將很有幫助。如果您能愉快地編寫幾行 C#，那麼您就可以開始了！
4. PDF 文件目錄：在系統上建立一個目錄，用於保存本教學的輸入和輸出 PDF 文件。

現在我們已經準備好了工具和知識，讓我們引入必要的包來開始吧！

## 導入包

首先，讓我們導入必要的名稱空間。確保 C# 檔案頂部包含以下內容：

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
```

這些命名空間可讓您存取處理 PDF 文件和建立標記內容所需的類別和方法。現在，讓我們進入問題的核心並開始編碼！

## 第 1 步：設定您的文件目錄

在進行任何編碼之前，我們需要確定文件的保存位置。這對於我們的腳本順利運行至關重要。

```csharp
//定義文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
```

代替`"YOUR DOCUMENT DIRECTORY"`與您想要儲存 PDF 檔案的實際路徑。這可能是這樣的`C:\\PDFs\\`.

## 第 2 步：建立新的 PDF 文檔

現在我們已經設定了目錄，讓我們建立一個 PDF 文檔，在其中加入結構元素。

```csharp
Document document = new Document();
```

這一行初始化了一個新的實例`Document`類，使我們能夠開始處理 PDF 內容。

## 第 3 步：存取和設定標記內容

文件準備就緒後，就可以設定標記內容，這對於可訪問性至關重要。

### 初始化標記內容

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

此行提供對 PDF 標記內容的存取。螢幕閱讀器需要標記內容才能準確解釋您的文件。

### 設定文檔元數據

您需要為文件指定適當的標題並定義語言。

```csharp
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
```

這增強了文件的元資料並提高了其可存取性。

## 第 4 步：建立並附加結構元素

讓我們來添加一些結構！這涉及創建段落和跨度元素，以便創建格式正確且標記正確的文件。

### 建立根結構元素

```csharp
StructureElement rootElement = taggedContent.RootElement;
```

現在，我們將建立第一組段落和 span 元素。

### 建立第一個段落元素

```csharp
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```

在這裡，我們初始化一個新的段落元素並將其附加到根結構元素。這是您內容的起點！

### 將 Span 元素加入段落

```csharp
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
```

這`span`元素就像大段落中的小段落。它們允許更好地控製文字格式。

### 結合一切

現在讓我們用所有元素來建構完整的段落：

```csharp
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
```

### 重複其他段落

您將對其他段落重複此過程：

```csharp
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
```

只要繼續創造`ParagraphElement`沙`SpanElement`s，將它們附加到`rootElement`以與上面所示相同的方式`p1`.

## 第 5 步：儲存您的文檔

所有結構元素就位後，就可以儲存 PDF 文件了。

### 指定輸出檔案路徑

```csharp
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
```

### 儲存文件

```csharp
document.Save(outFile);
```

這就是魔法發生的地方！您的文件將儲存到指定的輸出文件路徑。

## 第 6 步：驗證 PDF/UA 合規性

最後一步涉及檢查您的文件是否符合 PDF/UA 可訪問性標準。

若要檢查合規性，請使用以下程式碼：

```csharp
document = new Document(outFile);
string logFile = dataDir + "46144_log.xml";
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

這將輸出您的文件是否符合 PDF/UA 標準，這對於可訪問性至關重要。

## 結論

現在你就擁有了！您剛剛學習如何使用 Aspose.PDF for .NET 將結構元素新增至 PDF 文件中。透過執行這些步驟，您可以將任何 PDF 轉換為符合標準的易於存取的格式，確保每個人都可以平等地存取資訊。 

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個函式庫，可讓開發人員以程式設計方式建立、操作和轉換 PDF 文件。

### 如何檢查我的 PDF 是否可存取？
您可以使用 Aspose.PDF 庫根據 PDF/UA 標準驗證您的 PDF，以確保其符合輔助使用指南。

### 我可以免費使用 Aspose.PDF 嗎？
是的，Aspose 提供免費試用版，讓您無需支付任何費用即可探索其功能。你可以下載它[這裡](https://releases.aspose.com/).

### 在哪裡可以找到 Aspose.PDF 的文件？
您可以找到 Aspose.PDF 的綜合文檔[這裡](https://reference.aspose.com/pdf/net/).

### 如何購買 Aspose.PDF 的授權？
您可以直接從 Aspose 網站購買許可證[這裡](https://purchase.aspose.com/buy).