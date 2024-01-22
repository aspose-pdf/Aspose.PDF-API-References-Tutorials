---
title: 單選按鈕
linktitle: 單選按鈕
second_title: Aspose.PDF for .NET API 參考
description: 使用 Aspose.PDF for .NET 輕鬆將單選按鈕新增至 PDF 文件。
type: docs
weight: 220
url: /zh-hant/net/programming-with-forms/radio-button/
---
在本教學中，我們將向您展示如何使用 Aspose.PDF for .NET 在 PDF 文件中新增單選按鈕。我們將逐步解釋 C# 原始程式碼，以引導您完成此過程。

## 第 1 步：準備

確保您已匯入必要的庫並設定文件目錄的路徑：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：實例化文檔對象

實例化一個 Document 物件來建立一個新的 PDF 文件：

```csharp
Document pdfDocument = new Document();
```

## 第 3 步：新增頁面

在 PDF 文件中新增頁面：

```csharp
pdfDocument.Pages.Add();
```

## 第 4 步：實例化 RadioButtonField 對象

實例化一個 RadioButtonField 對象，並將頁碼指定為參數：

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## 第 5 步：新增單選按鈕選項

透過使用 Rectangle 物件指定每個選項的座標，將單選按鈕選項新增至 RadioButtonField 物件：

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## 第 6 步：將單選按鈕新增至表單中

將單選按鈕新增至文件的 Form 物件：

```csharp
pdfDocument.Form.Add(radio);
```

## 第7步：儲存PDF文檔

儲存已建立的PDF文件：

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 的單選按鈕範例原始碼 
```csharp
try
{
	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//實例化文檔對象
	Document pdfDocument = new Document();
	//將頁面新增至 PDF 文件
	pdfDocument.Pages.Add();
	//以頁碼作為參數實例化 RadioButtonField 對象
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	//新增第一個單選按鈕選項，並使用 Rectangle 物件指定其原點
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	//新增第二個單選按鈕選項
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	//新增單選按鈕以形成 Document 物件的對象
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	//儲存 PDF 文件
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 結論

在本教學中，我們學習如何使用 Aspose.PDF for .NET 在 PDF 文件中新增單選按鈕。透過執行以下步驟，您可以輕鬆建立單選按鈕並將其放置在 PDF 文件中的特定頁面上。


### 常見問題解答

#### Q：我可以自訂單選按鈕的外觀，例如其大小和顏色嗎？

答：是的，您可以使用以下命令自訂單選按鈕的外觀`Rectangle`物件的座標來定義其大小和位置。 Aspose.PDF for .NET 可讓您調整單選按鈕的外觀以符合您的需求。

#### Q：我可以在同一頁上新增多個不同群組的單選按鈕嗎？

答：是的，您可以在同一頁面上新增多個具有不同群組的單選按鈕。每組單選按鈕可以有一個唯一的名稱，並且一次只能選擇每組中的一個選項。

#### Q：如何為單選按鈕選項新增標籤或文字描述？

答：若要為單選按鈕選項新增標籤或文字描述，您可以使用`TextStamp`Aspose.PDF for .NET 中的類，用於在 PDF 文件上的特定座標處覆蓋文字。

#### Q：Aspose.PDF for .NET 是否與所有版本的 .NET Framework 相容？

答：是的，Aspose.PDF for .NET 與所有版本的 .NET Framework 相容，包括 .NET Core 和 .NET Standard。

#### Q：我可以透過程式控制 PDF 文件中單選按鈕選項的選擇嗎？

答：是的，您可以使用以下命令以程式方式控制單選按鈕選項的選擇：`IsSelected`的財產`RadioButtonOption`班級。此屬性可讓您設定選定的特定選項。