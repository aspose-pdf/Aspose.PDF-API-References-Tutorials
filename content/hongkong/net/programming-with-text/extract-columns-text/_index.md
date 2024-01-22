---
title: 提取 PDF 文件中的列文本
linktitle: 提取 PDF 文件中的列文本
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 擷取 PDF 檔案中的列文字。
type: docs
weight: 150
url: /zh-hant/net/programming-with-text/extract-columns-text/
---
本教學將引導您完成使用 Aspose.PDF for .NET 擷取 PDF 檔案中的列文字的流程。提供的 C# 原始程式碼演示了必要的步驟。

## 要求
在開始之前，請確保您具備以下條件：

- Visual Studio 或電腦上安裝的任何其他 C# 編譯器。
- Aspose.PDF for .NET 函式庫。您可以從 Aspose 官方網站下載它或使用 NuGet 等套件管理器來安裝它。

## 第 1 步：設定項目
1. 在您首選的開發環境中建立一個新的 C# 專案。
2. 新增對 Aspose.PDF for .NET 函式庫的參考。

## 步驟2：導入所需的命名空間
在要提取列文字的程式碼檔案中，在檔案頂部新增以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## 第三步：設定文檔目錄
在程式碼中，找到顯示以下內容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`以及儲存文檔的目錄的路徑。

## 步驟 4：開啟 PDF 文檔
使用以下命令開啟現有 PDF 文檔`Document`建構函數並將路徑傳遞給輸入 PDF 檔案。

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## 步驟5：調整字體大小
將文字片段的字體大小減小 0.7 倍，以增強可讀性並更好地表示柱狀文字。

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## 步驟 6：從列中提取文本
將修改後的 PDF 文件儲存到記憶體流並將其重新載入為新文件。然後，使用`TextAbsorber`類別從列中提取文字。

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## 步驟7：保存提取的文本
將提取的文字儲存到指定輸出檔案路徑的文字檔案中。

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 擷取列文字的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	//需要縮小字體大小至少 70%
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## 結論
您已使用 Aspose.PDF for .NET 成功地從 PDF 文件中提取了列文字。提取的文字已儲存到指定的輸出檔案中。

### 常見問題解答

#### Q：本教學的目的是什麼？

答：本教學提供了使用 Aspose.PDF for .NET 從 PDF 檔案中提取文字列的逐步指南。隨附的 C# 原始程式碼提供了所需流程的實際演示。

#### Q：我應該導入哪些命名空間？

答：在要擷取文字列的程式碼檔案中，在檔案開頭包含以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### Q：如何指定文檔目錄？

答：找到該線`string dataDir = "YOUR DOCUMENT DIRECTORY";`在代碼中並替換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

#### Q：如何開啟現有的 PDF 文件？

答：在步驟 4 中，您將使用以下命令開啟現有的 PDF 文件：`Document`建構函數並提供輸入 PDF 檔案的路徑。

#### Q：為什麼要調整字體大小？

答：第 5 步驟涉及將文字片段的字體大小減少 0.7 倍。此調整增強了可讀性並更準確地表示柱狀文字。

#### Q：如何從列中提取文字？

答：第 6 步包括將修改後的 PDF 文檔儲存到記憶體流，將其重新載入為新文檔，然後使用`TextAbsorber`類別從列中提取文字。

#### Q：保存擷取的文字的目的是什麼？

答：在步驟 7 中，您會將擷取的文字儲存到指定輸出檔案路徑的文字檔案中。

#### Q：為什麼提取前要減小字體大小？

答：減小字體大小有助於確保提取的文字在列內正確對齊，從而更準確地表示原始佈局。

#### Q：本教程的主要內容是什麼？

答：透過學習本教學課程，您已經獲得了使用 Aspose.PDF for .NET 從 PDF 文件中提取文字列所需的知識和技能。產生的文字已儲存到指定的輸出檔案中。