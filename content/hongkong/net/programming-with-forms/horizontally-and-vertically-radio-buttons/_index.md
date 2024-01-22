---
title: 水平和垂直單選按鈕
linktitle: 水平和垂直單選按鈕
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 在 PDF 文件中輕鬆建立水平和垂直單選按鈕。
type: docs
weight: 180
url: /zh-hant/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
在本教學中，我們將向您展示如何使用 Aspose.PDF for .NET 在 PDF 文件中建立水平和垂直排列的單選按鈕。我們將逐步解釋 C# 原始程式碼，以引導您完成此過程。

## 第 1 步：準備

確保您已匯入必要的庫並設定文件目錄的路徑：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：載入文檔

載入現有的 PDF 文件：

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## 第 3 步：自訂單選按鈕選項

透過設定以下屬性來自訂單選按鈕選項：

```csharp
formEditor. RadioGap = 4; //兩個單選按鈕選項之間的距離
formEditor. RadioHoriz = true; //單選按鈕的水平佈局
formEditor.RadioButtonItemSize = 20; //單選按鈕的大小
formEditor.Facade.BorderWidth = 1; //單選按鈕邊框的寬度
formEditor.Facade.BorderColor = System.Drawing.Color.Black; //單選按鈕邊框顏色
```

## 第 4 步：新增水平單選按鈕

透過指定欄位的選項和位置來新增水平排列的單選按鈕：

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## 第 5 步：新增垂直單選按鈕

透過指定欄位的選項和位置來新增垂直排列的單選按鈕：

```csharp
formEditor. RadioHoriz = false; //單選按鈕的垂直佈局
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## 第 6 步：儲存文檔

儲存修改後的PDF文件：

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 的水平和垂直單選按鈕的範例原始碼 
```csharp
try
{
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//載入先前儲存的文檔
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	//RadioGap 是兩個單選按鈕選項之間的距離。
	formEditor.RadioGap = 4;
	//新增水平單選按鈕
	formEditor.RadioHoriz = true;
	//RadioButtonItemSize 如果單選按鈕項目的大小。
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	//新增其他垂直放置的單選按鈕
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	//儲存 PDF 文件
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 在 PDF 文件中建立水平和垂直排列的單選按鈕。透過執行這些步驟，您可以輕鬆自訂單選按鈕的佈局，並使用 Aspose.PDF 將它們新增至 PDF 文件中。

### 常見問題解答

#### Q：PDF 文件中水平和垂直排列的單選按鈕是什麼？

答：PDF文件中單選按鈕的水平和垂直排列是指單選按鈕選項的佈局方向。水平佈局將單選按鈕選項並排放置，讓使用者從左到右進行選擇。另一方面，垂直佈局將單選按鈕選項堆疊在一起，使用戶能夠從上到下進行選擇。

#### Q：如何自訂 Aspose.PDF for .NET 中單選按鈕選項的外觀？

答：您可以透過調整多個屬性來自訂 Aspose.PDF for .NET 中單選按鈕選項的外觀。 API 提供了設定兩個單選按鈕選項之間距離的選項（`RadioGap`），佈局方向（`RadioHoriz`)、單選按鈕項目的大小 (`RadioButtonItemSize`)、單選按鈕的邊框寬度和顏色等等。

#### Q：我可以在同一個 PDF 文件中新增水平和垂直單選按鈕嗎？

答：是的，您可以使用 Aspose.PDF for .NET 將水平和垂直單選按鈕新增至相同 PDF 文件。本教學中提供的範例原始程式碼示範如何先新增水平排列的單選按鈕，然後在同一個 PDF 文件中新增另一組垂直排列的單選按鈕。

#### Q：我可以為每組單選按鈕設定不同的單選按鈕選項嗎？

答：是的，您可以為每組單選按鈕設定不同的單選按鈕選項。每個組別都應該有獨特的`RadioButtonField`對象，以及`RadioButtonOptionField`每個群組中的物件應共享相同的頁面和其選項的唯一名稱。這可確保每組中的單選按鈕正常運作，並且選擇是互斥的。

#### Q：所有 PDF 檢視器和應用程式都支援單選按鈕的佈局和外觀設定嗎？

答：是的，所有符合標準的 PDF 檢視器和應用程式都支援單選按鈕的佈局和外觀設定。 PDF 規格定義了單選按鈕及其各種屬性，使它們在 PDF 格式中得到普遍認可。但是，必須測試單選按鈕在不同 PDF 檢視器中的外觀和行為，以確保跨不同平台的渲染一致。