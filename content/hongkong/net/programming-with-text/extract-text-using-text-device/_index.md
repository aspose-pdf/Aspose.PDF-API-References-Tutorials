---
title: 使用文本設備提取文本
linktitle: 使用文本設備提取文本
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 中的文字裝置從 PDF 文件中擷取文字。
type: docs
weight: 210
url: /zh-hant/net/programming-with-text/extract-text-using-text-device/
---
本教學將引導您完成使用 Aspose.PDF for .NET 中的文字裝置從 PDF 文件中提取文字的過程。提供的 C# 原始程式碼演示了必要的步驟。

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
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## 第三步：設定文檔目錄
在程式碼中，找到顯示以下內容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`以及儲存文檔的目錄的路徑。

## 步驟 4：開啟 PDF 文檔
使用以下命令開啟現有 PDF 文檔`Document`建構函數並將路徑傳遞給輸入 PDF 檔案。

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## 第 5 步：使用文本設備提取文本
創建一個`StringBuilder`物件來保存提取的文字。遍歷文件的每一頁並使用`TextDevice`從每個頁面中提取文字。

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## 步驟6：保存提取的文本
指定輸出文件路徑並使用以下命令將提取的文字儲存到文字文件`File.WriteAllText`方法。

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### 使用 Aspose.PDF for .NET 使用文字裝置提取文字的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//開啟文件
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//用於保存提取的文字的字串
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		//建立文字設備
		TextDevice textDevice = new TextDevice();
		//設定文字擷取選項 - 設定文字擷取模式（Raw 或 Pure）
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		//轉換特定頁面並將文字儲存到流中
		textDevice.Process(pdfPage, textStream);
		//轉換特定頁面並將文字儲存到流中
		textDevice.Process(pdfDocument.Pages[1], textStream);
		//關閉記憶體流
		textStream.Close();
		//從記憶體流中獲取文本
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
//將提取的文字儲存在文字檔案中
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## 結論
您已使用 Aspose.PDF for .NET 中的文字裝置成功從 PDF 文件中提取文字。提取的文字已儲存到指定的輸出檔案中。

### 常見問題解答

#### Q：本教學的目的是什麼？

答：本教學提供有關使用 Aspose.PDF for .NET 中的文字裝置功能從 PDF 文件中提取文字的指導。隨附的 C# 原始程式碼演示了實現此任務的必要步驟。

#### Q：我應該導入哪些命名空間？

答：在您計劃提取文字的程式碼檔案中，在檔案開頭包含以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### Q：如何指定文檔目錄？

 A：在程式碼中，找出這樣一行：`string dataDir = "YOUR DOCUMENT DIRECTORY";`並替換`"YOUR DOCUMENT DIRECTORY"`與文檔目錄的實際路徑。

#### Q：如何開啟現有的 PDF 文件？

答：在步驟 4 中，您將使用以下命令開啟現有的 PDF 文件：`Document`建構函數並提供輸入 PDF 檔案的路徑。

#### Q：如何使用文字裝置提取文字？

答：第 5 步涉及創建`StringBuilder`物件來保存提取的文字。然後，您將遍歷文件的每一頁並使用`TextDevice`連同`TextExtractionOptions`從每個頁面中提取文字。

#### 問：如何將提取的文字儲存到文件中？

答：在步驟 6 中，您將指定輸出檔案路徑並使用`File.WriteAllText`方法將提取的文字儲存到文字檔案。

#### Q：本教程的主要內容是什麼？

答：透過學習本教學課程，您已經了解如何利用 Aspose.PDF for .NET 中的文字裝置功能從 PDF 文件中擷取文字。提取的文字已儲存到指定的輸出檔案中，使您能夠根據需要操作和利用提取的內容。