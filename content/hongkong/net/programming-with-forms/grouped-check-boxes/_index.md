---
title: PDF 文件中的分組複選框
linktitle: PDF 文件中的分組複選框
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 在 PDF 文件中輕鬆建立分組複選框。
type: docs
weight: 170
url: /zh-hant/net/programming-with-forms/grouped-check-boxes/
---
在本教學中，我們將向您展示如何使用 Aspose.PDF for .NET 在 PDF 文件中建立分組複選框。我們將逐步解釋 C# 原始程式碼，以引導您完成此過程。

## 第 1 步：準備

確保您已匯入必要的庫並設定文件目錄的路徑：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：實例化文檔對象

實例化一個 Document 物件：

```csharp
Document pdfDocument = new Document();
```

## 步驟 3：將頁面新增至 PDF 文檔

在 PDF 文件中新增頁面：

```csharp
Page page = pdfDocument.Pages.Add();
```

## 第 4 步：實例化 RadioButtonField 對象

使用頁碼作為參數實例化 RadioButtonField 物件：

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## 第 5 步：新增單選按鈕選項

使用 RadioButtonOptionField 物件新增單選按鈕選項並使用 Rectangle 物件指定其位置：

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## 第 6 步：自訂單選按鈕選項

透過設定單選按鈕選項的樣式、邊框和外觀來自訂單選按鈕選項：

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## 第 7 步：將單選按鈕新增至表單中

將單選按鈕新增至文件表單物件：

```csharp
pdfDocument.Form.Add(radio);
```

## 步驟 8：儲存文檔

儲存 PDF 文件：

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 的分組複選框的範例原始程式碼 
```csharp
try
{
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//實例化文檔對象
	Document pdfDocument = new Document();
	//將頁面新增至 PDF 文件
	Page page = pdfDocument.Pages.Add();
	//以頁碼作為參數實例化 RadioButtonField 對象
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	//新增第一個單選按鈕選項，並使用 Rectangle 物件指定其原點
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	//新增單選按鈕以形成 Document 物件的對象
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	//儲存 PDF 文件
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 在 PDF 文件中建立分組複選框。透過執行這些步驟，您可以輕鬆新增自訂單選按鈕選項，並使用 Aspose.PDF 將它們捆綁到 PDF 文件中。

### 常見問題解答

#### Q：PDF 文件中的分組複選框是什麼？

答：PDF 文件中的分組複選框是指分組在一起的一組單選按鈕選項。單選按鈕允許使用者從一組互斥的選項中僅選擇一個選項。當選擇單選按鈕時，同一組中的其他單選按鈕將自動取消選擇。當您想要向使用者提供多個選項但將他們的選擇限制為一個選項時，這種分組行為非常有用。

#### Q：我可以在 Aspose.PDF for .NET 中自訂分組複選框的外觀嗎？

答：是的，您可以在 Aspose.PDF for .NET 中自訂分組複選框的外觀。 API 提供了各種選項來設定單選按鈕選項的樣式、邊框和外觀。您可以定義每個選項的位置，在不同的框樣式（例如，方形、圓形、十字形）之間進行選擇，並調整邊框屬性以獲得所需的視覺表示。

#### Q：如何將分組複選框新增至 PDF 文件的特定頁面？

答：要將分組複選框新增至 PDF 文件中的特定頁面，您需要實例化一個`RadioButtonField`以所需頁碼作為參數的物件。然後，創建`RadioButtonOptionField`代表每個單選按鈕選項的物件並使用`Rectangle`目的。最後，將這些選項新增至`RadioButtonField`並在添加之前根據需要自訂其外觀`RadioButtonField`到文件表格。

#### Q：我可以在單一 PDF 文件中新增多組複選框嗎？

答：是的，您可以將多組複選框新增至單一 PDF 文件中。每個組別都應該有獨特的`RadioButtonField`對象，以及`RadioButtonOptionField`每個群組中的物件應共享相同的頁面和其選項的唯一名稱。這可確保每組中的單選按鈕正常運作，並且選擇是互斥的。

#### Q：所有 PDF 檢視器和應用程式都支援分組複選框嗎？

答：是的，所有符合標準的 PDF 檢視器和應用程式都支援分組複選框。 PDF 規格定義了單選按鈕及其分組行為，使它們在 PDF 格式中得到普遍認可。但是，必須在不同的 PDF 檢視器中測試功能，以確保跨不同平台的行為一致。