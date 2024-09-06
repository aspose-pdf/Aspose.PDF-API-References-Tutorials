---
title: 使用 DOM 和 PDF 覆蓋添加 HTML
linktitle: 使用 DOM 添加 HTML 並覆蓋
second_title: Aspose.PDF for .NET API 參考
description: 了解如何在 Aspose.PDF for .NET 中使用 DOM 和 PDF 覆寫新增 HTML 內容。
type: docs
weight: 50
url: /zh-hant/net/programming-with-text/add-html-using-dom-and-overwrite/
---
本教學將引導您完成在 Aspose.PDF for .NET 中使用 DOM（文件物件模型）新增 HTML 內容的過程。此外，您還將了解如何覆蓋 HTML 內容的樣式。提供的 C# 原始程式碼演示了必要的步驟。

## 要求
在開始之前，請確保您具備以下條件：

- Visual Studio 或電腦上安裝的任何其他 C# 編譯器。
- Aspose.PDF for .NET 函式庫。您可以從 Aspose 官方網站下載它或使用 NuGet 等套件管理器來安裝它。

## 第 1 步：設定項目
1. 在您首選的開發環境中建立一個新的 C# 專案。
2. 新增對 Aspose.PDF for .NET 函式庫的參考。

## 步驟2：導入所需的命名空間
在要新增 HTML 內容的程式碼檔案中，在檔案頂部新增以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第三步：設定文檔目錄和輸出檔案路徑
在程式碼中，找到顯示以下內容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`以及儲存文檔的目錄的路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步驟 4：建立一個新的 Document 對象
實例化一個新的`Document`對象，新增以下程式碼行：

```csharp
Document doc = new Document();
```

## 步驟 5：新增頁面
使用以下命令將新頁面新增至文件中`Add`的方法`Pages`收藏。在提供的程式碼中，新頁面被分配給變數`page`.

```csharp
Page page = doc.Pages.Add();
```

## 第 6 步：使用 HTML 內容建立 HtmlFragment
實例化一個`HtmlFragment`物件並提供所需的 HTML 內容。在提供的程式碼中，HTML 內容被指派給變數`title`。您可以根據需要修改 HTML 內容。

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## 步驟 7：覆蓋 HTML 內容的樣式
若要覆寫 HTML 內容的樣式，您可以修改`TextState`的屬性`HtmlFragment`目的。在提供的程式碼中，字體系列更改為“Arial”，字體大小設定為 20。

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## 步驟8：設定保證金訊息
如有必要，請調整 HTML 片段的底部和頂部邊距。在提供的代碼中，底部邊距設定為 10，頂部邊距設定為 400。

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## 第9步：將HtmlFragment加入頁面
添加`HtmlFragment`物件頁面的段落集合。

```csharp
page.Paragraphs.Add(title);
```

## 第10步：儲存PDF文檔
使用以下命令儲存 PDF 文檔`Save`的方法`Document`目的。指定您在步驟 3 中設定的輸出檔案路徑。

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### 使用 DOM 新增 HTML 並使用 Aspose.PDF for .NET 覆寫的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//實例化文檔對象
Document doc = new Document();
//將頁面新增到 PDF 檔案的頁面集合中
Page page = doc.Pages.Add();
//使用 HTML 內容實例化 HtmlFragment
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//“Verdana”的字體系列將重設為“Arial”
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
//設定下邊距資訊
title.Margin.Bottom = 10;
//設定上邊距資訊
title.Margin.Top = 400;
//將 HTML 片段加入到頁面的段落集合中
page.Paragraphs.Add(title);
//儲存 PDF 文件
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);
```

## 結論
您已在 Aspose.PDF for .NET 中使用 DOM 成功新增 HTML 內容並覆寫 HTML 內容的樣式。現在可以在指定的輸出檔案路徑中找到產生的 PDF 檔案。

### 常見問題解答

#### Q：本教程的重點是什麼？

答：本教學課程旨在引導您完成使用 Aspose.PDF for .NET 中的文件物件模型 (DOM) 將 HTML 內容新增至 PDF 文件的過程。此外，您還將學習如何覆寫 HTML 內容的樣式，從而自訂其外觀。本教學提供了 C# 原始碼片段來示範所需的步驟。

#### Q：本教學需要導入哪些命名空間？

答：在要新增 HTML 內容的程式碼檔案中，在檔案開頭匯入以下命名空間：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q：如何指定文檔目錄和輸出檔案路徑？

 A：在程式碼中，找到行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

#### Q：如何建立 Document 物件？

答：在步驟 4 中，您將實例化一個新的`Document`使用以下程式碼行物件：

```csharp
Document doc = new Document();
```

#### Q：如何為文件新增頁面？

答：在步驟 5 中，您將使用`Add`的方法`Pages`收藏：

```csharp
Page page = doc.Pages.Add();
```

#### Q：如何使用 DOM 設定 HTML 內容？

答：在步驟 6 中，您將建立一個`HtmlFragment`物件並將您想要的 HTML 內容指派給它。 HTML 內容被指派給變數`title`：

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### Q：如何覆蓋 HTML 內容的樣式？

答：在步驟 7 中，您將透過修改`TextState`的屬性`HtmlFragment`目的。例如，您可以將字體系列變更為“Arial”並將字體大小設為 20：

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### Q：我可以調整 HTML 內容的邊距嗎？

答：是的，在步驟 8 中，您可以根據需要調整 HTML 片段的下邊距和上邊距：

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### Q：如何將 HtmlFragment 加入 PDF 文件中？

答：在步驟 9 中，您將會加入`HtmlFragment`目的 （`title`到頁面的段落集合：

```csharp
page.Paragraphs.Add(title);
```

#### Q：如何保存產生的 PDF 文件？

A：新增HTML內容並自訂其樣式後，使用`Save`的方法`Document`儲存 PDF 文件的物件：

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### Q：本教程的主要內容是什麼？

答：透過學習本教學課程，您已經成功學習如何使用 Aspose.PDF for .NET 中的文件物件模型 (DOM) 合併 HTML 內容。此外，您還能夠覆蓋樣式以自訂生成的 PDF 文件中 HTML 內容的外觀。