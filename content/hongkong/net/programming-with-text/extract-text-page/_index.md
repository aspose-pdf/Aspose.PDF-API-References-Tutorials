---
title: 提取 PDF 文件中的文字頁面
linktitle: 提取 PDF 文件中的文字頁面
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 從 PDF 文件中的特定頁面提取文字。
type: docs
weight: 200
url: /zh-hant/net/programming-with-text/extract-text-page/
---
本教學將引導您完成使用 Aspose.PDF for .NET 從 PDF 文件中的特定頁面提取文字的過程。提供的 C# 原始程式碼演示了必要的步驟。

## 要求
在開始之前，請確保您具備以下條件：

- Visual Studio 或電腦上安裝的任何其他 C# 編譯器。
- Aspose.PDF for .NET 函式庫。您可以從 Aspose 官方網站下載它或使用 NuGet 等套件管理器來安裝它。

## 第 1 步：設定項目
1. 在您首選的開發環境中建立一個新的 C# 專案。
2. 新增對 Aspose.PDF for .NET 函式庫的參考。

## 步驟2：導入所需的命名空間
在要擷取文字的程式碼檔案中，在檔案頂部加入以下 using 指令：

```csharp
using Aspose.Pdf;
using System.IO;
```

## 第三步：設定文檔目錄
在程式碼中，找到顯示以下內容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`以及儲存文檔的目錄的路徑。

## 步驟 4：開啟 PDF 文檔
使用以下命令開啟現有 PDF 文檔`Document`建構函數並將路徑傳遞給輸入 PDF 檔案。

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## 步驟 5：從特定頁面提取文本
創建一個`TextAbsorber`物件從文件中提取文字。透過訪問它來接受所需頁面的吸收器`Pages`的集合`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## 步驟6：獲取提取的文本
訪問提取的文本`TextAbsorber`目的。

```csharp
string extractedText = textAbsorber.Text;
```

## 步驟7：保存提取的文本
創建一個`TextWriter`並開啟要儲存提取文字的檔案。將提取的文字寫入檔案並關閉串流。

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### 使用 Aspose.PDF for .NET 擷取文字頁面的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
//建立 TextAbsorber 物件來提取文本
TextAbsorber textAbsorber = new TextAbsorber();
//接受特定頁面的吸收器
pdfDocument.Pages[1].Accept(textAbsorber);
//獲取提取的文本
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
//建立編寫器並開啟文件
TextWriter tw = new StreamWriter(dataDir);
//將一行文字寫入文件
tw.WriteLine(extractedText);
//關閉流
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## 結論
您已使用 Aspose.PDF for .NET 從 PDF 文件的特定頁面成功提取文字。提取的文字已儲存到指定的輸出檔案中。

### 常見問題解答

#### Q：本教學的目的是什麼？

答：本教學將引導您完成使用 Aspose.PDF for .NET 從 PDF 檔案中的特定頁面擷取文字的過程。隨附的 C# 原始程式碼演示了實現此任務所需的步驟。

#### Q：我應該導入哪些命名空間？

答：在您計劃提取文字的程式碼檔案中，在檔案開頭包含以下 using 指令：

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Q：如何指定文檔目錄？

 A：在程式碼中，找出這樣一行：`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

#### Q：如何開啟現有的 PDF 文件？

答：在步驟 4 中，您將使用以下命令開啟現有的 PDF 文件：`Document`建構函數並提供輸入 PDF 檔案的路徑。

#### Q：如何從特定頁面提取文字？

答：第 5 步涉及創建`TextAbsorber`物件從 PDF 文件中提取文字。然後，您將透過造訪所需頁面來接受吸收器`Pages`的集合`pdfDocument`.

#### Q：如何存取提取的文字？

答：第 6 步將引導您訪問從`TextAbsorber`目的。

#### 問：如何將提取的文字儲存到文件中？

答：在步驟 7 中，您將建立一個`TextWriter`，開啟要儲存擷取的文字的文件，將擷取的文字寫入該文件，然後關閉串流。

#### Q：本教程的主要內容是什麼？

答：透過學習本教學課程，您已經了解如何使用 Aspose.PDF for .NET 從 PDF 文件的特定頁面中提取文字。提取的文字已儲存到指定的輸出檔案中，使您能夠定位和分析特定頁面的文字內容。