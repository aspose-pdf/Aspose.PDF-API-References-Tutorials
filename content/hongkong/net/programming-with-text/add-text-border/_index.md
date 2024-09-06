---
title: 在 PDF 檔案中新增文字邊框
linktitle: 在 PDF 檔案中新增文字邊框
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中新增文字邊框。
type: docs
weight: 70
url: /zh-hant/net/programming-with-text/add-text-border/
---
本教學將引導您完成使用 Aspose.PDF for .NET 在 PDF 檔案中新增文字邊框的流程。提供的 C# 原始程式碼演示了必要的步驟。

## 要求
在開始之前，請確保您具備以下條件：

- Visual Studio 或電腦上安裝的任何其他 C# 編譯器。
- Aspose.PDF for .NET 函式庫。您可以從 Aspose 官方網站下載它或使用 NuGet 等套件管理器來安裝它。

## 第 1 步：設定項目
1. 在您首選的開發環境中建立一個新的 C# 專案。
2. 新增對 Aspose.PDF for .NET 函式庫的參考。

## 步驟2：導入所需的命名空間
在要新增文字邊框的程式碼檔案中，在檔案頂部新增以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第三步：設定文檔目錄
在程式碼中，找到顯示以下內容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`以及儲存文檔的目錄的路徑。

## 步驟 4：建立一個新的 Document 對象
實例化一個新的`Document`對象，新增以下程式碼行：

```csharp
Document pdfDocument = new Document();
```

## 步驟 5：新增頁面
使用以下命令將新頁面新增至文件中`Add`的方法`Pages`收藏。在提供的程式碼中，新頁面被分配給變數`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## 第 6 步：建立一個 TextFragment
創建一個`TextFragment`物件並提供所需的文字。使用設定文字片段的位置`Position`財產。在提供的代碼中，文字設定為「主文本」並位於頁面上的 (100, 600) 處。

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## 第 7 步：設定文字屬性
自訂文字屬性，如字體大小、字體類型、背景顏色、前景色等。

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## 第 8 步：啟用文字邊框
若要啟用文字邊框，請設定`DrawTextRectangleBorder`文字片段的屬性`TextState`到`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## 第9步：將TextFragment新增至頁面
使用`TextBuilder`類別來添加`TextFragment`反對該頁面。

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## 第10步：儲存PDF文檔
使用以下命令儲存 PDF 文檔`Save`的方法`Document`目的。指定您在步驟 3 中設定的輸出檔案路徑。

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### 使用 Aspose.PDF for .NET 新增文字邊框的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//建立新文檔對象
Document pdfDocument = new Document();
//取得特定頁面
Page pdfPage = (Page)pdfDocument.Pages.Add();
//建立文字片段
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
//設定文字屬性
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
//設定 StrokingColor 屬性以在文字矩形周圍繪製邊框（描邊）
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
//將 DrawTextRectangleBorder 屬性值設為 true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
//儲存文件
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## 結論
您已使用 Aspose.PDF for .NET 成功地為 PDF 文件新增文字邊框。現在可以在指定的輸出檔案路徑中找到產生的 PDF 檔案。

### 常見問題解答

#### Q：本教程的主要重點是什麼？

答：本教學將引導您完成使用 Aspose.PDF for .NET 程式庫為 PDF 檔案新增文字邊框的流程。提供的 C# 原始程式碼演示了實現此目的的必要步驟。

#### Q：本教學需要導入哪些命名空間？

A：在要新增文字邊框的程式碼檔案中，在檔案開頭匯入以下命名空間：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q：如何指定文檔目錄？

 A：在程式碼中，找到行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

#### Q：如何建立 Document 物件？

答：在步驟 4 中，您將實例化一個新的`Document`使用以下程式碼行物件：

```csharp
Document pdfDocument = new Document();
```

#### Q：如何為文件新增頁面？

答：在步驟 5 中，您將使用`Add`的方法`Pages`收藏：

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### Q：如何建立 TextFragment 並設定其位置？

答：在步驟 6 中，您將建立一個`TextFragment`物件並使用以下命令設定其在頁面上的位置`Position`財產：

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### Q：如何自訂文字屬性，包括文字邊框？

答：在步驟 7 中，您將自訂各種文字屬性，例如字體大小、字體類型、背景顏色、前景色和文字邊框：

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### Q：如何將 TextFragment 新增至 PDF 文件中？

答：在第 9 步驟中，您將使用`TextBuilder`類別來添加`TextFragment`頁面對象：

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### Q：如何保存產生的 PDF 文件？

 A：新增有邊框的文字後，使用`Save`的方法`Document`儲存 PDF 文件的物件：

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### Q：本教程的主要內容是什麼？

答：透過學習本教學課程，您已經成功學習如何使用 Aspose.PDF for .NET 新增文字邊框來增強 PDF 文件。這對於強調 PDF 文件中的特定文字內容特別有用。