---
title: 在 PDF 檔案中設定預設字體
linktitle: 在 PDF 檔案中設定預設字體
second_title: Aspose.PDF for .NET API 參考
description: 透過此逐步指南，了解如何使用 Aspose.PDF for .NET 在 PDF 檔案中設定預設字體。
type: docs
weight: 280
url: /zh-hant/net/programming-with-document/setdefaultfont/
---
如果您在 .NET 中處理 PDF 文檔，則可能會遇到以下問題：PDF 中使用的字體在檢視或列印 PDF 的系統上不可用。這可能會導致文字顯示不正確或根本不顯示。 Aspose.PDF for .NET 可讓您為文件設定預設字體，從而提供了此問題的解決方案。在此範例中，如何使用 Aspose.PDF for .NET 設定預設字體。

## 第一步：設定文檔目錄路徑

我們需要設定PDF文件所在目錄的路徑。我們將該路徑儲存在名為「dataDir」的變數中。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入 PDF 文檔

我們首先載入缺少字體的現有 PDF 文件。在此範例中，我們假設 PDF 文件位於由`dataDir`多變的。

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    //代碼放在這裡
}
```

## 第三步：設定預設字體

接下來，我們將使用以下命令設定 PDF 文件的預設字體`PdfSaveOptions`班級。在此範例中，我們將預設字體設定為“Arial”。

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## 步驟 4：儲存更新後的文檔

最後，我們將更新的文檔儲存到新文件中。在此範例中，我們將更新的文件儲存到與輸入檔案位於同一目錄中的名為「output_out.pdf」的檔案中。

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### 使用 Aspose.PDF for .NET 設定預設字體的範例原始碼

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//載入缺少字體的現有 PDF 文檔
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	//指定預設字體名稱
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```

## 結論

使用 Aspose.PDF for .NET 在 PDF 文件中設定預設字體是一種簡單且有效的方法，可確保文字正確顯示，即使原始字體不可用。透過遵循逐步指南並使用提供的 C# 原始程式碼，開發人員可以輕鬆設定預設字體並建立 PDF，從而在不同環境中提供一致且可靠的檢視體驗。當在可能安裝了不同字體集的各種系統上檢視或列印 PDF 時，此功能特別有用。

### PDF 檔案中設定預設字體的常見問題解答

#### Q：為什麼在 PDF 文件中設定預設字體很重要？

答：在 PDF 文件中設定預設字體非常重要，因為即使在檢視或列印 PDF 的系統上沒有原始字體，它也能確保文字正確顯示。它有助於防止文字遺失或亂碼等問題，確保一致且可靠的觀看體驗。

#### Q：我可以使用 Aspose.PDF for .NET 選擇任何字體作為預設字體嗎？

答：是的，您可以使用 Aspose.PDF for .NET 選擇系統上可用的任何字體作為預設字體。只需在中指定字型名稱即可`DefaultFontName`的財產`PdfSaveOptions`班級。

#### Q：如果系統上沒有指定的預設字體，會發生什麼情況？

答：如果系統上沒有指定的預設字體，PDF 檢視器將使用後備字體來顯示文字。建議選擇常用字體，如 Arial 或 Times New Roman，以確保不同系統之間的相容性。