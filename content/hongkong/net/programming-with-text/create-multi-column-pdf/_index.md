---
title: 建立多列 PDF
linktitle: 建立多列 PDF
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 建立多列 PDF。包含程式碼範例和詳細說明的逐步指南。非常適合專業人士。
type: docs
weight: 110
url: /zh-hant/net/programming-with-text/create-multi-column-pdf/
---
## 介紹

建立多列 PDF 是以更有條理、更易讀的格式呈現文字的好方法。無論您是在為出版物製作報告、文章還是佈局，多欄結構都可以使您的內容更具吸引力。在本教學中，我們將逐步介紹如何使用 Aspose.PDF for .NET 建立多列 PDF。不用擔心，我們會將其全部分解為簡單的步驟，即使您是該平台的新手，也可以輕鬆遵循。

## 先決條件

在我們開始編寫程式碼之前，您需要做好一些準備工作才能順利進行：

1.  Aspose.PDF for .NET：您需要安裝此程式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/pdf/net/).
2. 開發環境：設定您喜歡的 IDE（例如 Visual Studio），用於編寫和執行 C# 程式碼。
3. .NET Framework：確保您安裝了相容版本的 .NET。
4. 對 C# 的基本了解：熟悉 C# 語法將會有所幫助，但我們將詳細解釋每個步驟。
5. 臨時許可證：Aspose.PDF 需要許可證以避免浮水印或限制。你可以獲得一個[臨時執照](https://purchase.aspose.com/temporary-license/)如果需要的話。

## 導入包

在開始編碼之前，您需要匯入必要的命名空間，以便與 Aspose.PDF 進行互動。以下是您需要匯入的內容：

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

這些命名空間提供對建立 PDF、繪製形狀和處理文字格式所需的類別的存取。

讓我們將建立多列 PDF 的流程分解為簡單、易於管理的步驟。

## 第 1 步：設定文檔

首先，您需要建立一個新的 PDF 文件。這涉及定義頁邊距並添加內容所在的頁面。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//建立新的 PDF 文檔
Document doc = new Document();

//設定 PDF 檔案的邊距
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;

//新增頁面
Page page = doc.Pages.Add();
```

在這裡，我們創建了一個`Document`物件並將左右邊距設定為 40 個單位。然後，我們向該文件添加了一個新頁面，它將保存我們的多列佈局。

## 步驟 2： 在單獨的部分中新增一條線

接下來，我們在頁面上新增一條水平線以進行視覺分隔。這有助於打造乾淨、專業的外觀。

```csharp
//創建一個圖形物件來保持線條
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500.0, 2.0);

//將行加入到頁面的段落集合中
page.Paragraphs.Add(graph1);

//定義線的座標
float[] posArr = new float[] { 1, 2, 500, 2 };

//建立一條線並將其新增至圖表中
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
```

在這裡，我們使用創建一條水平線`Graph`和`Line`類。該行被加入到頁面的`Paragraphs`集合，包含所有視覺元素。

## 第 3 步：新增帶格式的 HTML 文字

接下來，讓我們插入一些包含 HTML 標籤的文本，以展示如何在 PDF 中動態設定文本格式。

```csharp
//建立一個包含 HTML 內容的字串
string s = "<font face=\"Times New Roman\" size=4>" +
           "<strong> How to Steer Clear of Money Scams </strong>" +
           "</font>";

//使用格式化文字建立一個新的 HtmlFragment
HtmlFragment heading_text = new HtmlFragment(s);

//將 HTML 文字新增至頁面
page.Paragraphs.Add(heading_text);
```

使用`HtmlFragment`在類別中，我們可以新增格式化文本，其中包括 HTML 標記，例如字體大小、樣式和粗體文字。這對於增強 PDF 內容的外觀非常有用。

## 步驟 4：建立多列佈局

現在我們將建立一個多列佈局。這就是神奇的地方——你可以指定你想要的列數以及它們的寬度。

```csharp
//建立一個浮動框來容納列
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();

//設定列數和列間距
box.ColumnInfo.ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

//將框新增至頁面
page.Paragraphs.Add(box);
```

在這裡，我們建立一個包含兩個欄位的浮動框。我們設定列之間的間距，並指定每列的寬度應為 105 個單位。這使我們能夠在 PDF 中建立所需的列佈局。

## 第 5 步：向列新增文本

現在讓我們用一些文字內容填充列。您可以添加不同的`TextFragment`物件到每一列。

```csharp
//建立並格式化第一個文字片段
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.FontStyle = FontStyles.Italic;
box.Paragraphs.Add(text1);

//新增另一條線進行分隔
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50.0, 10.0);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

//建立並新增第二個文字片段
TextFragment text2 = new TextFragment("Lorem ipsum dolor sit amet, consectetur adipiscing elit...");
box.Paragraphs.Add(text2);
```

我們添加一個`TextFragment`到浮動框，然後是另一條水平線。第二個`TextFragment`包含更多文字來填充第二列。這些片段允許我們使用不同的格式選項將各種文字元素新增到 PDF 中。

## 第 6 步：儲存 PDF

新增所有內容後，最後一步是將文件另存為 PDF 文件。

```csharp
//定義 PDF 的輸出路徑
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";

//儲存 PDF 文件
doc.Save(dataDir);

//輸出成功訊息
Console.WriteLine("\nMulti-column PDF file created successfully.\nFile saved at " + dataDir);
```

該區塊將 PDF 檔案儲存到指定目錄並在控制台中輸出成功訊息。 PDF 現在可供查看！

## 結論

透過遵循這些簡單的步驟，您可以使用 Aspose.PDF for .NET 輕鬆建立具有專業外觀的多列 PDF。無論是報告、文章或時事通訊，此技術都有助於將內容組織成具有視覺吸引力的格式。 Aspose.PDF 提供了強大的工具來自訂 PDF，從邊距和佈局到文字格式和繪圖形狀。現在輪到您嘗試一下，將您的 PDF 創建技能提升到新的水平！

## 常見問題解答

### 我可以在 PDF 中建立兩列以上嗎？
是的，您可以根據需要建立任意數量的列。只需調整`ColumnCount`屬性來符合您想要的列數。

### 如何變更每列的寬度？
您可以修改`ColumnWidths`屬性來為每列指定不同的寬度。此屬性接受一串由空格分隔的值。

### 是否可以將圖像新增至列？
絕對地！您可以使用新增圖像`Image`類別並將它們包含在 PDF 中的浮動框或任何其他佈局元素中。

### 我可以在列中使用 HTML 標籤設定文字樣式嗎？
是的，您可以在其中使用 HTML 標籤`HtmlFragment`物件來設定文字樣式。這包括添加字體、大小、顏色等。

### 如何新增更多具有相同列佈局的頁面？
您可以使用新增附加頁面`doc.Pages.Add()`並重複為每個頁面新增列和內容的過程。