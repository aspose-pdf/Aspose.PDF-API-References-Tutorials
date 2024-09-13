---
title: 使用 DOM 新增 HTML
linktitle: 使用 DOM 新增 HTML
second_title: Aspose.PDF for .NET API 參考
description: 了解如何在 Aspose.PDF for .NET 中使用 DOM 新增 HTML 內容。
type: docs
weight: 40
url: /zh-hant/net/programming-with-text/add-html-using-dom/
---
本教學將引導您完成在 Aspose.PDF for .NET 中使用 DOM（文件物件模型）新增 HTML 內容的過程。提供的 C# 原始程式碼演示了必要的步驟。

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
```

## 第三步：設定文檔目錄和輸出檔案路徑
在程式碼中，找到顯示以下內容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`以及儲存文檔的目錄的路徑。

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
實例化一個`HtmlFragment`物件並提供所需的 HTML 內容。在提供的程式碼中，HTML 內容被指派給變數`titel`。您可以根據需要修改 HTML 內容。

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

## 第7步：設定保證金訊息
如有必要，請調整 HTML 片段的底部和頂部邊距。在提供的代碼中，底部邊距設定為 10，頂部邊距設定為 200。

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 200;
```

## 步驟8：將HtmlFragment加入頁面
添加`HtmlFragment`物件頁面的段落集合。

```csharp
page.Paragraphs.Add(title);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

## 第9步：儲存PDF文檔
使用以下命令儲存 PDF 文檔`Save`的方法`Document`目的。指定您在步驟 3 中設定的輸出檔案路徑。

```csharp
doc.Save(dataDir);
```

## 第10步：顯示成功訊息
顯示成功訊息以及 PDF 檔案的儲存路徑。

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 新增 HTMLUsing DOM 的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//實例化文檔對象
Document doc = new Document();
//將頁面新增到 PDF 檔案的頁面集合中
Page page = doc.Pages.Add();
//使用 HTML 內容實例化 HtmlFragment
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
//設定下邊距資訊
titel.Margin.Bottom = 10;
//設定上邊距資訊
titel.Margin.Top = 200;
//將 HTML 片段加入到頁面的段落集合中
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
//儲存 PDF 文件
doc.Save(dataDir);
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

## 結論
您已在 Aspose.PDF for .NET 中使用 DOM 成功新增 HTML 內容。現在可以在指定的輸出檔案路徑中找到產生的 PDF 檔案。

### 常見問題解答

#### Q：本教學的目標是什麼？

答：本教學課程旨在提供如何使用 Aspose.PDF for .NET 中的文件物件模型 (DOM) 將 HTML 內容新增至 PDF 文件的逐步指南。它包括 C# 原始程式碼片段，可幫助您理解和實現該流程。

#### Q：本教學需要導入哪些命名空間？

答：在您打算新增 HTML 內容的程式碼檔案中，在檔案開頭匯入以下命名空間：

```csharp
using Aspose.Pdf;
```

#### Q：如何指定文檔目錄和輸出檔案路徑？

 A：在程式碼中找到這一行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

#### Q：如何建立 Document 物件？

 A：在第4步中，實例化一個新的`Document`對象，新增以下程式碼行：

```csharp
Document doc = new Document();
```

#### Q：如何為文件新增頁面？

答：在步驟 5 中，您將使用`Add`的方法`Pages`收藏：

```csharp
Page page = doc.Pages.Add();
```

#### Q：如何使用 DOM 設定 HTML 內容？

答：在步驟 6 中，您將建立一個`HtmlFragment`物件並將您想要的 HTML 內容指派給它。 HTML 內容被指派給變數`titel`:

```csharp
HtmlFragment titel = new HtmlFragment("<fontsize=10><b><i>Table</i></b></fontsize>");
```

#### Q：我可以調整 HTML 內容的邊距嗎？

答：是的，在步驟 7 中，您可以根據需要調整 HTML 片段的下邊距和上邊距：

```csharp
titel.Margin.Bottom = 10;
titel.Margin.Top = 200;
```

#### Q：如何將 HTMLFragment 新增至 PDF 文件中？

答：在步驟 8 中，您將會加入`HtmlFragment`目的 （`titel`到頁面的段落集合：

```csharp
page.Paragraphs.Add(titel);
dataDir = dataDir + "AddHTMLUsingDOM_out.pdf";
```

#### Q：如何保存產生的 PDF 文件？

 A：新增HTML內容並調整邊距後，使用`Save`的方法`Document`儲存 PDF 文件的物件：

```csharp
doc.Save(dataDir);
```

#### Q：有沒有辦法驗證流程是否成功？

答：當然可以，在步驟10中，會顯示成功訊息以及PDF檔案的儲存路徑：

```csharp
Console.WriteLine("\nHTML using DOM added successfully.\nFile saved at " + dataDir);
```

#### Q：本教程的主要內容是什麼？

答：透過學習本教學課程，您已經成功學習如何利用 Aspose.PDF for .NET 中的文件物件模型 (DOM) 將 HTML 內容新增至 PDF 文件中。這些知識使您能夠增強 PDF 生成能力。