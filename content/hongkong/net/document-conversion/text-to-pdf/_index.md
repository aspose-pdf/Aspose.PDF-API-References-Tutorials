---
title: 文字轉PDF
linktitle: 文字轉PDF
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 將文字檔案簡單且有效率地轉換為 PDF。
type: docs
weight: 300
url: /zh-hant/net/document-conversion/text-to-pdf/
---
本教學將引導您完成使用 Aspose.PDF for .NET 將文字檔案轉換為 PDF 檔案的步驟。 Aspose.PDF 提供了一個簡單而有效的解決方案，用於將純文字轉換為 PDF，同時保留文字格式和簡報。請按照以下步驟執行此轉換。

## 先決條件
在開始之前，請確保滿足以下先決條件：

- C# 程式語言的基礎知識。
- 您的系統上安裝了適用於 .NET 的 Aspose.PDF 庫。
- 開發環境，例如 Visual Studio。

## 第一步：讀取文字文件
第一步是使用以下命令讀取文字檔案的內容`StreamReader`班級。使用以下程式碼：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//讀取文字文件
TextReader tr = new StreamReader(dataDir + "log.txt");
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`與文字檔案所在的實際目錄。

## 第 2 步：建立 PDF 文檔
第二步是創建一個`Document`代表最終 PDF 文件的對象。使用以下程式碼：

```csharp
//建立文檔對象
Document doc = new Document();
```

## 步驟 3：為文件新增文本
第三步，將閱讀的文字加入PDF文件的頁面中。使用以下程式碼：

```csharp
//新增頁面
Page page = doc.Pages.Add();

//建立一個 TextFragment 物件並將讀取的文字作為參數傳遞
TextFragment text = new TextFragment(tr.ReadToEnd());

//將文字段落新增至頁面
page.Paragraphs.Add(text);
```

## 步驟 4：儲存 PDF 文件
最後，透過指定所需的路徑和檔案名稱來儲存產生的 PDF 檔案。使用以下程式碼：

```csharp
//儲存生成的 PDF 文件
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

請務必為產生的 PDF 檔案指定所需的路徑和檔案名稱。

### 使用 Aspose.PDF for .NET 的文字轉 PDF 範例原始碼

```csharp
try
{
	
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//讀取來源文字文件
	TextReader tr = new StreamReader(dataDir + "log.txt");

	//透過呼叫其空建構函數來實例化 Document 對象
	Document doc = new Document();

	//在文件的頁面集合中新增頁面
	Page page = doc.Pages.Add();

	//建立 TextFragmet 的實例並將文字從 reader 物件傳遞到其建構函式作為參數
	TextFragment text = new TextFragment(tr.ReadToEnd());
	//Text.TextState.Font = FontRepository.FindFont("Arial Unicode MS");

	//在段落集合中新增新的文字段落並傳遞 TextFragment 對象
	page.Paragraphs.Add(text);

	//儲存生成的 PDF 文件
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論
在本教學中，我們學習如何使用 Aspose.PDF for .NET 將文字檔案轉換為 PDF 檔案。按照上面給出的步驟，您可以輕鬆地執行此轉換。使用此方法將文字檔案轉換為 PDF，並享受 Aspose.PDF 的靈活性和品質。

### 常見問題解答

#### Q：什麼是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一個功能強大的程式庫，可讓開發人員在 C# 應用程式中處理 PDF 文件。它提供各種功能，包括將純文字轉換為 PDF。

#### Q：為什麼我要將文字檔案轉換為 PDF？

答：將文字檔案轉換為 PDF 格式可以更好地管理、共用和分發文件。 PDF 檔案在不同裝置和作業系統上提供一致的格式。

#### Q：如何使用 Aspose.PDF for .NET 載入文字檔案並將其轉換為 PDF？

答：要載入文字文件，您可以使用`StreamReader`類別來讀取文件的內容。然後，創建一個`Document`代表 PDF 文檔的對象。新增一個新頁面和一個`TextFragment`包含文字檔案中的文字。最後，使用以下命令儲存生成的 PDF`Save`的方法`Document`目的。

#### Q：我可以自訂 PDF 中文字的外觀嗎？

答：是的，Aspose.PDF for .NET 提供了各種選項來自訂產生的 PDF 中文字的外觀，例如字體樣式、大小、顏色和對齊方式。

#### Q：生成的 PDF 中是否保留文字格式？

答：是的，Aspose.PDF for .NET 在文字到 PDF 轉換期間保留文字格式和佈局，確保原始內容的準確表示。