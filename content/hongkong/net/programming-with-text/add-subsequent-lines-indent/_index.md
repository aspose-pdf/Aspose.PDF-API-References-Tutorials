---
title: 在 PDF 文件中新增後續行縮排
linktitle: 在 PDF 文件中新增後續行縮排
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中的文字中新增後續行縮排。
type: docs
weight: 60
url: /zh-hant/net/programming-with-text/add-subsequent-lines-indent/
---
本教學將引導您完成使用 Aspose.PDF for .NET 在 PDF 檔案中的文字中新增後續行縮排的過程。提供的 C# 原始程式碼演示了必要的步驟。

## 要求
在開始之前，請確保您具備以下條件：

- Visual Studio 或電腦上安裝的任何其他 C# 編譯器。
- Aspose.PDF for .NET 函式庫。您可以從 Aspose 官方網站下載它或使用 NuGet 等套件管理器來安裝它。

## 第 1 步：設定項目
1. 在您首選的開發環境中建立一個新的 C# 專案。
2. 新增對 Aspose.PDF for .NET 函式庫的參考。

## 步驟2：導入所需的命名空間
在要新增後續行縮排的程式碼檔案中，在檔案頂部新增以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第三步：設定文檔目錄
在程式碼中，找到顯示以下內容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`以及儲存文檔的目錄的路徑。

## 步驟 4：建立一個新的 Document 對象
實例化一個新的`Document`對象，新增以下程式碼行：

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## 步驟 5：新增頁面
使用以下命令將新頁面新增至文件中`Add`的方法`Pages`收藏。在提供的程式碼中，新頁面被分配給變數`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## 步驟 6：建立一個有後續行縮排的 TextFragment
實例化一個`TextFragment`物件並提供所需的文字。在提供的程式碼中，文字被分配給變數`text`。然後，初始化`TextFormattingOptions`為`TextFragment`並指定`SubsequentLinesIndent`價值。

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## 步驟7：將TextFragment新增至頁面
添加`TextFragment`物件頁面的段落集合。

```csharp
page.Paragraphs.Add(text);
```

## 步驟 8：對其他行重複步驟 6 和 7
若要新增具有相同縮排的後續行，請對每行重複步驟 6 和 7。根據需要更新文字內容。

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## 第9步：儲存PDF文檔
使用以下命令儲存 PDF 文檔`Save`的方法`Document`目的。指定輸出檔案路徑。

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### 使用 Aspose.PDF for .NET 新增後續行縮排的範例原始程式碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//建立新文檔對象
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
//為文字片段初始化 TextFormattingOptions 並指定 SubsequentLinesIndent 值
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## 結論
您已使用 Aspose.PDF for .NET 成功地在文字中新增了後續行縮排。現在可以在指定的輸出檔案路徑中找到產生的 PDF 檔案。

### 常見問題解答

#### Q：本教程的重點是什麼？

答：本教學提供瞭如何使用 Aspose.PDF for .NET 程式庫為 PDF 檔案中的文字新增後續行縮排的全面指南。它包括 C# 原始程式碼範例來說明實現此目的所需的步驟。

#### Q：本教學需要導入哪些命名空間？

答：在要新增後續行縮排的程式碼檔案中，在檔案開頭匯入以下命名空間：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q：如何指定文檔目錄？

 A：在程式碼中，找到行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

#### Q：如何建立 Document 物件？

答：在步驟 4 中，您將實例化一個新的`Document`使用以下程式碼行物件：

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### Q：如何為文件新增頁面？

答：在步驟 5 中，您將使用`Add`的方法`Pages`收藏：

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### Q：如何為文字新增後續行縮排？

答：在步驟 6 中，您將建立一個`TextFragment`物件並為其分配所需的文字。然後，您將初始化`TextFormattingOptions`為`TextFragment`並指定`SubsequentLinesIndent`價值：

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### Q：如何將 TextFragment 新增至 PDF 文件中？

答：在步驟 7 中，您將會加入`TextFragment`目的 （`text`到頁面的段落集合：

```csharp
page.Paragraphs.Add(text);
```

#### Q：我可以對其他線路重複此過程嗎？

答：是的，在步驟 8 中，您可以透過建立新的行來對具有相同縮排的其他行重複此過程`TextFragment`物件並將它們新增至頁面的段落集合中。

#### Q：如何保存產生的 PDF 文件？

 A：新增帶有後續行縮排的文字後，使用`Save`的方法`Document`儲存 PDF 文件的物件：

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### Q：本教程的主要內容是什麼？

答：透過學習本教學課程，您已經成功學習如何使用 Aspose.PDF for .NET 新增後續行縮排來增強 PDF 文件中文字的可讀性。此技術可用於各種類型的文件和報告。