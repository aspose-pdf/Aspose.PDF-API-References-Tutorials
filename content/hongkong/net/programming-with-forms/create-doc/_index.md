---
title: 建立文檔
linktitle: 建立文檔
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 輕鬆建立具有單選按鈕的文件。
type: docs
weight: 40
url: /zh-hant/net/programming-with-forms/create-doc/
---
在本教學中，我們將向您展示如何使用 Aspose.PDF for .NET 建立具有單選按鈕的文件。我們將逐步解釋 C# 原始程式碼，以引導您完成此過程。

##第一步：準備

首先，確保您已匯入必要的庫並設定文件目錄的路徑：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：建立一個新文檔

建立一個新的 Document 物件來儲存 PDF 文件：

```csharp
Document doc = new Document();
```

## 第 3 步：新增頁面

新增頁面至文件：

```csharp
Page page = doc.Pages.Add();
```

## 第 4 步：新增單選按鈕字段

建立一個單選按鈕欄位並設定其位置和大小：

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## 第 5 步：新增單選按鈕選項

將所需的選項新增至單選按鈕欄位。您可以根據需要設定每個選項的座標和大小：

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## 步驟 6：將單選按鈕欄位新增至表單中

將單選按鈕欄位新增至文件表單欄位集合：

```csharp
doc.Form.Add(field);
```

## 步驟7：儲存文檔

儲存 PDF 文件：

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 建立文件的範例原始碼 
```csharp
try
{
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//建立一個新文檔
	Document doc = new Document();
	Page page = doc.Pages.Add();
	//新增單選按鈕字段
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	//新增單選按鈕選項。請注意，這些選項位於
	//既不是水平的也不是垂直的。
	//您可以嘗試為它們設定任何座標（甚至大小）。
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	//儲存 PDF 文件
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 建立具有單選按鈕的文件。透過執行以下步驟，您可以使用 Aspose.PDF 輕鬆地將單選按鈕新增至 PDF 文件中。

### 常見問題解答

#### Q：我可以使用 Aspose.PDF for .NET 自訂文件中單選按鈕的外觀嗎？

答：是的，您可以使用 Aspose.PDF for .NET 自訂文件中單選按鈕的外觀。您可以設定大小、顏色、邊框樣式等屬性來自訂單選按鈕的外觀。

#### Q：如何新增具有互斥選項的單選按鈕群組？

答：為了建立互斥的選項，您可以新增多個同名的單選按鈕欄位。這將確保當選擇選項時，將自動取消選擇其他同名選項。

#### Q：是否可以為單選按鈕設定預設選擇的選項？

答：是的，您可以使用 Aspose.PDF for .NET 為單選按鈕設定預設選擇的選項。您可以使用`Selected`的財產`RadioButtonOptionField`物件將選項標記為預設選取。

#### Q：我可以為單選按鈕新增事件處理程序嗎？

答：是的，您可以使用 Aspose.PDF for .NET 將事件處理程序新增至單選按鈕。您可以關聯 JavaScript 操作，例如`OnValueChanged`，新增至單選按鈕以在使用者選擇選項時執行特定操作。

#### Q：使用者做出選擇後，如何從單選按鈕群組中檢索所選選項？

答：您可以使用 Aspose.PDF for .NET 從單選按鈕群組中擷取所選選項。用戶做出選擇後，您可以訪問`Selected`的財產`RadioButtonOptionField`物件來檢查選擇了哪個選項。