---
title: 選擇 PDF 文件中的單選按鈕
linktitle: 選擇 PDF 文件中的單選按鈕
second_title: Aspose.PDF for .NET API 參考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中選擇單選按鈕。
type: docs
weight: 250
url: /zh-hant/net/programming-with-forms/select-radio-button/
---
以下是如何使用 Aspose.PDF for .NET 選擇單選按鈕的詳細教學。請依照下列步驟操作：

## 步驟 1：首先透過指定路徑來定義文件的目錄`dataDir` variable.

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟 2：使用以下命令開啟 PDF 文檔`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## 步驟 3：從文件表單中取得單選按鈕欄位。

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## 步驟 4：指定要從群組中選擇的單選按鈕的索引。

```csharp
radioField. Selected = 2;
```

## 步驟5：設定編輯後的PDF檔案的輸出路徑。

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## 步驟6：儲存修改後的PDF檔案。

```csharp
pdfDocument.Save(dataDir);
```

## 步驟 7：顯示確認訊息和儲存文件的位置。

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### 使用 Aspose.PDF for .NET 選擇單選按鈕的範例原始碼 
```csharp
try
{
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//開啟文件
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	//取得一個字段
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	//指定群組中單選按鈕的索引
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	//儲存 PDF 文件
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 選擇單選按鈕。透過執行上述步驟，您可以使用 Aspose.PDF for .NET 操作和修改 PDF 文件中的單選按鈕。


### 常見問題解答

#### Q：我可以使用 Aspose.PDF for .NET 選擇群組中的多個單選按鈕嗎？

答：不可以，群組中的單選按鈕被設計為互斥的。您一次只能在一組中選擇一個單選按鈕，選擇一個單選按鈕將自動取消選擇同一組中先前選擇的任何單選按鈕。

#### Q：如何使用 Aspose.PDF for .NET 檢索群組中選定的單選按鈕？

答：要檢索群組中選定的單選按鈕，您可以使用`Selected`的財產`RadioButtonField`班級。它將傳回群組內所選單選按鈕的索引。

#### Q：我可以自訂 PDF 文件中所選單選按鈕的外觀嗎？

答：是的，您可以使用 Aspose.PDF for .NET 自訂所選單選按鈕的外觀。您可以修改其顏色、大小、邊框樣式和其他視覺屬性以符合您所需的外觀。

#### Q：是否可以使用 Aspose.PDF for .NET 以程式設計方式建立新的單選按鈕群組？

答：是的，您可以使用 Aspose.PDF for .NET 以程式設計方式建立新的單選按鈕群組。您可以將新的單選按鈕新增至文件的表單中，並為每個單選按鈕指定相同的群組名稱以建立新群組。

#### Q：Aspose.PDF for .NET 支援使用互動式 PDF 表單嗎？

答：是的，Aspose.PDF for .NET 完全支援使用互動式 PDF 表單，包括單選按鈕、文字欄位、複選框和其他表單元素。您可以使用該程式庫輕鬆閱讀、修改和建立互動式 PDF 表單。