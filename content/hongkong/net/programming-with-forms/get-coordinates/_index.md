---
title: 取得 PDF 表單欄位座標
linktitle: 取得 PDF 表單欄位座標
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 輕鬆取得 PDF 文件中的 PDF 表單欄位座標。
type: docs
weight: 120
url: /zh-hant/net/programming-with-forms/get-coordinates/
---
在本教學中，我們將向您展示如何使用 Aspose.PDF for .NET 取得 PDF 表單欄位座標。我們將逐步解釋 C# 原始程式碼，以引導您完成此過程。

## 第 1 步：準備

確保您已匯入必要的庫並設定文件目錄的路徑：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入輸出文檔

載入輸出 PDF 文件：

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## 第 3 步：尋找新增的字段

找到新增的表單欄位（在本例中，我們使用「Item1」、「Item2」和「Item3」欄位）：

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## 步驟 4：顯示每個欄位的子項位置

循環瀏覽每個欄位的選項並查看每個子項的座標：

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### 使用 Aspose.PDF for .NET 取得座標的範例原始碼 
```csharp
try
{
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//載入輸出文檔
	Document doc1 = new Document( dataDir + "input.pdf");
	//尋找新增的字段
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	//並顯示每個子項目的位置。
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 取得表單欄位座標。透過執行這些步驟，您可以使用 Aspose.PDF 輕鬆檢索 PDF 文件中表單欄位子元素的座標。

### 常見問題解答

#### Q：我可以使用此方法取得 Aspose.PDF for .NET 中任何類型表單欄位的座標嗎？

答：是的，您可以使用此方法來取得 Aspose.PDF for .NET 中各種類型表單欄位的座標。提供的 C# 原始程式碼示範如何取得 RadioButton 欄位的座標，但您可以對其他表單欄位類型（例如 TextBox、CheckBox、ListBox 等）採用相同的方法。

#### Q：如何修改或調整表單域座標？

答：表單域座標是基於 PDF 文件的座標系，原點 (0,0) 位於頁面的左下角。若要修改或調整表單欄位座標，您可以更新`Rect`對應表單欄位或其子項的屬性，例如 RadioButtonOptionField。

#### Q：我可以取得以程式設計方式新增到 PDF 文件中的表單欄位的座標嗎？

答：是的，您可以獲得以程式設計方式新增至 PDF 文件的表單欄位的座標。 Aspose.PDF for .NET 可讓您動態新增表單字段，新增後，您可以使用本教學課程中示範的方法檢索其座標。

#### Q：檢索表單欄位座標的目的是什麼？

答：當您需要對 PDF 文件中的表單欄位執行特定的佈局相關操作或驗證時，檢索表單欄位座標會很有幫助。它允許您根據表單字段的座標準確定位和對齊表單字段，確保它們正確顯示在文件中並提供無縫的用戶體驗。

#### Q：表單欄位座標是以點還是其他單位表示的？

答：Aspose.PDF for .NET 中的表單欄位座標以點表示。 1 點相當於 1/72 英寸，使其成為 PDF 格式中的標準測量單位。