---
title: 設定單選按鈕標題
linktitle: 設定單選按鈕標題
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 設定 PDF 表單中單選按鈕的標題。
type: docs
weight: 280
url: /zh-hant/net/programming-with-forms/set-radio-button-caption/
---
在本指南中，我們將逐步說明如何使用 .NET 的 Aspose.PDF 庫來定義 PDF 表單中單選按鈕的標題。我們將向您展示如何存取單選按鈕欄位、建立新的單選按鈕選項以及自訂按鈕標題。

## 步驟1：配置文檔目錄

第一步是配置您要處理的 PDF 表單所在的文件目錄。您可以使用`dataDir`變數來指定目錄路徑。

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

一定要更換`"YOUR DOCUMENTS DIRECTORY"`與文檔目錄的實際路徑。

## 第 2 步：載入來源 PDF 表單

在此步驟中，我們將使用以下命令載入來源 PDF 表單`Aspose.Pdf.Facades.Form`Aspose.PDF 類別。

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

確保包含表單的 PDF 檔案存在於指定的文件目錄中。

## 步驟 3：編輯單選按鈕標題

我們將循環遍歷表單欄位名稱並蒐索單選按鈕欄位。如果找到符合的字段，我們將建立一個帶有自訂標題的新單選按鈕選項，並將其新增至現有欄位。

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
//建立一個 TextParagraph 對象
TextParagraph par = new TextParagraph();
//設定段落位置
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
//指定自動換行模式
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
//將新的 TextFragment 加入到段落中
par.AppendLine(updatedFragment);
//使用 TextBuilder 新增 TextParagraph
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

根據需要自訂標題單選按鈕和其他設定。

## 第 4 步：儲存產生的 PDF

現在我們已經完成了單選按鈕標題的修改，我們可以使用以下命令保存生成的 PDF：`Save`的方法`Document`班級。

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

請務必指定產生的 PDF 的完整路徑和檔案名稱。

### 使用 Aspose.PDF for .NET 設定單選按鈕標題的範例原始碼 
```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//載入來源 PDF 表單
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		//建立 TextParagraph 對象
		TextParagraph par = new TextParagraph();
		//設定段落位置
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		//指定自動換行模式
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		//新增新的 TextFragment 到段落
		par.AppendLine(updatedFragment);
		//使用 TextBuilder 新增 TextParagraph
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## 結論

在本指南中，我們學習如何使用 .NET 的 Aspose.PDF 庫來設定 PDF 表單中單選按鈕的標題。透過執行所描述的步驟，您可以自訂單選按鈕選項並根據需要變更標題。請隨意進一步探索 Aspose.PDF for .NET 的功能，以擴充處理 PDF 檔案的可能性。

### 常見問題解答

#### Q：我可以使用 Aspose.PDF for .NET 為 PDF 表單中的單選按鈕設定標題嗎？

答：是的，您可以使用 Aspose.PDF for .NET 為 PDF 表單中的單選按鈕設定標題。提供的範例原始程式碼示範如何存取單選按鈕欄位、建立帶有自訂標題的新單選按鈕選項以及更新現有欄位。

#### Q：如何自訂單選按鈕標題的外觀，例如字體大小和顏色？

答：您可以透過調整單選按鈕標題的屬性來自訂單選按鈕標題的外觀。`TextFragment`用於標題。例如，您可以設定字體、字體大小、顏色、行距和其他文字格式選項。

#### Q：是否可以將具有不同標題的多個單選按鈕選項新增至單一單選按鈕組？

答：是的，您可以將具有不同標題的多個單選按鈕選項新增至單一單選按鈕組。每個選項都代表一個不同的選擇，使用者只能從該群組中選擇一個選項。

#### Q：我可以使用 Aspose.PDF for .NET 修改 PDF 文件中的其他表單欄位嗎？

答：是的，Aspose.PDF for .NET 提供了一套全面的功能來操作 PDF 文件中的各種表單字段，例如文字字段、複選框、下拉列表等。您可以使用該庫來設定值、修改外觀以及為表單欄位新增互動性。

#### Q：Aspose.PDF for .NET 是否支援處理從其他來源（例如掃描文件）產生的 PDF？

答：是的，Aspose.PDF for .NET 支援處理從各種來源產生的 PDF，包括掃描文件。該庫提供 OCR（光學字元辨識）功能，可從掃描的 PDF 中提取文字並以程式設計方式操作內容。