---
title: 頁首頁尾部分中的表格
linktitle: 頁首頁尾部分中的表格
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件的頁首/頁尾部分新增表格。
type: docs
weight: 170
url: /zh-hant/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
## 介紹

您是否曾發現自己盯著一個普通的 PDF 文檔，希望它有額外的功能？嗯，你很幸運！ Aspose.PDF for .NET 可讓您像專業人士一樣建立和操作 PDF 檔案。今天，我們將深入研究一項方便的功能，可讓您在 PDF 文件的頁首中新增表格。你不僅會學會如何做，而且我會一步步指導你，讓整個過程像黃油一樣順利。 🎉

## 先決條件

在我們開始實際的編碼部分之前，讓我們確保您擁有開始所需的一切。這是您需要的：

1.  Visual Studio：確保您的電腦上安裝了 Visual Studio。如果還沒有，您可以從以下位置下載[微軟的網站](https://visualstudio.microsoft.com/).
2. Aspose.PDF 庫：您必須擁有適用於 .NET 的 Aspose.PDF 庫。您可以使用以下連結獲取[Aspose.PDF for .NET 套件](https://releases.aspose.com/pdf/net/).
3. C# 基礎知識：您至少應該對 C# 有基本了解。如果您還在學習，請不要擔心；我會盡量簡單！

## 導入包

好吧，是時候捲起袖子開始編碼了！但首先，我們需要透過導入必要的套件來設定環境。操作方法如下：

###  打開您的項目
開啟您將在其中建立 PDF 的 Visual Studio 專案。 

###  新增對 Aspose.PDF 的引用
1. NuGet 套件管理器：在解決方案資源管理器中以滑鼠右鍵按一下您的項目，然後選擇「管理 NuGet 套件」。
2. 搜尋 Aspose.PDF：在搜尋欄中輸入「Aspose.PDF」並安裝該軟體包。

到此步驟結束時，您應該已完成所有設定並準備好開始編碼！

現在，讓我們動手編寫一些程式碼吧！請依照以下步驟在 PDF 的標題部分建立表格：

## 第 1 步：設定文檔目錄的路徑

在開始建立 PDF 之前，我們需要定義文件的儲存位置。操作方法如下：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY"; //將其變更為您的實際目錄
```

代替`YOUR DOCUMENT DIRECTORY`以及您要儲存 PDF 的路徑。它可以位於系統上的任何位置 - 只要確保它可以訪問即可！

## 第 2 步：實例化文檔

接下來，我們將建立一個新的 PDF 文件。

```csharp
//透過呼叫空建構函式實例化 Document 實例
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();
```

我們在這裡所做的是創建一個空的 PDF 文檔，我們將在其中添加所有的好東西。

## 第 3 步：建立新頁面

讓我們為文件新增一個新頁面。 

```csharp
//在 pdf 文件中建立頁面
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

將此頁面視為空白畫布，我們將在其中繪製我們的傑作！

## 第 4 步：建立標題部分

現在我們將為 PDF 建立一個標題。

```csharp
//建立 PDF 檔案的標題部分
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
```

這個標題將保存我們的桌子。 

## 第 5 步：將標題分配給頁面

接下來，我們要確保我們的標題出現在頁面上。

```csharp
//設定 PDF 檔案的奇數頁眉
page.Header = header;
```

## 第 6 步：設定上邊距

為了確保標題頂部有一些喘息空間，讓我們調整邊距。

```csharp
//設定標題部分的上邊距
header.Margin.Top = 20;
```

設置邊距就像給文字一些個人空間一樣——沒有人喜歡被擁擠！

## 第7步：建立表

現在，是時候建立將進入我們的標題的表格了。

```csharp
//實例化一個表對象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## 步驟 8：將表格新增至標題

我們將新建立的表格新增到標題的段落集合中。

```csharp
//將表格新增至所需部分的段落集合中
header.Paragraphs.Add(tab1);
```

## 步驟9：設定單元格邊框

讓我們透過定義預設儲存格邊框來為表格提供一些結構。

```csharp
//使用 BorderInfo 物件設定預設儲存格邊框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## 第 10 步：定義列寬

您可以指定表格每列的寬度。

```csharp
//設定表格的列寬
tab1.ColumnWidths = "60 300";
```

這些值表示每列的寬度（以磅為單位）。請隨意調整它們以滿足您的需求！

## 第 11 步：建立行並新增儲存格

是時候添加一些行和單元格了！ 

```csharp
//在表格中建立行，然後在行中建立儲存格
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;
```

這將建立第一行，其中包含包含文字的儲存格，並將其背景顏色設為灰色。

## 第12步：設定行距和文字樣式

您希望您的行跨越多列嗎？方法如下：

```csharp
//將第一行的行跨距值設為 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
```

此步驟不僅設定行跨度，還更改文字顏色和字體。

## 第 13 步：新增第二行

讓我們在表中添加另一行，好嗎？

```csharp
//在表中建立另一行
Aspose.Pdf.Row row2 = tab1.Rows.Add();

//設定 Row2 的背景顏色
row2.BackgroundColor = Color.White;
```

## 步驟 14：將影像新增至第二行

現在我們將添加一個徽標，讓我們的桌子看起來很時髦！

```csharp
//新增儲存影像的儲存格
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg"; //確保將圖像放置在您的目錄中
```

不要忘記更換`"aspose-logo.jpg"`與您映像的實際名稱！

## 第15步：調整影像寬度

設定圖像寬度以確保它在單元格中看起來恰到好處。

```csharp
//將影像寬度設定為 60
img.FixWidth = 60;

//將圖像新增至表格單元格
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
cell2.Paragraphs.Add(img);
```

## 第 16 步：將文字新增至第二個儲存格

是時候在我們的標誌旁邊添加一些文字了！

```csharp
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
```

## 步驟 17：垂直和水平對齊文本

確保一切看起來都很整潔。對齊您的文字！

```csharp
//將文字的垂直對齊方式設定為居中對齊
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## 第18步：儲存PDF文檔

最後但並非最不重要的一點是，讓我們保存我們的創作！

```csharp
//儲存 PDF 文件
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

瞧！您已經建立了一個令人驚嘆的 PDF，並在標題部分包含了一個表格！

## 結論

現在你就擁有了！您已使用 Aspose.PDF for .NET 成功將表格新增至 PDF 文件的頁首。令人驚訝的是，只需幾行程式碼就可以將簡單的 PDF 轉換為具有專業外觀的文件。無論您是在準備報告、發票還是演示文稿，添加一點創意都會讓一切變得不同。 

## 常見問題解答

### 什麼是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員以程式設計方式建立和操作 PDF 文件。

### 我需要許可證才能使用 Aspose.PDF 嗎？
雖然您可以在試用期內免費使用該庫，但長時間使用需要許可證。您可以獲得[臨時執照](https://purchase.aspose.com/temporary-license/)進行評估。

### 我在哪裡可以找到文件？
您可以在以下位置找到全面的文件和範例[Aspose.PDF 文件頁面](https://reference.aspose.com/pdf/net/).

### 如何聯絡支援人員解決技術問題？
您可以透過以下方式尋求支持[Aspose論壇](https://forum.aspose.com/c/pdf/10).

### 我可以在 PDF 的其他部分建立表格嗎？
絕對地！您也可以在頁尾和正文部分建立表格；只需遵循類似的步驟即可。